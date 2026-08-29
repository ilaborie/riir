+++
title = "Client lourd"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>

### Application desktop

<!-- pause -->

#### 🍬 UI Native

- [slint](https://slint.rs/)
- [gpui](https://www.gpui.rs/)
- [Iced](https://github.com/iced-rs/iced)
- [Xilem](https://github.com/linebender/xilem/), [Masonry](https://github.com/linebender/xilem/tree/main/masonry), [Vello](https://github.com/linebender/vello) — [Linebender](https://linebender.org/), ...

<!-- pause -->

#### 🕸️ Web Based

- [Tauri](https://tauri.app/)
- [Dioxus](https://dioxuslabs.com/)

<!-- pause -->

#### 🏆 Champions

- [Zed](https://zed.dev/): <abbr title="Integrated Development Environment">IDE</abbr>, [**1.0** en avril 2026](https://zed.dev/blog/zed-1-0)
- [COSMIC desktop](https://system76.com/cosmic): [**Epoch 1**](https://blog.system76.com/post/cosmic-epoch-1-updates/), avec [Pop!_OS 24.04 LTS](https://system76.com/pop/)

<!-- notes -->

🍬 Linebender
Xilem n'est que la couche du dessus. Le collectif Linebender construit
toute la pile 2D en Rust, et chaque brique est utilisable séparément :
- Masonry : le framework de widgets sous Xilem
- Vello : moteur de rendu 2D sur GPU (compute shaders)
- Parley : mise en page de texte riche (+ Fontique pour le fallback de fontes)
- Kurbo : courbes de Bézier et géométrie de chemins
C'est l'héritage de Druid, désormais en maintenance passive.
Ces crates servent bien au-delà de Xilem — Vello est utilisé par Bevy.
<https://linebender.org/>

Zed 1.0 : sorti le 29 avril 2026, sur GPUI, son propre framework
UI écrit en Rust. Un IDE qui atteint sa 1.0, pas une préversion.

COSMIC Epoch 1 : sorti le 11 décembre 2025 avec Pop!_OS 24.04 LTS.
Un environnement de bureau complet, écrit from scratch en Rust —
pas un composant, tout l'environnement.

Avantages :
- Binaires légers sans runtime
- Démarrage instantané
- Faible consommation mémoire vs Electron
- Performances natives
