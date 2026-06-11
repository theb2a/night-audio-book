# Guide Rapide — Modifications dans Claude Code

## 🎬 Démarrer

1. **Ouvre le fichier** `livre-histoires.html` dans Claude Code
2. **Clique sur Preview** (œil en haut à droite)
3. **Modifie** → la prévisualisation se met à jour automatiquement

---

## ✏️ Modifications super rapides

### ▶ Changer le prénom du personnage
Cherche-remplacer (Ctrl+H) :
- `Steve` → `Maxime` (ou le prénom de l'enfant)
- Et le livre entier change !

### ▶ Ajouter une histoire
Dans l'array `STORIES`, ajoute avant la dernière `}` :
```javascript
{cat:'fun',scene:'cow',title:'Le titre de ma nouvelle histoire',text:[
  "Première phrase du soir.",
  "Deuxième phrase.",
  "Troisième phrase.",
  "Et voilà c'est fini."
]},
```

**Catégories :** `'hero'` (héros), `'fun'` (drôle), `'manners'` (manières), `'family'` (famille)

**Scènes disponibles :** steve, creeper, noobi, goku, team, diamond, sheep, cow, star, hiccup, socks, dance, villager, heart, night, table, slide

### ▶ Changer les couleurs
En haut du CSS, dans `:root{ ... }` :
```css
--night-1: #1a1147;    /* couleur de fond sombre */
--lamp: #ffd27a;       /* accent doré */
--cat-hero: #ff8a3d;   /* couleur des histoires de héros */
--cat-fun: #ffcf3d;
--cat-manners: #5bd0e8;
--cat-family: #ff7a9c;
```

### ▶ Changer le titre du livre
Cherche `<h1>Le Grand Livre des Histoires du Soir</h1>` et remplace.

---

## 🎨 Ajouter une nouvelle scène SVG

Dans le dictionnaire `SCENES`, ajoute :
```javascript
monScene(){return `<svg viewBox="0 0 200 200">
  <g class="a-float">
    <rect x="50" y="50" width="100" height="100" fill="#ff0000"/>
  </g>
</svg>`;},
```

**Classes d'animation disponibles :**
- `.a-float` — monte et descend doucement
- `.a-bob` — sautille
- `.a-pulse` — grandit et rétrécit
- `.a-spin` — tourne continuellement
- `.a-spark` — clignote
- `.a-sway` — se balance
- `.a-bounce` — rebondit
- `.a-shoot` — s'envole et disparaît
- `.a-hue` — change de couleur

Tu peux combiner : `<g class="a-float a-spin">` = tourne en flottant.

---

## 🔊 Ajouter de l'audio (optionnel)

Pour faire lire l'histoire à voix haute, dans `storyHTML()`, avant le `</div>` final :
```javascript
<button onclick="speak('${s.text.join('. ')}')" style="margin-top:10px;padding:8px 14px;background:#ffd27a;border:none;border-radius:8px;cursor:pointer;font-weight:700;">🔊 Lire à voix haute</button>
```

Et ajoute avant `</script>` :
```javascript
function speak(txt){
  const utterance = new SpeechSynthesisUtterance(txt);
  utterance.lang = 'fr-FR';
  utterance.rate = 0.8;
  window.speechSynthesis.speak(utterance);
}
```

---

## 💾 Sauvegarder la progression

Pour que le lecteur reprenne où il s'était arrêté, après `let idx=COVER;` ajoute :
```javascript
// Charger la page sauvegardée
idx = parseInt(localStorage.getItem('bookIdx') || '-1');

// Sauvegarder à chaque changement (dans la fonction turn)
localStorage.setItem('bookIdx', idx);
```

---

## 📱 Test mobile dans Claude Code

**Sans appareil réel :**
- Zoom out sur Desktop (Ctrl+Minus)
- Ouvre DevTools (F12) → device toolbar (Ctrl+Shift+M)
- Simule iPhone / Pixel 5

**Avec appareil réel :**
- Dans Claude Code, cherche "Local URL" ou "Preview URL"
- Partage l'URL (souvent `http://192.168.x.x:PORT`)
- Ouvre sur ton téléphone = test réel

---

## 🎯 Exemples de modifs faciles

### Ajouter un minuteur (30 min puis dodo)
```javascript
setTimeout(()=>{
  alert('Bonne nuit ! 🌙');
  document.body.innerHTML = '<p style="text-align:center;padding:40px;">À demain !</p>';
},30*60*1000);
```

### Changer le message du soir
Cherche `Bonne nuit 🌙` et remplace par ton message.

### Rendre le texto encore plus gros pour les petits yeux
```css
.story-text{font-size: clamp(17px, 4.2vw, 20px);}
```

---

## 🐛 Déboguer dans Claude Code

**Console erreurs :** DevTools (F12) → Console
**Vérifier le HTML :** DevTools → Elements
**Tester les animations :** Ajoute `animation-duration: 0.3s !important;` au CSS pour accélérer

---

## 📦 Exporter / Imprimer

**Imprimer le PDF :**
- Ctrl+P → Enregistrer sous PDF
- Couvre environ 5 pages pour toutes les histoires

**Convertir en EPUB (pour liseuse) :**
- Utilise un outil en ligne comme `pandoc` ou `Calibre`
- Ou demande à Claude de générer un EPUB

---

## ❓ Besoin d'aide dans Claude Code ?

Pose la question dans la conversation et Claude Code te donnera les changements exacts avec avant/après. Par ex :
- "Fais une animation de pluie pendant la nuit"
- "Ajoute un bouton pour changer de langue"
- "Mets des stickers emoji entre chaque phrase"

Claude Code c'est fait pour ça. Allez-y ! 🚀
