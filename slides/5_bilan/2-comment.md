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

Un composant à la fois - Firefox, [RediSearch](https://github.com/RediSearch/RediSearch)

- [🎥 Luca Palmieri, « Rewrite, Optimize, Repeat », EuroRust 2025](https://youtu.be/XklFGy3aUX4)
- [📖 The C to Rust Migration Book](https://mainmatter.com/c-to-rust-migration-book/)

<!-- pause -->

#### 🤖 Traduction automatique

- [c2rust](https://github.com/immunant/c2rust) : transpilation à base de règles
- [DARPA TRACTOR](https://www.darpa.mil/research/programs/translating-all-c-to-rust) : <span lang="en">*Translating All C To Rust*</span>

<!-- pause -->

#### Des exemples avec LLM

<div class="scale">

- [Google, `giflib`](https://bughunters.google.com/blog/scaling-memory-safety) : perf neutre, millions de tests
- [Bun](https://bun.com/blog/bun-in-rust) : 535 000 lignes Zig → Rust en **11 jours**
- [pgrust](https://github.com/malisper/pgrust) : Postgres, 46 066 tests

</div>

<!-- pause -->

#### ⚠️ Des pièges

- Génération avec des **`unsafe`** (du C déguisé en Rust)
- Comment prouver l'équivalence ?

<!-- notes -->
