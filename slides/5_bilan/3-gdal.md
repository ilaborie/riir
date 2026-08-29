+++
title = "Et notre CVE ?"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}

.punchline {
  font-size: 150%;
  display: flex;
  justify-content: center;
  text-align: center;
}
</style>

### 🗺️ Et notre CVE GDAL ?

<!-- pause -->

#### ❌ Non, on ne réécrit pas GDAL

C++, 200+ formats, 25 ans de corrections de bugs

<!-- pause -->

#### 🎯 Le bug n'est pas dans GDAL, mais dans un `zlib` embarqué

<!-- pause -->

#### 🛠️ Réduire le périmètre

- **mettre à jour** — GDAL ≥ 3.11.0
- **isoler** — <span lang="en">sandbox</span>, WASM
- **remplacer** le composant C — [zlib-rs](https://trifectatech.org/blog/zlib-rs-is-faster-than-c/) : <span lang="en">memory-safe</span> **et** le plus rapide

<!-- pause -->

#### 📉 Écrire le neuf en Rust

Android : **76% → 24%** des vulnérabilités mémoire <small>(2019-2024)</small>

sans réécrire l'ancien code — en géo, [GeoRust](https://georust.org/)

<!-- pause -->

<div class="punchline">
    <strong>On n'a pas besoin de RIIR de tout.<br>Il faut RIIR ce qui compte.</strong>
</div>

<!-- notes -->

On boucle la boucle : on a ouvert sur cette CVE, on y répond.
Le slide sépare volontairement DEUX choses qu'on mélange souvent :
traiter la faille d'aujourd'hui, et ne pas en refabriquer demain.

❌ Réécrire GDAL est une mauvaise idée
Frank Warmerdam a commencé en 1998, première release en 2000.
200+ formats raster et vecteur, dont des formats propriétaires
que plus personne ne sait re-spécifier.
Toute la valeur de GDAL, c'est justement ces 25 ans de cas tordus.
Une réécriture repart de zéro sur ce plan-là.

🎯 Relire la CVE — et se rappeler giflib (slide précédent)
CVE-2026-4738 n'est pas dans le code géospatial de GDAL.
Elle est dans frmts/zlib/contrib/infback9 — un décodeur de compression C
embarqué. Le périmètre à traiter n'est pas « GDAL », il est minuscule.
Google fait exactement ça : réécrire, assisté par IA, LA DÉPENDANCE C
à risque plutôt que le produit entier.

Détail vérifié, et il porte : GDAL ne dépend pas d'un zlib système,
il embarque une COPIE MINIFIÉE du contrib (frmts/zlib/contrib/infback9/,
10 fichiers, dont minified_zutil.c). Du C copié-collé, qui diverge
de l'amont. C'est le profil type de la dépendance vendorisée oubliée.

🛠️ Réduire le périmètre — c'est le mouvement, pas la liste
Le titre nomme ce qu'on fait : on passe de « GDAL » (200+ formats,
25 ans) à « un décodeur de compression C ». Les trois réponses
ci-dessous portent toutes sur ce périmètre-là, minuscule.
Et elles se cumulent, ce n'est pas un menu à la carte :
- mettre à jour : le correctif existe, GDAL >= 3.11.0. À faire d'abord,
  aujourd'hui. C'est la réponse au mail du RSSI.
- isoler : le parsing de fichiers non fiables derrière un bac à sable
  ou compilé en WASM (cf. Wasmtime, slide 3.4). Ça vaut pour les 200
  autres formats qu'on n'a pas audités.
- remplacer le composant C : zlib-rs. Réécriture Rust de zlib,
  aujourd'hui le zlib le plus rapide en décompression — devant zlib-ng
  et devant celui de Chromium. +10% sur 1 ko, +6% à 65 ko,
  +10 à 20% en WASM. Ça répond à l'objection « réécrire = régresser » :
  non, la sécurité ne se paie pas en performance.

⚠️ Honnêteté — à assumer sur scène, ça renforce le propos
Ne PAS dire « on remplace par zlib-rs et la CVE est corrigée ».
Vérifié dans le code : zlib-rs couvre inflate/deflate, PAS le deflate64.
Zéro occurrence de deflate64 dans le dépôt, et son API C exporte
inflateBack mais pas inflateBack9 — or infback9, c'est précisément
le deflate64, un contrib que zlib lui-même ne compile pas par défaut.
Donc le composant exactement fautif n'a pas encore d'équivalent Rust.
zlib-rs illustre la STRATÉGIE (remplacer le composant C à risque),
il n'est pas le correctif de cette CVE-ci. Si on pose la question,
la bonne réponse est : « on met à jour et on isole aujourd'hui ;
zlib-rs montre où va le remplacement, et qu'il ne coûte rien. »

📉 La preuve à l'échelle : Android — c'est l'autre moitié du slide

Ce que mesurent EXACTEMENT les chiffres, à savoir avant de les dire :
la PART des vulnérabilités Android qui sont des failles mémoire.
Formulation d'origine : « the percentage of Android vulnerabilities
attributable to memory safety issues has fallen from 76 percent in 2019
to an expected 24 percent by the end of 2024 ».
Périmètre : code first-party ET open source tiers, sur C, C++, Java,
Kotlin et Rust. Et ça continue : sous les 20% en 2025.

⚔️ L'objection à préparer : « c'est une proportion, elle baisse peut-être
juste parce que les AUTRES catégories ont explosé ».
La parade, en une phrase : les chiffres ABSOLUS baissent aussi.
223 vulnérabilités mémoire en 2019 → moins de 50 en 2024, soit -68%.
La proportion s'effondre ET le compte s'effondre — alors même que le
volume de code C++ continue d'augmenter.
Le point clé, et c'est contre-intuitif :
Google n'a PAS réécrit l'ancien code.
Ils ont écrit le NOUVEAU code dans un langage memory-safe,
et laissé l'ancien tranquille (hors correctifs importants).
La proportion s'effondre alors même que le volume de code C++ augmente.
C'est ça que prouve le chiffre — pas les trois réponses du dessus.

🌍 GeoRust — et la réponse à l'issue du début
L'issue du slide 1.4 proposait « use existing crates from GeoRust ».
La réponse honnête est en deux temps :
- non, GeoRust ne remplace pas GDAL. On est très loin de l'iso-fonctionnel,
  et ce ne serait pas du RIIR mais du greenfield.
- oui, GeoRust est le bon endroit pour le CODE NEUF en géospatial.
C'est la déclinaison géo de ce que Google a fait sur Android.

<https://blog.google/security/rust-in-android-move-fast-fix-things/>
<https://trifectatech.org/blog/zlib-rs-is-faster-than-c/>
<https://github.com/advisories/GHSA-hp6p-5qh5-w9fj>
