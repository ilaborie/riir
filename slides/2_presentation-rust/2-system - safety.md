+++
title= "Programmation système"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>

### Rust Vs langages bas niveaux

<!-- pause -->

#### 🛟 Sécurité mémoire <sup>*</sup>

- Pas de crash mémoire
- Pas de <em>dangling pointers</em>
- Pas de <em>double free</em>
- Pas de <em>use after free</em>

<br>
<p>
<sup>*</sup>: <small>en <em>safe Rust</em></small>
</p>

<!-- pause -->

#### 🧰 Outils

- [cargo](https://doc.rust-lang.org/cargo/), [crates.io](https://crates.io/) : gestion de dépendances
- [rustfmt](https://github.com/rust-lang/rustfmt), [clippy](https://doc.rust-lang.org/clippy/): format & linter
- Mais aussi, [miri](https://github.com/rust-lang/miri), [rustsec](https://rustsec.org/), [cargo-vet](https://mozilla.github.io/cargo-vet/), ...

<!-- notes -->

🧰 Les outils, dans l'ordre de la chaîne :
- miri : interpréteur qui détecte l'UB dans le code `unsafe`
- rustsec / `cargo audit` : les CVE connues de vos dépendances
- cargo-vet (Mozilla) : l'étape d'après — tracer QUI a audité chaque
  dépendance, et mutualiser ces audits entre organisations.
  On revient au mail du début : le RSSI parle de BOM et d'audit.
  cargo-vet, c'est exactement cette réponse-là, intégrée à cargo.
  <https://mozilla.github.io/cargo-vet/>

[2019 - A proactive approach to more secure code](https://msrc.microsoft.com/blog/2019/07/a-proactive-approach-to-more-secure-code/)
[2019 - Implications of Rewriting a Browser Component in Rust](https://hacks.mozilla.org/2019/02/rewriting-a-browser-component-in-rust/)
[Chromium](https://www.chromium.org/Home/chromium-security/memory-safety/)
[2023 - The Urgent Need for Memory Safety in Software Products](https://www.cisa.gov/news-events/news/urgent-need-memory-safety-software-products)

<https://en.wikipedia.org/wiki/Memory_safety>


National Institute of Standards and Technology (NIST)