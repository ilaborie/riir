+++
title = "RIIR ou ne pas RIIR?"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
  margin-bottom: 2em;
}
</style>

### RIIR ou ne pas RIIR?

<!-- pause -->

#### 💰 Quel <abbr title="Return On Investment">ROI</abbr> ?

<div class="two-columns" style="margin-top: 1em;">

<div>
    <header class="block" style="--bg: var(--color-success); --fg: white;">👍 Oui</header>
    <div>si pas de compromis sur</div>
    <ul>
        <li>la sécurité</li>
        <li>la performance</li>
        <li>l'efficacité</li>
    </ul>
</div>

<div>
    <header class="block" style="--bg: var(--color-error); --fg: white;">👎 Non</header>
    <div>si</div>
    <ul>
        <li>pas de problèmes</li>
        <li>pas le temps de réécrire</li>
        <li>pas les compétences</li>
    </ul>
</div>

</div>

<!-- pause -->

#### 🎯 Stratégie

- Intégrer Rust dans les <abbr title="Continuous Integration">CI</abbr>/<abbr title="Continuous Deployement">CD</abbr>
- Former progressivement les équipes
- Commencer petit

<!-- notes -->
Context entreprise.

sécurité: rustls remplace OpenSSL Microsoft
performances: Discord, Figma success stories
Migration progressive possible : Firefox l'a prouvé partie par partie

[Mark Russinovich: "From Blue Screens to Orange Crabs: Microsoft’s Rusty Revolution" | RustConf 2025](https://www.youtube.com/watch?v=uDtMuS7BExE)
[Lars Bergstrom - Beyond Safety and Speed: How Rust Fuels Team Productivity](https://www.youtube.com/watch?v=QrrH2lcl9ew)
