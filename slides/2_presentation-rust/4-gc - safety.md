+++
title= "Sécurité du langage"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>


### Autres avantages

<!-- pause -->

#### 🛟 Système de typage

- Types de données algébriques, `trait`
- <span lang="en">Pattern matching</span>
- `Option` et `Result`

<!-- pause -->

#### 🔑 Propriété et emprunt

- `T` : transfert de propriété (<span lang="en">move</span>)
- `&T` : emprunt partagé — `&mut T` : emprunt exclusif
- <abbr title="Resource Acquisition Is Initialization">RAII</abbr> : libération déterministe (`Drop`)

<small>Une seule règle : plusieurs lecteurs, **ou** un seul écrivain. Jamais les deux.</small>

<!-- pause -->

#### 🧵 <span lang="en">Fearless concurrency</span>

- `Send` : transférable vers un autre thread
- `Sync` : partageable entre threads
- Pas de <span lang="en">data race</span>, à la compilation

<!-- notes -->

🛟 Système de typage
pas de `null`
pas d'exceptions
Mais pas d'héritage (OOP)

Typage proche FP
Mais Zero cost

🔑 Propriété et emprunt — à dire : ça sert D'ABORD en mono-thread
Le borrow checker n'est pas un outil de concurrence. La majorité des
développeurs en bénéficient sans jamais écrire un `thread::spawn` :
pas d'use-after-free, pas de double-free, pas d'invalidation d'itérateur,
et une libération déterministe (`Drop`) — donc pas seulement de la mémoire,
aussi les fichiers, les verrous, les connexions.

La règle affichée est la formulation courte de « aliasing XOR mutation » :
soit N lecteurs, soit 1 écrivain, jamais les deux en même temps.
Tout le reste en découle.

🧵 Fearless concurrency — LE pont entre les deux blocs
C'est le point à faire passer : `Send` et `Sync` ne sont pas un système
à part. Ils font remonter AU NIVEAU DES THREADS exactement la règle du
bloc précédent. Deux blocs, une seule idée, à deux échelles.
- `Send` : la valeur peut être transférée vers un autre thread
- `Sync` : `&T` peut être partagé entre threads (donc T: Sync ⟺ &T: Send)
Ce sont des traits marqueurs AUTO-DÉRIVÉS, propagés par le compilateur :
on ne les écrit presque jamais à la main. Un `Rc` n'est pas `Send`, et
c'est le compilateur qui refuse de le laisser traverser un thread.

« Fearless concurrency » est le terme du Rust Book, pas une formule maison.
<https://doc.rust-lang.org/book/ch16-00-concurrency.html>
