+++
title= "Quotidien"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  margin-bottom: 2em;
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

Linux, Android, Fushia, Windows, ...

<!-- pause -->

#### 💻 Outils

uv, ruff, biome, oxlint, ...

<!-- notes -->

Vous utilisez déjà du code Rust

Production usage détaillé par grandes entreprises :

**Navigateurs & Desktop :**
- Firefox : Servo engine (nouvelle génération), WebRender GPU, CSS parser Stylo
  Gains performance 2-4x vs C++ équivalent
- Chrome/Google : Fuchsia OS (nouveau système), composants sécurité critiques Temopral
- Microsoft VS Code : ripgrep pour recherche fichiers
  10x+ plus rapide que grep traditionnel

**Cloud Infrastructure (Critical Systems) :**
- AWS Firecracker : microVMs pour Lambda, Fargate
  Performance + sécurité isolation containers
- AWS Bottlerocket : OS optimisé containers
- Cloudflare Pingora : remplace nginx/apache
  Traite 1+ trillion requests/jour
- Google Cloud : composants Fuchsia, cargo-gn build

**Mobile & Operating Systems :**
- Android AOSP : Bluetooth stack réécrit 2022-2023
  Sécurité memory-safe pour composants critiques
- Linux kernel : modules Rust officiels depuis 6.1
  Drivers réseau, filesystems experimentaux
- Windows : Win32 bindings, Azure backend services

**Package Managers & DevTools :**
- npm Inc : authentication microservice en production
  Performance critical user auth
- GitHub : git operations, repository management
  Performance sur scale massive
- Docker Inc : BuildKit components, registry backend

- **Docker** : BuildKit, registry components

**Métriques Impact :**
- Cloudflare : 160+ pays, 10%+ traffic internet mondial
- Android : 3+ milliards devices
- Linux kernel : infrastructure mondiale

Sources officielles :
- [Cloudflare Pingora Blog](https://blog.cloudflare.com/how-we-built-pingora-the-proxy-that-connects-cloudflare-to-the-internet/)
- [Android Rust Blog](https://android-developers.googleblog.com/2023/02/improving-android-interaction-with-hearing-aids.html)
- [Linux Kernel Rust](https://www.kernel.org/doc/html/latest/rust/)
- [AWS Firecracker](https://firecracker-microvm.github.io/)
- [GitHub Engineering](https://github.blog/2023-03-09-how-github-uses-rust-to-deliver-better-performance/)