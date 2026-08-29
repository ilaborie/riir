+++
title = "Python"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>

### 🐍 Interopérabilité avec Python

<!-- pause -->

#### 📦 Crates

- [PyO3](https://pyo3.rs/): bindings Rust ↔ Python
- [Maturin](https://www.maturin.rs/) : packaging

<!-- pause -->

#### 🏆 Champions

- [Polars](https://pola.rs/), [datafusion](https://datafusion.apache.org/): big data
- [Pydantic](https://docs.pydantic.dev/latest/): validation des données
- [tokenizers](https://github.com/huggingface/tokenizers): ML Tokenizers
- [orjson](https://github.com/ijl/orjson): JSON
- ...

<!-- pause -->

#### 🛠️ Et l'outillage aussi

[uv](https://github.com/astral-sh/uv), [ruff](https://astral.sh/ruff), [ty](https://astral.sh/blog/ty) — [Astral a rejoint OpenAI](https://astral.sh/blog/openai) en mars 2026

<!-- notes -->

Exemples : calculs intensifs, parsing, crypto, compression, etc.

📦 Le motif : « API Python, moteur Rust »
Polars, Pydantic v2, tokenizers, orjson : dans chaque cas
l'interface reste 100% Python, seul le cœur change de langage.
C'est exactement le RIIR ciblé du slide 5.3, appliqué à Python.
Personne n'a réécrit Python.

🛠️ L'argument qui clôt le débat
uv remplace pip + pip-tools + virtualenv + pipx en un seul binaire.
ruff remplace flake8 + isort + black. ty est le type-checker.
Et le 19 mars 2026, Astral a annoncé rejoindre OpenAI,
au sein de l'équipe Codex. <https://astral.sh/blog/openai>
Quand l'outillage Rust d'un écosystème devient une acquisition
stratégique, ce n'est plus un pari technique.

🧵 Bonus si on demande « et le GIL ? »
PyO3 supporte le Python free-threaded (PEP 703, Python 3.13+).
<https://pyo3.rs/latest/free-threading.html>
Le sans-GIL rend justement le parallélisme natif intéressant —
et Rust garantit l'absence de data race à la compilation.
