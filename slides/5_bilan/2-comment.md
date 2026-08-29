+++
title = "Comment RIIR ?"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}

/* `.scale` réduisait les trois exemples à 95% pour les faire tenir ; les deux
   lignes récupérées en retirant les <br> forcés rendent ça inutile, et ils sont
   plus lisibles à la taille du reste du slide. */
.scale small {
  opacity: .75;
}
</style>

### Comment RIIR ?

<!-- pause -->

#### 🧗 Par composants

Un composant à la fois — Firefox, [RediSearch](https://github.com/RediSearch/RediSearch)

<!-- pause -->

#### 🤖 Traduction automatique

- [c2rust](https://github.com/immunant/c2rust) : transpilation à base de règles
- [DARPA TRACTOR](https://www.darpa.mil/research/programs/translating-all-c-to-rust) : <span lang="en">*Translating All C To Rust*</span>

<!-- pause -->

#### 🏗️ Trois échelles

<div class="scale">

- une **dépendance** — [Google, `giflib`](https://bughunters.google.com/blog/scaling-memory-safety) : perf neutre, millions de tests
- **tout** le code — [Bun](https://bun.com/blog/bun-in-rust) : 535 000 lignes Zig → Rust en **11 jours**
- une **réimplémentation** — [pgrust](https://github.com/malisper/pgrust) : Postgres, 46 066 tests <small>(pas pour la prod)</small>

</div>

<!-- pause -->

#### ⚠️ Deux pièges

- le **`unsafe`** : un port mécanique = du C déguisé en Rust
- l'**oracle** : écrire le Rust n'est plus le goulot, **prouver l'équivalence** l'est

<!-- notes -->

Le talk dit *pourquoi* et *quoi*. Voici *comment*.

🧗 Par composants — et ça reste partiel, c'est ça le point
La méthode Firefox / « oxidation » : on ne big-bang pas.
Un composant, une interface stable, on remplace derrière.

⚠️ Ne PAS dire « progressivement » : ça laisse entendre qu'on avance
vers une réécriture complète, donc que le succès se mesure à la fin.
Personne ne prévoit de réécrire Firefox en entier, ni Redis.
L'état partiel n'est pas une étape, c'est la destination.
(Et ça prépare le slide suivant : reste à choisir QUOI réécrire.)

🔍 RediSearch — l'exemple le plus parlant, et il est en cours
C'est le moteur de requêtes / recherche de Redis, et depuis Redis 8
il est intégré à Redis, ce n'est plus un module optionnel.
Mainmatter (Luca Palmieri) le migre du C vers Rust, un module à la fois.
Le chiffre à lâcher : dans le dépôt, Rust est AUJOURD'HUI le premier
langage — ~6,95 Mo de Rust contre ~5,15 Mo de C. Rust a dépassé C.
Et pourtant personne ne réécrit Redis : Redis lui-même reste en C.
On réécrit le moteur de recherche à l'intérieur, pas le produit.

- 🎥 Luca Palmieri, « Rewrite, Optimize, Repeat », EuroRust 2025
  <https://youtu.be/XklFGy3aUX4>
- 📖 The C to Rust Migration Book
  <https://mainmatter.com/c-to-rust-migration-book/>
- <https://github.com/RediSearch/RediSearch>

🤖 L'outillage
- c2rust : transpilation à base de règles. Ça compile, mais ça produit
  du « C déguisé en Rust ». Sur CRUST-Bench : 62% de compilation,
  21% de tests qui passent, et surtout 69,6% des lignes en `unsafe`.
  On a déplacé le problème, pas résolu.
  Les approches agentiques (LLM + analyse statique + boucle de compilation)
  descendent à 0,06% d'unsafe et 92% de tests qui passent — même benchmark.
  (Attention : ne jamais comparer des chiffres de benchmarks différents.)

  ⚠️ Précision si on pose la question « c2rust utilise un LLM ? » :
  NON pour le transpileur. `c2rust transpile` et `c2rust refactor` sont
  déterministes (Clang). Le dépôt ajoute en revanche un troisième outil,
  `c2rust postprocess`, lui « LLM-powered », pour le nettoyage qu'on ne
  sait pas automatiser de façon déterministe. D'où le titre du slide :
  « traduction automatique », pas « assisté par LLM ».

  💎 Et c'est LEUR README qui pose le piège n°2, à citer à l'oral :
  « Even though the postprocessor validates the output of LLMs, it can
    introduce errors; we recommend using it in combination with a robust
    test suite. »
  Ce ne sont pas les sceptiques du LLM qui disent ça, ce sont ceux qui en
  ont mis un dans leur transpileur. Enchaîner sur l'oracle.
  <https://github.com/immunant/c2rust>
- DARPA TRACTOR : 7 équipes financées ~2 M$ chacune, benchmarks publiés
  tous les 6 mois par le MIT Lincoln Laboratory. Quand la DARPA met ça
  sur la table, ce n'est plus un sujet de hackathon.
- Le LLM seul, sans analyse ni boucle de compilation, introduit des bugs :
  « Lost in Translation », étude empirique des bugs de traduction par LLM
  <https://alirezai.cs.illinois.edu/assets/pdf/plempirical.pdf>

🏗️ Les trois échelles — c'est le cœur du slide

🐜 Google, giflib (Max Hils & Bastian Kersting)
« AI-Assisted Rewrites of C/C++ Dependencies to Rust ».
On ne réécrit pas le produit : on réécrit LA DÉPENDANCE C à risque.
Validé par des millions de tests, performance neutre.
C'est exactement ce qu'on ferait pour le zlib de GDAL — cf. slide suivant.

🍞 Bun (8 juillet 2026)
535 496 lignes de Zig → Rust, du 3 au 14 mai 2026. 11 jours.
6 502 commits, jusqu'à 695 commits en une heure, 64 Claude en parallèle
sur 4 worktrees git. ~165 000 $ d'API, 690 M de tokens de sortie.
Workflow adversarial : un Claude implémente, DEUX Claude relisent
indépendamment en cherchant des bugs, un quatrième corrige.
Choix assumé : portage mécanique fidèle à l'architecture Zig d'abord,
refactoring idiomatique APRÈS la 1.4. Gains modestes en perf
(2-5% HTTP/CLI) mais binaire ~20% plus petit et fuites mémoire éliminées.
La citation qui tue : « à la main, ça aurait pris 3 ingénieurs
qui connaissent le code environ un an… on ne l'aurait jamais fait. »
Nuance à dire : c'est du Zig → Rust, pas du C legacy. Zig est déjà moderne.
La motivation reste la sécurité mémoire (use-after-free, double-free
en mélangeant valeurs JS gérées par le GC et mémoire manuelle).

🐘 pgrust
Pas une traduction : une RÉIMPLÉMENTATION. « Postgres s'il était
écrit en 2026 ». Compatible wire + dialecte SQL avec Postgres 18.3.
Passe les 46 066 tests de la suite de régression Postgres.
1 000 des 3 000 fonctions vérifiées formellement avec Kani.
Le README annonce des perfs spectaculaires, mais dit aussi noir sur blanc :
« not production ready, do not put data you care about in it ».
À présenter comme une démonstration de faisabilité, pas comme un remplaçant.

☢️ Piège n°1 : le `unsafe` — le contre-argument le plus sérieux
Un RIIR raté ne donne pas du Rust, il donne du C avec une syntaxe Rust.
c2rust : 69,6% des lignes en `unsafe` sur CRUST-Bench.
⚠️ CE CHIFFRE N'EST PLUS SUR LE SLIDE — le dire à l'oral,
c'est lui qui rend le piège concret.
On a payé le coût de la réécriture SANS acheter la sécurité mémoire.

Et c'est pire que ça : les règles d'`unsafe` Rust (aliasing, UB)
sont PLUS strictes que celles du C. Un port mécanique en `unsafe`
peut introduire de l'UB que le C d'origine n'avait pas.

Nuance honnête : `unsafe` n'est pas l'ennemi en soi. zlib-rs en contient
pour les optimisations SIMD. Ce qui compte, c'est la SURFACE :
quelques centaines de lignes auditables, encapsulées derrière une API sûre,
ce n'est pas 70% du code.
Bun l'assume aussi : portage mécanique d'abord, idiomatique après la 1.4.
La dette est explicite et datée — c'est ça, la bonne façon de la prendre.

Question à se poser après un RIIR assisté :
« combien de lignes `unsafe`, et est-ce que je peux les relire toutes ? »

🎯 Piège n°2 : l'oracle — LE point à faire passer
Regardez ce que les trois ont en commun. Ce n'est pas le modèle utilisé,
ni le langage de départ. C'est le HARNAIS DE TEST :
- giflib : des millions de tests
- Bun : 60 624 fichiers de test, 1,39 M d'assertions, ZÉRO test supprimé.
  Et la suite est en TypeScript, donc agnostique du langage : elle a survécu
  au changement de langage. C'est ça qui rend le port vérifiable.
- pgrust : les 46 066 tests de régression de Postgres + vérification formelle

Le LLM sait écrire le Rust. Il ne sait pas prouver qu'il fait la même chose.
Tests différentiels, fuzzing (cargo-fuzz), property testing (proptest),
snapshots : c'est là que passe le vrai travail.
Sans oracle, un RIIR assisté par LLM ne fait que déplacer les bugs.

Et ça prépare le slide suivant : si vous n'avez pas l'oracle,
vous ne réécrivez pas — vous isolez et vous écrivez le neuf en Rust.
