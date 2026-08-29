+++
title= "Quotidien"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>

### Rust au quotidien

<!-- pause -->

#### 🦊 Navigateurs

Firefox, Chrome

<!-- pause -->

#### ☁️ Cloud

<abbr title="Amazon Web Service">AWS</abbr>, Azure, Cloudflare, ...

<!-- pause -->

#### 🐧 OS & Mobile

Linux, Android, Fuchsia, Windows, ...

<!-- pause -->

#### 💻 Outils

[uv](https://github.com/astral-sh/uv), [ruff](https://astral.sh/ruff), [ty](https://astral.sh/blog/ty), [biome](https://biomejs.dev/), [oxlint](https://oxc.rs/), ...

<!-- notes -->

Vous utilisez déjà du code Rust, sans le savoir.

🦊 Navigateurs
- Firefox : Stylo (moteur CSS) et WebRender (compositing GPU).
  ⚠️ Ne PAS dire « Servo » : Servo est un projet indépendant
  (Linux Foundation Europe depuis 2023), ce n'est pas le moteur de Firefox.
- Chrome : Fontations / Skrifa (Rust) remplace FreeType pour les webfonts
  depuis Chrome 133 (février 2025)
  <https://developer.chrome.com/blog/memory-safety-fonts>
  et le décodeur PNG en Rust (crate `image-png`) est l'implémentation
  par défaut depuis M139 (août 2025), desktop ET mobile
  <https://blog.image-rs.org/2026/06/18/png-adoption.html>

☁️ Cloud
- AWS Firecracker : les microVMs qui font tourner Lambda et Fargate
  <https://firecracker-microvm.github.io/>
- AWS Bottlerocket : OS orienté conteneurs
- Cloudflare Pingora : remplace nginx, plus de 1 000 milliards de requêtes/jour
  <https://blog.cloudflare.com/how-we-built-pingora-the-proxy-that-connects-cloudflare-to-the-internet/>

🐧 OS & Mobile
- Linux : la phase « expérimentale » de Rust dans le noyau est TERMINÉE
  (sommet des mainteneurs, Tokyo, décembre 2025). Greg Kroah-Hartman :
  les drivers Rust s'avèrent plus sûrs que leurs équivalents C, et il y a
  eu moins de frictions Rust/C que prévu. Le DRM annonce vouloir exiger
  Rust pour les nouveaux drivers d'ici environ un an.
  <https://lwn.net/Articles/1049831/>
  Documentation officielle : <https://www.kernel.org/doc/html/latest/rust/>
- Android : pile Bluetooth, allocateur ashmem, ...
  Sous les 20% de vulnérabilités mémoire — cf. le slide 1.3
  <https://security.googleblog.com/2024/09/eliminating-memory-safety-vulnerabilities-Android.html>
- Windows : Rust tourne DANS le noyau (win32kbase_rs.sys, DirectWriteCore),
  et la crypto TLS passe par rustls-symcrypt.
  Cf. le keynote RustConf 2025 de Mark Russinovich, lien sur le slide 5.1.

💻 Outils
uv, ruff, ty (Astral), biome, oxlint : l'outillage Python et JS
se réécrit en Rust. Le détail — et l'argument qui tue — sur le slide 4.4.

📊 Ordres de grandeur
- Cloudflare : 160+ pays, plus de 10% du trafic web mondial
- Android : 3+ milliards d'appareils
