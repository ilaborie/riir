+++
title = "Diagram 2"
classes = ["no_title"]
style = "margin-top: 0; min-height: 100%; width: 100%;"
+++

<style>
/* The diagram is a raster wider than the slide box on anything below 1920px,
   so it has to be contained rather than cropped by `section { overflow: hidden }`.
   `flex: 1 1 0` + `min-height: 0` give the figure a definite height for the
   image's `max-height: 100%` to resolve against. */
article {
    min-height: 0;
}

figure {
    display: flex;
    flex: 1 1 0;
    min-height: 0;
    align-items: center;
    justify-content: center;
    margin: 0;
    padding: 0 3rem;
}

figure img {
    max-width: 100%;
    max-height: 100%;
    object-fit: contain;
}
</style>

<figure>
    <img alt="Toboggan" src="public/diagram2.webp">
</figure>
