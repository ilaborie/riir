+++
title = "Mobile"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>

### 📱 Mobile

<!-- pause -->

#### 🏗️ Un cœur en Rust, deux UI natives

La logique métier une seule fois — SwiftUI d'un côté, Jetpack Compose de l'autre

<!-- pause -->

#### 📦 Crates

- [UniFFI](https://mozilla.github.io/uniffi-rs/latest/) : bindings Swift & Kotlin générés
- [Crux](https://github.com/redbadger/crux) : structurer le cœur partagé
- [Flutter Rust Bridge](https://cjycode.com/flutter_rust_bridge/), ou tout en Rust avec [Tauri](https://tauri.app/), [Dioxus](https://dioxuslabs.com/)

<!-- pause -->

#### 🏆 Champions

- [**Proton Mail**](https://proton.me/blog/next-generation-proton-mail-mobile-apps) : **80%** du code partagé iOS/Android
- [**Element X**](https://github.com/matrix-org/matrix-rust-sdk) : Matrix Rust SDK, iOS **et** Android
- [**Mullvad**](https://mullvad.net/en/blog/announcing-gotatun-the-future-of-wireguard-at-mullvad-vpn) : WireGuard en Rust, plantages **0,40% → 0,01%**
- **Signal**, **1Password** : le cœur cryptographique

<!-- notes -->

🏗️ Le motif — LE point à faire passer
On ne réécrit pas l'UI. La logique métier passe en Rust, l'interface
reste SwiftUI / Jetpack Compose. C'est le RIIR par composants du bilan
(slide 34), appliqué au mobile.

📦 Outillage
- UniFFI (Mozilla) : génère les bindings Kotlin/Swift depuis le Rust.
- Crux (Red Badger) : structure le cœur partagé — cœur sans effets de
  bord d'un côté, coquille native de l'autre. Pré-1.0 mais donné
  production-ready ; utilisé par Proton et PhotoRoom.
- Tauri 2 et Dioxus font aussi du mobile, mais moins mûrs que
  flutter_rust_bridge sur ce terrain.
- Le dépôt d'exemple de Proton (Rust Nation 2026) montre l'assemblage
  complet : Rust + Crux + UniFFI + serde codegen.
  <https://github.com/ProtonMail/proton-rust-nation-2026>

🏆 Proton Mail — le plus spectaculaire, et il est récent
Billet d'ingénierie du 2 février 2026. Réécriture complète des apps
iOS et Android sur un cœur Rust : « presque 80% du code est désormais
partagé ». Le Rust porte TOUTE la logique métier, y compris la
navigation et le scroll infini de la liste des messages.
Taux de crash iOS : 0,12% → 0,05%. Android revenu à sa base de 0,19%.
La même architecture part sur Proton Calendar.
<https://proton.me/blog/next-generation-proton-mail-mobile-apps>

🏆 Mullvad / GotaTun — le vrai RIIR du slide (19 décembre 2025)
Ils remplacent wireguard-go par GotaTun, leur implémentation WireGuard
en Rust, forkée de BoringTun (Cloudflare).
Le chiffre à lâcher : plus de 85% de TOUS les plantages venaient de
wireguard-go. La frontière Rust ↔ Go passe par un FFI, et le runtime Go
est opaque — quand ça casse, pas de stacktrace exploitable.
Après le déploiement Android (2025.10, fin novembre) : taux de plantage
perçu 0,40% → 0,01%, et ZÉRO plantage attribué à GotaTun.
Desktop et iOS en 2026. <https://github.com/mullvad/gotatun>

🏆 Element X — l'exemple libre, à citer ici
Element a réécrit ses clients iOS et Android par-dessus le Matrix Rust
SDK, partagé entre les deux, avec des bindings UniFFI.
Le même SDK fait aussi tourner Fractal (GNOME) et iamb.

🏆 Signal / 1Password — plus ancien et plus limité
C'est le cœur cryptographique qui est en Rust (libsignal), pas toute
l'app. Garder court : c'est de la notoriété, pas l'argument.
