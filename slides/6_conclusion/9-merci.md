+++
title = "Citation"
classes = ["no_title", "slide-end"]

style = """
margin-top: 0;
min-height: 100%;
width: 100%;
overflow: hidden;
background-image:
    url(./public/items/forme7.svg),
    url(./public/items/animal_meduse.svg)
    ;
background-position:
    107% -40%,
    7% 27%
    ;
background-size:
    30vw,
    15vw
    ;
background-repeat:
    no-repeat,
    no-repeat
    ;
"""
+++

<style>
.slide-end article {
  padding-top: 2em;
  justify-content: center;
  gap: 2em;
}

.quote {
    display: flex;
    flex-direction: column;
    max-width: 60vw;
    margin: 0 auto;
    text-shadow: 1px 1px white;
}

blockquote {
  --icon-open: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 60 60"><rect width="100%" height="100%" fill="yellow" fill-opacity="0" /><text y=".8em" font-size="90" fill="rgba(104, 170, 175, 1)" fill-opacity=".2">❝</text></svg>');
  --color: currentColor;
  float: inline-end;
  margin-inline: 1em -3em;
  margin-block-start: -1rem;
  text-wrap: balance;
  font-family: var(--font-sans);
  hyphens: manual;
  color: oklab(from var(--color) clamp(0, l, 0.52) a b);
  background: var(--icon-open) no-repeat 0 0 / auto min(8em, 80%);
  font-weight: 500;
  &:hover {
    --color: var(--color-accent);
  }

  p {
    font-size: 200%;
    line-height: 1.5;
    margin-block: .2em 1em;
    margin: 0;
  }
  cite {
    font-weight: 500;
  }
}

.step-0 {
  display: flex;
flex-direction: column;
}

.table {
  display: grid;
  justify-content: center;
  grid-template-columns: 1fr 1fr;
  gap: 2em;
  justify-items: center;

  .links {
    display: flex;
    flex-direction: column;
    align-self: center;
  }

  img {
    height: 25vh;
  }
}

</style>

<div class="quote">
  <blockquote>
    <p>Soyez donc résolus à ne plus<br> servir et vous serez libres.</p>
    <footer>
      — Étienne de La Boétie
      - <cite>Discours de la servitude volontaire (1576)</cite>
    </footer>
  </blockquote>
</div>

<div class="table">
  <div class="links">
    <a href="https://github.com/ilaborie/riir">Source Slides</a>
    <a href="https://github.com/ilaborie/toboggan">Source Toboggan</a>
    <a href="https://github.com/ilaborie/toboggan-esp32">Source Toboggan ESP32</a>
  </div>
  <div>
    <img src="./public/qr-code.svg" alt="https://openfeedback.io/devfest-toulouse-2025/2025-11-13/949153">
  </div>
</div>

<!-- notes -->
