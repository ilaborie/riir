+++
title = "Interop"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>

### Rust & autres écosystèmes

<!-- pause -->

- **C**: via [FFI](https://doc.rust-lang.org/nomicon/ffi.html)
- **C++**: [cxx](https://cxx.rs/), [zngur](https://hkalbasi.github.io/zngur/), [crubit](https://github.com/google/crubit)

<!-- pause -->

- **Web**: via Web Assembly
- **Swift** & **Kotlin**: via [UniFFI](https://mozilla.github.io/uniffi-rs/latest/)

<!-- pause -->

- **NodeJS**: [neon](https://neon-rs.dev/), [napi](https://napi.rs/), [Deno](https://deno.com/)
- **JVM**: [FFM API](https://akilmohideen.github.io/java-rust-bindings-manual/title.html) (finale depuis Java 22), [jni](https://github.com/jni-rs/jni-rs), [robusta](https://github.com/giovanniberti/robusta)
- **Ruby**: [magnus](https://github.com/matsadler/magnus)

<!-- notes -->

L'interop, c'est ce qui rend le RIIR progressif possible :
on ne remplace pas l'application, on remplace un composant
derrière une interface stable.

JVM : la Foreign Function & Memory API (projet Panama) est FINALE
depuis Java 22, et donc disponible sur la LTS Java 25.
Plus besoin de JNI ni de code natif de collage : `jextract` génère
les liaisons depuis les en-têtes C, donc depuis n'importe quelle
bibliothèque Rust exposée en `extern "C"`.

C++ : cxx pour du bidirectionnel typé, crubit (Google) pour
l'interop à grande échelle, zngur pour appeler du Rust générique
depuis C++.
