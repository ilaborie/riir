+++
title= "GitHub issue"
classes = ["no_title"]
+++

<style>
.gh-issue {
  font-size: 80%;
  padding: 0.25em .5em;
  background-color: white;
  color: rgb(31, 35, 40);
}
.gh-issue header h2, .gh-issue h3 {
  text-align: left;
  font-family: var(--font-slide-body);
  padding-top: .25em;
}

.gh-issue > header {
  .tools {
    display: flex;
    justify-content: space-between;

    button {
      display: flex;
      align-items: center;
      gap: .5em;
      border-radius: 2em;

      border:none;
      color: white;
      background: rgb(31, 136, 61);
      font-weight: bold;
      padding: .25em .75em;
      margin: .25em;
      font-size: .5rem;

      /* The inline SVG carries a 24px intrinsic size, which would stay 24px at
         every resolution — size it against the text instead. */
      img {
        width: 1.5em;
        height: 1.5em;
      }
    }
  }
  h2 {
      font-size: 150%;
      display: flex;
      justify-content: space-between;
  }
}
hr {
  opacity: .6;
  margin: .5em;
}

.gh-issue .body {
  display: flex;
  gap: 1em;
  font-size: 80%;
}

.body figure {
  margin: 0;
}
.body img {
  width: 2em;
  height: 2em;
  border: 1px solid rgba(0,0,0,.2);
  border-radius: 50%;
  box-shadow: .1em .1em .1em rgba(0, 0, 0, .5);
}

.body ul {
  list-style: disc;
  margin: .5em 0;
  /* The slide stylesheet zeroes list padding; put back enough for the markers to
     sit inside the card. 1.25rem is the 40px browsers use, on the deck canvas. */
  padding-inline-start: 1.25rem;
}

.card {
  border: 1px solid #54aeff66;
  border-radius: .5em;
  font-size: 90%;
}
.card header {
  background: rgb(221, 244, 255);
  border-bottom: thin solid #54aeff66;
  display: flex;
  gap: 1em;
  padding: .25em .75em;
  border-top-left-radius: .5em;
  border-top-right-radius: .5em;
}


.card-body {
  padding: .25em .75em;
  h3 {
    font-size: 110%; 
  }
}
.labels {
  display: flex;
  gap: 1em;
  font-size: 70%;
}
.labels > * {
  border-radius: 2em;
  color: white;
  font-weight: bold;
  padding: .25em .75em;
  display: flex;
  align-items: center;
  margin: .25em;
}
.labels .security {
  background: magenta;
}
.labels .first {
  background: purple;
}
.labels .help {
  background: forestgreen;
}

.create-at, .gh-id {
  color: rgb(89, 99, 110);
  margin: 0 1em;
}
</style>

<div class="gh-issue">
  <header>
    <h2>Critical vulnerability CVE-2026-4738<span class="gh-id">#42</span></h2>
    <div class="tools">
      <button>
          <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9IiNmZWZmZmYiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBjbGFzcz0ibHVjaWRlIGx1Y2lkZS1jaXJjbGUtZG90LWljb24gbHVjaWRlLWNpcmNsZS1kb3QiPjxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjEwIi8+PGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iMSIvPjwvc3ZnPg==">
          Open
      </button>
      <div class="labels">
        <div class="security">Security</div>
        <div class="first">Good first issue</div>
        <div class="help">Need help</div>
      </div>
    </div>
  </header>
  <hr>
  <div class="body">
    <figure>
        <img src="./public/avatar-ilovecrab.jpg">
    </figure>
    <div class="card">
      <header>
        <strong>ilovecrab</strong>
        <span class="create-at">opened 2 months ago</span>
      </header>
      <div class="card-body">
        <p>Consider migrating from GDAL to "safer" language</p>
        <h3>Description</h3>
        <hr>
        <p>Given the recent <a href="https://www.cve.org/CVERecord?id=CVE-2026-4738">CVE-2026-4738</a> critical vulnerability in GDAL (CVSS 9.4), I believe we should seriously consider migrating to a Rust-based alternative or another "safer" language.
        </p>
        <h3>Problem</h3>
        <hr>
        <ul>
          <li>Recurring memory safety issues in GDAL and its vendored C dependencies</li>
          <li>Complex dependency management</li>
        </ul>
        <h3>Proposed solution</h3>
        <hr>
        <p>Use existing crates referenced in <a href="https://georust.org/">GeoRust</a>, and add create missing one.</p>
        <h3>Benefits</h3>
        <hr>
        <p>✅ Memory safety by design<br>✅ Better performance (no GC)<br>✅ Simpler deployment</p>
        <p>🤔 Thoughts?</p>
      </div>
    </div>
  </div>
</div>

<!-- notes -->

Expliquer le contexte : vous devez créer une issue GitHub pour signaler la vulnérabilité et demander une correction. Cela illustre le processus habituel quand on trouve un problème de sécurité dans une librairie C/C++.
