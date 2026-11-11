+++
title = "CLI"
classes = ["no_title"]
+++

<style>
article {
  /* dégage les décorations du footer, qui débordent au-dessus de la barre */
  margin-bottom: 3em;
}
</style>

### Outils <abbr title="Command Line Interface">CLI</abbr>

📖 [Command line apps in Rust](https://rust-cli.github.io/book/index.html)

<!-- pause -->

#### 📦 Crates

- Arguments: [clap](https://github.com/clap-rs/clap), [argh](https://github.com/google/argh), [pico-args](https://github.com/razrfalcon/pico-args), ... [benchmark](https://github.com/rosetta-rs/argparse-rosetta-rs)
- Prompt: [dialoguer](https://github.com/console-rs/dialoguer), [inquire](https://github.com/mikaelmello/inquire), [demand](https://github.com/jdx/demand), ...
- [comfy-table](https://github.com/nukesor/comfy-table), [indicatif](https://github.com/console-rs/indicatif), [spinners](https://github.com/fgribreau/spinners), [owo-colors](https://github.com/owo-colors/owo-colors), ...

<!-- pause -->

#### 🏆 Champions

- [ripgrep (rg)](https://github.com/BurntSushi/ripgrep): remplace `grep`
- [fd](https://github.com/sharkdp/fd): remplace `find`, plus rapide
- [bat](https://github.com/sharkdp/bat) : `cat` avec des ailes
- [eza](https://github.com/eza-community/eza), [lsd](https://github.com/lsd-rs/lsd) : `ls` moderne
- [starship](https://starship.rs/) : prompt shell personnalisable
- [mise](https://mise.jdx.dev/) : versions d'outils &amp; tâches
- [hyperfine](https://github.com/sharkdp/hyperfine) : benchmark de commandes
- ...

<!-- notes -->

Avantages
- Compilation vers binaire statique (pas de dépendances)
- Très rapide à l'exécution
- Gestion d'erreurs robuste
- Cross-platform facilement