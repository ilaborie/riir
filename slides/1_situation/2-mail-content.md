+++
title= "Nouvelle CVE"
classes = ["no_title"]
+++

<style>
.mail {
    font-size: 80%;
    margin: .5em;
    padding: .5em;
    background: white;
    border: thin solid gray;
    border-radius: .5em;
    box-shadow: .1em .1em .2em rgba(0, 0, 0, .8);
}

.mail header {
    display: grid;
    grid-template-columns: 4rem auto;
    grid-template-areas:
        "avatar name"
        "avatar title"
        "avatar to";

    .avatar {
        grid-area: avatar;

        img {
            width: 2em;
            height: 2em;
            border: thin solid rgba(0,0,0,.2);
            border-radius: 50%;
            padding: .125em;
            box-shadow: .1em .1em .2em rgba(0, 0, 0, .8);
        }
    }

    .name {
        grid-area: name;
    }
    .title {
        grid-area: title;
    }
    .to {
        grid-area: to;
    }

}

.toolbar {
    float:right;
    display: flex;
    gap: 1em;

    ul {
        border: thin solid rgba(0,0,0,.2);
        border-radius: .5em;
        padding: 0 .3em;
        display: flex;
        gap: .5em;
        background: #eee;
        box-shadow: .02em .0em rgba(0, 0, 0, .5);
    }
}

.mail .body {
    font-family: Inconsolata Nerd Font Mono, system-ui, -apple-system, sans-serif;
    
    .score {
        color: firebrick;
        font-family: mono;
    }
}
</style>

<div class="mail">
    <div class="toolbar">
        <ul>
            <li title="Reply">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9ImN1cnJlbnRDb2xvciIgc3Ryb2tlLXdpZHRoPSIyIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGNsYXNzPSJsdWNpZGUgbHVjaWRlLXJlcGx5LWljb24gbHVjaWRlLXJlcGx5Ij48cGF0aCBkPSJNMjAgMTh2LTJhNCA0IDAgMCAwLTQtNEg0Ii8+PHBhdGggZD0ibTkgMTctNS01IDUtNSIvPjwvc3ZnPg==">
            <li title="Reply All">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9ImN1cnJlbnRDb2xvciIgc3Ryb2tlLXdpZHRoPSIyIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGNsYXNzPSJsdWNpZGUgbHVjaWRlLXJlcGx5LWFsbC1pY29uIGx1Y2lkZS1yZXBseS1hbGwiPjxwYXRoIGQ9Im0xMiAxNy01LTUgNS01Ii8+PHBhdGggZD0iTTIyIDE4di0yYTQgNCAwIDAgMC00LTRINyIvPjxwYXRoIGQ9Im03IDE3LTUtNSA1LTUiLz48L3N2Zz4=">
            </li>
            <li title="Forward">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9ImN1cnJlbnRDb2xvciIgc3Ryb2tlLXdpZHRoPSIyIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGNsYXNzPSJsdWNpZGUgbHVjaWRlLXJlcGx5LWljb24gbHVjaWRlLXJlcGx5Ij48cGF0aCBkPSJNMjAgMTh2LTJhNCA0IDAgMCAwLTQtNEg0Ii8+PHBhdGggZD0ibTkgMTctNS01IDUtNSIvPjwvc3ZnPg==">
            </li>
        </ul>
        <ul>
            <li title="Archive">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9ImN1cnJlbnRDb2xvciIgc3Ryb2tlLXdpZHRoPSIyIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGNsYXNzPSJsdWNpZGUgbHVjaWRlLWFyY2hpdmUtaWNvbiBsdWNpZGUtYXJjaGl2ZSI+PHJlY3Qgd2lkdGg9IjIwIiBoZWlnaHQ9IjUiIHg9IjIiIHk9IjMiIHJ4PSIxIi8+PHBhdGggZD0iTTQgOHYxMWEyIDIgMCAwIDAgMiAyaDEyYTIgMiAwIDAgMCAyLTJWOCIvPjxwYXRoIGQ9Ik0xMCAxMmg0Ii8+PC9zdmc+">
            </li>
            <li title="Delete">
                <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0IiBmaWxsPSJub25lIiBzdHJva2U9ImN1cnJlbnRDb2xvciIgc3Ryb2tlLXdpZHRoPSIyIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGNsYXNzPSJsdWNpZGUgbHVjaWRlLXRyYXNoLWljb24gbHVjaWRlLXRyYXNoIj48cGF0aCBkPSJNMTkgNnYxNGEyIDIgMCAwIDEtMiAySDdhMiAyIDAgMCAxLTItMlY2Ii8+PHBhdGggZD0iTTMgNmgxOCIvPjxwYXRoIGQ9Ik04IDZWNGEyIDIgMCAwIDEgMi0yaDRhMiAyIDAgMCAxIDIgMnYyIi8+PC9zdmc+">
            </li>
        </ul>
    </div>
    <header>
        <figure class="avatar">
            <img src="https://robohash.org/620050a4db5104bae758cd75171d64ca?set=set4">
        </figure>
        <div class="name"><strong>Rowan O'Wasp</strong> - rssi@my-company.ai</div>
        <div class="title">[URGENT] CVE GDAL</div>
        <div class="to">me@my-company.ai</div>
    </header>
    <hr>
    <div class="body">

Bonjour,<br>

<p>
Suite à notre audit de sécurité régulier et l'analyse de votre <strong>BOM</strong> (Bill of Materials), j'ai identifié que votre projet utilise <strong>GDAL 3.10.x</strong>.
</p>

<p>
Une vulnérabilité <strong>critique</strong> vient d'être publiée :<br><br>

🔴 <strong>CVE-2025-29480</strong> - Score CVSS : <strong class="score">9.8/10</strong><br><br>

- Type : Buffer overflow dans le parser GeoTIFF<br>
- Impact : Exécution de code arbitraire possible<br>
- Exploitation : Active dans la nature<br>
</p>

<p>
<a href="https://nvd.nist.gov/vuln/detail/CVE-2025-29480">Détails CVE</a>
</p>

<p>
⚠️ <strong>Action requise</strong> : Mise à jour urgente ou mitigation
</p>

<p>
Cordialement,<br>
<strong>Rowan O'Wasp</strong> - RSSI
</p>

    </div>

</div>

<!-- notes-->

GDAL dans postgis

FIXME UI

> **Nouvelle notification** **De:** securite-info@entreprise.fr **Objet:** [URGENT] Vulnérabilité critique GDAL - Action requise _Reçu à l'instant_
