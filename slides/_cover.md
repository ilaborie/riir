+++
title = "Peut-on RIIR de tout ?"
classes = ["no_title"]
style = """
margin-top: 0;
min-height: 100%;
width: 100%;
overflow: hidden;
background-image:
    url(./public/items/forme7.svg),
    url(./public/items/forme9.svg),
    url(./public/items/animal_meduse.svg),
    url(./public/items/forme6.svg),
    url(./public/items/forme6.svg),
    url(./public/items/forme8.svg),
    url(./public/items/forme8.svg),
    url(./public/items/forme8.svg),
    url(./public/items/forme8.svg)
    ;
background-position:
    103% -30%,
    -4% 0%,
    101% 45%,
    65% 1%,
    5% 40%,
    67% 53%,
    69% 50%,
    65% 27%,
    51% 13%
    ;
background-size:
    18rem,
    30rem,
    7.8rem,
    9rem,
    7.2rem,
    2.1rem,
    1.5rem,
    2.4rem,
    1.2rem
    ;
background-repeat:
    no-repeat,
    no-repeat,
    no-repeat,
    no-repeat,
    no-repeat,
    no-repeat,
    no-repeat,
    no-repeat,
    no-repeat
    ;
"""
+++

<style>

h1 {
    font-size: 300%;
    padding-top: 2em;
    width: 100%;
    text-align: left;
}

section.cover, section.center {
  & article {
    justify-content: center;
    align-items: center;
    align-self: start;
    margin-left: 3em;
    width: calc(100% - 3em);
  }
}

/* Chrome's UA margin for `figure` is a fixed 40px, which alone would not follow
   the deck's viewport scale (see public/style.css); 1.25rem is that same 40px on
   the 1920x1080 canvas. */
figure {
    margin-inline: 1.25rem;
}

.crab {
    width: 18rem;
    position: absolute;
    bottom: -1.35rem;
    right: -1.2rem;
    transform: rotate(-.05turn);
}

.shell1 {
    width: 6rem;
    position: absolute;
    bottom: 5.4rem;
    right: 14.4rem;
    transform: rotate(.05turn);
}

.shell2 {
    width: 6rem;
    position: absolute;
    bottom: 7.425rem;
    right: 7.2rem;
    transform: rotate(-0.08turn);
}

.shrimp {
    width: 7.2rem;
    position: absolute;
    top: 8.775rem;
    right: 16.2rem;
    transform: rotate(-0.05turn);
}

</style>

# Peut-on <abbr title="Rewrite It In Rust">RIIR</abbr> de tout ?


<figure class="crab">
    <img src="./public/items/animal_crabe.svg">
</figure>

<figure class="shell1">
    <img src="./public/items/coquillage1.svg">
</figure>

<figure class="shell2">
    <img src="./public/items/coquillage2.svg">
</figure>

<figure class="shrimp">
    <img src="./public/items/animal_crevette.svg">
</figure>
