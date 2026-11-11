+++
title = "TUI"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>

### <abbr title="Terminal User Interface">TUI</abbr>

<!-- pause -->

#### 📦 Crates

- [🐀 Ratatui](https://ratatui.rs/) : framework TUI moderne
- [Crossterm](https://github.com/crossterm-rs/crossterm) : terminal cross-platform 

<!-- pause -->

#### 🏆 Champions

- [🐢 atuin](https://github.com/atuinsh/atuin): historique du shell
- [Yazi](https://yazi-rs.github.io/): gestionnaire de fichier
- [Gitui](https://github.com/gitui-org/gitui) : Git UI
- [ATAC](https://github.com/Julien-cpsn/ATAC): API client (Postman)
- [yozefu](https://github.com/MAIF/yozefu/): explore Kafka cluster
- [Bottom (btm)](https://github.com/ClementTsang/bottom) : monitoring process
- [Zellij](https://zellij.dev/): multiplexeur tmux-like
- ...

<!-- notes -->

Avantages Rust pour TUI :
- Performances excellentes même avec beaucoup de données
- Gestion robuste des événements keyboard/mouse
- Cross-platform (Windows, macOS, Linux)
- Rendu fluide et responsive
- Gestion mémoire efficace pour l'affichage

