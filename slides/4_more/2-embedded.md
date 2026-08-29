+++
title = "Embarqué"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>


### Embarqué & IoT

- 📖 [The embedded Rust Book](https://docs.rust-embedded.org/book/)
- 📖 [impl Rust for ESP32](https://esp32.implrust.com/)
- [Ferrocene](https://ferrocene.dev/en/): Rust pour les systèmes critique

<!-- pause -->

#### 📦 Crates

- [embassy](https://github.com/embassy-rs/embassy) : async/await embedded
- [embedded-graphics](https://github.com/embedded-graphics/embedded-graphics), [embedded-svc](https://github.com/esp-rs/embedded-svc), [embedded-hal](https://github.com/rust-embedded/embedded-hal) : abstraction hardware cross-platform
- [heapless](https://github.com/rust-embedded/heapless), [defmt](https://github.com/knurling-rs/defmt), ...

<!-- pause -->

#### 🎯 Cibles

ARM Cortex-M (STM32, nRF, ...), RISC-V, ESP32 (avec [esp-rs](https://github.com/esp-rs)), AVR (expérimental)

<!-- notes -->

Écosystème fragmenté mais très riche :
- embedded-hal : abstraction hardware cross-platform
- RTIC : framework temps réel pour microcontrôleurs
- Embassy : async/await pour embedded

Projets notables :
- Redox OS : OS complet écrit en Rust
- Tock OS : OS pour microcontrôleurs
- Noyau Linux : le support Rust est entré en 6.1 (2022), et la phase
  « expérimentale » a été officiellement close au sommet des mainteneurs
  de décembre 2025 — Rust est désormais un composant permanent du noyau.
  <https://lwn.net/Articles/1049831/>

Ferrocene : la toolchain Rust qualifiée pour le safety-critical
(ISO 26262 / IEC 61508). Ça change la conversation avec un auditeur :
on ne défend plus le langage, on montre la certification.

Défis : écosystème encore jeune, courbe d'apprentissage

