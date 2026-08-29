+++
title = "CVE-2026-4738"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>

### `CVE-2026-4738`

<!-- pause -->

💥 **Buffer Overflow**: Gestion mémoire défaillante

<small>dans le zlib embarqué de GDAL, pas dans son code géospatial</small>

<!-- pause -->

📊 **~70%** des CVEs critiques: problème mémoire

- [Microsoft: Proactive Approach to Secure Code](https://msrc.microsoft.com/blog/2019/07/a-proactive-approach-to-more-secure-code/)
- [Mozilla: Rewriting Browser Component in Rust](https://hacks.mozilla.org/2019/02/rewriting-a-browser-component-in-rust/)
- [Chromium Memory Safety](https://www.chromium.org/Home/chromium-security/memory-safety/)
- [CISA: Need for Memory Safety](https://www.cisa.gov/news-events/news/urgent-need-memory-safety-software-products)

<!-- pause -->

📉 Android: **76% → 24%** en 6 ans, **< 20%** en 2025

- [Rust in Android: move fast and fix things](https://blog.google/security/rust-in-android-move-fast-fix-things/)

<!-- pause -->

**💭 Et si on pouvait éviter ça ?**

