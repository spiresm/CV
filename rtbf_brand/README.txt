# RTBF Gamification Pack — Placeholders & Branding
Date: 2025-08-24

Ce pack contient des **assets de substitution** (placeholders) pour styliser les mini‑jeux avec un habillage RTBF/Auvio/Viva for Life. Remplacez-les par les logos/images **officiels** dès que possible.

## Contenu
- `rtbf-logo-placeholder.svg`
- `auvio-logo-placeholder.svg`
- `vivaforlife-badge-placeholder.svg`
- `bg-auvio-invaders.svg` (fond pour Auvio Invaders)
- `bg-quiz-info.svg` (fond pour Quiz « Attrape l’info »)
- `bg-cactus.svg` (fond alternatif style Grand Cactus)
- `sprites-auvio.svg` (sprites simples: vaisseau, ennemis, projectiles)
- `branding-rtbf.css` (variables & classes utilitaires)

## Intégration rapide (extraits)
1) **Copiez** le dossier `rtbf_brand/` à la racine de votre projet (même niveau que `index_fixed.html`).

2) **Ajoutez** la feuille de style :
```html
<link rel="stylesheet" href="./rtbf_brand/branding-rtbf.css">
```

3) **Appliquez** les fonds brandés sur les canvas (dans `index_fixed.html`) :
```html
<canvas id="cvGame" class="game-canvas brand-info"></canvas>
<canvas id="auvioGame" class="game-canvas brand-auvio"></canvas>
```

4) **Préchargez** les images dans le JS (optionnel, pour replacement des formes par sprites) :
```js
const assets = {
  logoRTBF: new Image(),
  logoAuvio: new Image(),
  sprite: new Image()
};
assets.logoRTBF.src = './rtbf_brand/rtbf-logo-placeholder.svg';
assets.logoAuvio.src = './rtbf_brand/auvio-logo-placeholder.svg';
assets.sprite.src = './rtbf_brand/sprites-auvio.svg';
```

5) **Remplacez** dans *Auvio Invaders* le rendu du joueur/ennemis/bullets par les sprites (exemple) :
```js
// Au lieu de ctx.fillRect(player.x, player.y, player.w, player.h);
ctx.drawImage(assets.sprite, 16, 200, 84, 40, player.x, player.y, player.w, player.h);
// Pour un ennemi (source sprite: x=140,y=24,w=36,h=24):
ctx.drawImage(assets.sprite, 140, 24, 36, 24, e.x, e.y, e.w, e.h);
// Pour un projectile (source sprite: x=24,y=24,w=4,h=12):
ctx.drawImage(assets.sprite, 24, 24, 4, 12, b.x, b.y, b.w, b.h);
```

6) **Utilisez** les logos placeholders là où nécessaire dans les cartes/headers :
```html
<img src="./rtbf_brand/rtbf-logo-placeholder.svg" alt="RTBF" width="40" height="40"/>
```

> ⚠️ **Remplacez** ces placeholders par les **logos et images RTBF officiels** une fois validés (respect des chartes et droits).
