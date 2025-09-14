+++
title = "Me"
classes = ["no_title"]
style = "margin: 1rem 1rem 0; width: calc(100% - 2rem); min-height: calc(100% - 2rem);"
+++

<style>
h3 {
    flex: 0 0 auto;
}
.auto-carousel {
    animation: 15s infinite carousel;
    display: flex;
    width: 100%;
    flex: 1 1 auto;
    box-shadow: 1px 1px .5em rgba(0,0,0,.5);
    margin: .5em;
    width: calc(100% - 7em);
    margin: 1em 3em 3em 3em;
}

@keyframes carousel {
    from {
        background: url('public/d1.webp');
        background-size: cover;
    }
    25% {
        background: url('public/d2.webp');
        background-size: cover;
    }
    50% {
        background: url('public/d3.webp');
        background-size: cover;
    }
    75% {
        background: url('public/d4.webp');
        background-size: cover;
    }
    100% {
        background: url('public/d5.webp');
        background-size: cover;
    }
}
</style>

### <strong>Igor Laborie</strong><br>Founding Engineer @ [Darwin Data](https://www.darwindata.ai/)

<div class="auto-carousel"></div>

<!-- Notes -->

Darwin: mesure l'impact sur la biodiv des entreprises.

TODO: Video darwin.

Rust daily - c'est possible

Backend, CLI, Uniffi, WASM
