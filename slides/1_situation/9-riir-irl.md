+++
title = "RIIR IRL"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>

### RIIR <abbr title="In Real Life">IRL</abbr>

<!-- pause -->

####  🔌 Infrastructure

[Discord](https://discord.com/blog/why-discord-is-switching-from-go-to-rust),
[Figma](https://www.figma.com/blog/rust-in-production-at-figma/),
[Dropbox](https://qconsf.com/sf2016/sf2016/presentation/going-rust-optimizing-storage-dropbox.html)

<!-- pause -->

#### 🛠️ Outils systèmes

[sudo-rs](https://github.com/trifectatechfoundation/sudo-rs) &
[coreutils](https://github.com/uutils/coreutils): par défaut dans [Ubuntu 26.04 LTS](https://canonical.com/blog/canonical-releases-ubuntu-26-04-lts-resolute-raccoon),
[Fish Shell](https://fishshell.com/blog/rustport/): portage terminé (4.0),
[gitoxide](https://github.com/GitoxideLabs/gitoxide)

<!-- pause -->

#### 🗄️ Base de données

[InfluxDB](https://www.influxdata.com/blog/meet-founders-who-rewrote-in-rust/),
[Turso (sqlite)](https://turso.tech/blog/introducing-limbo-a-complete-rewrite-of-sqlite-in-rust)

<!-- pause -->

...

<!-- notes -->
**Mème devenu réalité** dans l'industrie tech

Discord: Go → Rust  latence /10
Figma: Serveur multiplayer
Dropbox: Stockage optimisé

sudo-rs + uutils/coreutils: par défaut depuis Ubuntu 26.04 LTS
(« Resolute Raccoon », 23 avril 2026). C'est la PREMIÈRE LTS —
donc du support 5 ans — à livrer sudo et les coreutils en Rust,
plus des drivers et sous-systèmes noyau en Rust.
Ce ne sont plus des projets de niche : c'est ce qui tourne
sur la machine par défaut.
Nuance à assumer si on pose la question : cp, mv et rm restent
fournis par GNU en 26.04 (TOCTOU non résolus côté uutils).
Fish Shell: portage vers Rust terminé, sorti en 4.0 (mars 2025)

InfluxDB: Core réécrit
Turso: SQLite moderne

