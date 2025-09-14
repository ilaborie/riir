+++
title = "Embarqué"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  margin-bottom: 2em;
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


<!-- notes -->

Écosystème fragmenté mais très riche :
- embedded-hal : abstraction hardware cross-platform
- RTIC : framework temps réel pour microcontrôleurs
- Embassy : async/await pour embedded

Projets notables :
- Redox OS : OS complet écrit en Rust
- Tock OS : OS pour microcontrôleurs
- Linux kernel modules : acceptés depuis 2022



Défis : écosystème encore jeune, courbe d'apprentissage

