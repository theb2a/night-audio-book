# Le Grand Livre des Histoires du Soir
## Projet interactif pour enfant 6 ans

**État actuel :** ✅ Complet avec 31 histoires (11 héros, 5 drôles, 8 manières, 7 famille)

---

## 🎯 Idées de continuation possibles

### Modifications du contenu
- [x] **Amine, héros du livre** — 6 histoires où Amine est le héros, avec figure SVG réutilisable `amineHero()` et scènes `amine`, `amineStar`, `amineFly`, `amineShield`, `amineNight`, `amineHeart`
- [x] **Narration audio** — contrôles « 🔊 Écouter / ⏸️ Pause ⇄ ▶️ Reprendre / ⏹️ Arrêter » + synthèse vocale `SpeechSynthesis` (fr-FR, débit 0.85), reprise là où on s'est arrêté
- [ ] **Réduire à 20 histoires** (garder les plus drôles/touchantes)
- [ ] **Personnaliser davantage** (remplacer Steve/Noobi/Goku par les vrais amis d'Amine)
- [ ] **Créer des histoires personnalisées** avec les vrais amis/famille de l'enfant
- [ ] **Illustration pour chaque histoire** (générer avec Firefly ou Dall-E)

### Fonctionnalités à ajouter
- [ ] **Mode sombre auto** (basé sur l'heure du coucher)
- [ ] **Minuteur d'endormissement** (lire 3 histoires puis tout s'éteint progressivement)
- [ ] **Progression sauvegardée** (reprendre où on s'était arrêté)
- [ ] **Sons ambiants** (musique douce, bruit de nature)
- [ ] **Partage avec les parents** (QR code, cloud sync)
- [ ] **Avis réactions** (émojis "trop drôle", "trop mignon", "tristounet")
- [ ] **Créateur d'histoires** (formulaire pour ajouter ses propres histoires)

### Design & animation
- [ ] **Thème personnalisé** (couleurs préférées de l'enfant)
- [ ] **Plus d'animations** (pluie, neige, étoiles filantes)
- [ ] **Effets sonores** pour les actions (bruit de page qui tourne, etc.)
- [ ] **Version mobile optimisée** (écran vertical)
- [ ] **Mode dyslexie** (police spéciale, interlettrage)

### Technique
- [ ] **Export PDF** (imprimer le livre)
- [ ] **Conversion en EPUB** (liseuse)
- [ ] **Progressive Web App** (installer sur téléphone)
- [ ] **Synchronisation multi-appareils** (lire sur tablette, continuer sur ordi)
- [ ] **Analytics légères** (quelle histoire préférée sans data sensible)

---

## 🔧 Structure du code

**main HTML :**
- `coverHTML()` — couverture avec bouton "Commencer"
- `storyHTML(i)` — génère une page d'histoire (titre, illustration, texte)
- `SCENES` — dictionnaire des SVG animés (14 scènes)
- `STORIES` — tableau de 25 objets {cat, scene, title, text}
- Navigation par flèches, swipe tactile, sommaire cliquable

**Styles importants :**
- `@keyframes` — animations (float, bob, pulse, spin, spark, etc.)
- `var(--night-1/2/3)` — palette nuit
- `var(--hero/fun/manners/family)` — couleurs des catégories
- 40 étoiles dynamiques avec twinkling

---

## 📝 Comment modifier rapidement

### Ajouter une histoire
```javascript
{cat:'fun',scene:'hiccup',title:'Mon titre',text:[
  "Première phrase.",
  "Deuxième phrase.",
  "Etc."
]}
```

### Ajouter une scène SVG
```javascript
myScene(){return `<svg viewBox="0 0 200 200">
  <g class="a-float">
    <!-- ton SVG ici -->
  </g>
</svg>`;},
```

### Changer les couleurs
```css
:root{
  --night-1:#1a1147;  /* fond sombre */
  --lamp:#ffd27a;     /* teinte or */
  --cat-fun:#ffcf3d;  /* couleur bouton drôle */
}
```

---

## 🚀 Pour continuer dans Claude Code

1. Ouvre ce dossier dans Claude Code
2. Modifie `livre-histoires.html` directement
3. Le navigateur intégré te montrera les changements en temps réel
4. Test mobile : zoom out sur desktop, ou vrai téléphone en réseau local

**Commandes utiles :**
- Cmd/Ctrl + S : sauvegarde auto
- Chercher-remplacer : Cmd/Ctrl + H (pour changer tous les noms)
- Preview : bouton œil en haut à droite de l'éditeur

---

## ✨ Notes sur les illustrations

Chaque SVG a une classe d'animation (`.a-float`, `.a-bob`, `.a-pulse`, etc.)

**Les 14 scènes actuelles :**
1. steve — flootte avec diamant brillant
2. creeper — sautille avec texture
3. noobi — flotte avec carré rouge tournant
4. goku — pulse avec aura dorée
5. team — trois persos avec spark central
6. diamond — pulse + scintille
7. sheep — arc-en-ciel animé
8. cow — rebondit dans foin
9. star — tombe + pulse
10. hiccup — rebond "boing"
11. socks — pulse avec chaussettes qui bougent
12. dance — sway avec notes de musique
13. villager — float avec cœur
14. heart — grosse pulse
15. night — lune + étoiles
16. table — float avec manger
17. slide — float + enfant glisse

Les animations se superposent avec `animation-delay` pour un rendu vivant.

---

## 📱 Testé sur

✅ Desktop (Chrome, Firefox, Safari)  
✅ Tablette (iPad, Android)  
✅ Mobile vertical/horizontal  
✅ Ralenti pour animations (reduced-motion respecté)

---

**Dernière modif :** juin 2026  
**Prêt pour :** embellissements, perso, audio, PDF export, PWA
