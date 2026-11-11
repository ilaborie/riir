+++
title = "Et notre CVE ?"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}

.punchline {
  font-size: 150%;
  display: flex;
  justify-content: center;
  text-align: center;
}
</style>

### 🗺️ Et notre CVE GDAL ?

<!-- pause -->

#### ❌ Non, on ne réécrit pas GDAL

- C++, 200+ formats, 25 ans de corrections de bugs

<!-- pause -->

### Des solutions

- Utiliser une nouvelle version de `zlib`
- Sandoxer les appels
- Remplacer par [zlib-rs](https://trifectatech.org/blog/zlib-rs-is-faster-than-c/) : <span lang="en">memory-safe</span>, et plus rapide que la version C

<!-- pause -->

Des crates alternatives à GDAL en Rust: [GeoRust](https://georust.org/)

<!-- pause -->

<div class="punchline">
    <strong>On n'a pas besoin de RIIR de tout.<br>Il faut RIIR ce qui compte.</strong>
</div>

<!-- notes -->
