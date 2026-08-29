+++
title= "Contrôle sans GC"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>

### Rust Vs langages à gestion de mémoire

<!-- pause -->

#### 🏎️ Performance

- Pas de <abbr title="ramasse miettes">GC</abbr>
- Abstractions à coût nul
- 📈 meilleures performances moyennes, p99
- 📉 moins de mémoire

<!-- pause -->

#### 🎛️ Contrôle sur la gestion mémoire

- Choix d'allocation: pile ou tas
- Choix de pattern d'allocation: arena, slab, ...
- Choix de l'allocateur: jemalloc, mimalloc, ...

<!-- notes -->

GC: coût au runtime (CPU/mémoire)