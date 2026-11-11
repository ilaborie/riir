+++
title = "Web avec WASM"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>

### <abbr title="Web Assembly">WASM</abbr>

<!-- pause -->

#### 📦 Crates

- [Leptos](https://leptos.dev/): full-stack comme React
- [Dioxus](https://dioxuslabs.com/) : cross-platform (web/desktop/mobile)
- [wasm-bindgen](https://wasm-bindgen.github.io/wasm-bindgen/), [Trunk](https://trunkrs.dev/) : le socle et le bundler

<!-- pause -->

#### 📦 Hors du navigateur

- [WASI](https://wasi.dev/) 0.2, modèle de composants
- [Wasmtime](https://wasmtime.dev/) : exécuter du code non fiable **isolé**

<!-- pause -->

- [🎥 Et si on écrivait nos Web Components en Rust ?](https://www.youtube.com/watch?v=OPKFfHmMuqg)

<!-- pause -->

#### 🏆 Champions

- [✏️ graphite.rs](https://graphite.rs/)
- [IronCalc](https://github.com/ironcalc/IronCalc)

<!-- notes -->

Avantages :
- Performances proches du natif dans le navigateur
- Partage de code entre client et serveur
- Sécurité par défaut (pas de XSS, buffer overflows)
- Taille de binaire optimisée

Hors navigateur : WASI 0.2 + le modèle de composants font de WASM
un bac à sable portable. C'est LA réponse au « isoler » du slide 5.3 :
si on ne peut pas réécrire une bibliothèque C, on peut la compiler
en WASM et lui retirer l'accès à la mémoire de l'hôte.
Le parsing de fichiers non fiables est le cas d'école.

Note : référence au talk web-components pour plus de détails