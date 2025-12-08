# Exemples de Commentaires pour HTML et CSS

## 📌 COMMENTAIRES HTML

### ✅ BON : Sections principales

```html
<!-- ==================== HEADER ==================== -->
<header class="header">
  <!-- Logo et marque -->
  <div class="logo">
    <img src="logo.png" alt="Aegis Bank" />
  </div>

  <!-- Navigation principale -->
  <nav class="navbar">
    <a href="#accueil">Accueil</a>
    <a href="#produits">Produits</a>
  </nav>
</header>

<!-- ==================== CONTENU PRINCIPAL ==================== -->
<main class="main-content">
  <!-- Section héro avec appel à l'action -->
  <section class="hero">
    <h1>Bienvenue</h1>
    <p>Description du service</p>
  </section>

  <!-- Carte offre promotionnelle -->
  <section class="offers">
    <div class="card-container">
      <p>Offre spéciale</p>
    </div>
  </section>
</main>

<!-- ==================== FOOTER ==================== -->
<footer class="footer">
  <!-- Liens légaux -->
  <p>CGU | Confidentialité</p>
</footer>
```

### ✅ BON : Commentaires courts sur éléments spécifiques

```html
<!-- Bouton d'action principal -->
<a class="btn-primary" href="#contact">Commencer</a>

<!-- Menu burger pour mobile (non visible sur desktop) -->
<button class="burger-menu" aria-label="Menu">
  <span></span>
  <span></span>
  <span></span>
</button>

<!-- Formulaire de contact avec validation -->
<form class="contact-form" id="contactForm">
  <input type="email" required placeholder="Email" />
</form>
```

### ❌ À ÉVITER : Commentaires inutiles

```html
<!-- Mauvais : C'est évident -->
<p>Text</p>
<!-- Ceci est un paragraphe -->

<!-- Mauvais : Trop technique sans contexte -->
<div class="flex-col gap-3">Text</div>
<!-- div flexbox colonne gap 3rem -->
```

---

## 📌 COMMENTAIRES CSS

### ✅ BON : Sections et blocs

```css
/* ============================
   HEADER / BURGER
   ============================ */

/* Conteneur principal du burger */
.header-brg__icon {
  background: var(--third-color);
  width: 6rem;
  height: 6rem;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}

/* SVG à l'intérieur du burger (icône) */
.header-brg svg {
  width: 2.4rem;
  height: 2.4rem;
}

/* ============================
   ANIMATIONS
   ============================ */

/* Rotation 360° en 0.6s (3 fois) - Pour la carte offre */
@keyframes rotate-center {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

/* Appliquer l'animation de rotation */
.rotate-center {
  animation: rotate-center 0.6s ease-in-out both 3;
}

/* Déclencher la rotation au survol de la carte */
.card-container:hover .rotate-center {
  animation: rotate-center 0.6s ease-in-out both 3;
}

/* ============================
   BOUTONS CTA
   ============================ */

/* Conteneur des boutons d'action */
.cta-container {
  display: flex;
  gap: 3rem;
  justify-content: center;
  margin-top: 5rem;
}

/* Lien principal (ex: "Connexions") */
.cta-container a {
  background: var(--third-color);
  padding: 1rem;
  border-radius: 25px;
  text-transform: uppercase;
}

/* Variante secondaire (ex: "Télécharger APP") */
.cta-container .cta-connect {
  /* Hérite des styles du conteneur, avec modifications ici si besoin */
  font-weight: bold;
}

/* ============================
   CARD OFFRE
   ============================ */

/* Conteneur de la carte promotionnelle */
.card-container {
  width: fit-content;
  padding: 2.4rem 4rem;
  background: var(--third-color);
  border: 4px solid #38ef7d;
  border-radius: 2rem;
}

/* Texte à l'intérieur de la carte */
.card-container p {
  font-size: 2.8rem;
  font-weight: bold;
  color: rgb(255, 255, 255);
  margin: 0; /* Enlève les marges par défaut */
}

/* ============================
   RESPONSIVE / MOBILE
   ============================ */

/* Sur écran petit (mobile) */
@media (max-width: 768px) {
  /* Réduire la taille du titre */
  h1 {
    font-size: 3rem;
  }

  /* Empiler les boutons verticalement */
  .cta-container {
    flex-direction: column;
  }
}
```

### ✅ BON : Commentaires détaillés pour les règles complexes

```css
/* 
 * Flexbox pour aligner verticalement les éléments
 * - display: flex : active le flexbox
 * - flex-direction: column : empile les enfants verticalement
 * - align-items: center : centre horizontalement
 * - gap: 1rem : espacement entre enfants
 */
.intro {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

/* 
 * Ombre portée avec dégradé de couleur
 * - box-shadow : drop shadow noir avec flou
 * - border : bordure double verte
 * - background-image : dégradé (teal → vert)
 */
.button {
  box-shadow: rgb(0, 0, 0) 5px 5px 15px 5px;
  border: 2px double #38ef7d;
  background-image: linear-gradient(90deg, #11998e, #38ef7d);
}
```

### ❌ À ÉVITER : Commentaires inutiles

```css
/* Mauvais : Obvious */
.text {
  color: red;
} /* Couleur rouge */

/* Mauvais : Pas assez informatif */
.box {
  padding: 2rem;
} /* Padding */

/* Mauvais : Orthographe/grammaire */
.btn {
  /* button pour click */
}
```

---

## 📋 STRUCTURE RECOMMANDÉE

### Pour les FICHIERS HTML

```html
<!-- 
  ====================================
  PAGE : Accueil Aegis Bank
  ====================================
  Description : Page d'accueil avec hero, offres et footer
  Auteur : [Ton nom]
  Date : [Date]
-->

<!DOCTYPE html>
<html>
  <head>
    <!-- Métadonnées et CSS -->
  </head>
  <body>
    <!-- ========== SECTIONS ========== -->

    <!-- En-tête avec logo et menu -->

    <!-- Contenu principal (sections) -->

    <!-- Pied de page -->
  </body>
</html>
```

### Pour les FICHIERS CSS

```css
/*
  ====================================
  STYLE CSS : Aegis Bank
  ====================================
  Description : Styles principaux du site
  Auteur : [Ton nom]
  Date : [Date]
  Variables : Voir styles/all-variables.css
*/

@import "./styles/all-variables.css";

/* Ordre logique recommandé :
   1. LAYOUT / STRUCTURE (body, container)
   2. HEADER / NAVIGATION
   3. MAIN CONTENT (sections)
   4. BUTTONS / CTA
   5. CARDS
   6. ANIMATIONS
   7. FOOTER
   8. MEDIA QUERIES / RESPONSIVE
*/

/* ========== 1. LAYOUT ========== */
body {
}

/* ========== 2. HEADER ========== */
.header {
}

/* ... etc ... */
```

---

## 🎯 BONNES PRATIQUES

| À FAIRE                                      | À ÉVITER                                      |
| -------------------------------------------- | --------------------------------------------- |
| ✅ Commenter les sections principales        | ❌ Commenter chaque ligne                     |
| ✅ Expliquer le _pourquoi_, pas le _quoi_    | ❌ Dire "color: red" en commentaire           |
| ✅ Clarifier les règles complexes            | ❌ Mettre des commentaires évidents           |
| ✅ Documenter les hacks ou workarounds       | ❌ Laisser du code commenté (sauf temporaire) |
| ✅ Utiliser des séparateurs visuels (`====`) | ❌ Murs de texte sans structure               |
| ✅ Français clair et grammaire correcte      | ❌ Abréviations incompréhensibles             |

---

## 💡 EXEMPLE COMPLET : Votre projet

### HTML commenté

```html
<!-- ==================== HEADER ==================== -->
<header>
  <!-- Bouton burger menu (3 lignes) -->
  <a class="header-brg__icon" href="#">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      width="25"
      height="25"
      viewBox="0 0 16 16"
    >
      <!-- 3 lignes horizontales du burger -->
      <path
        fill="white"
        d="M2 2.5a.5.5 0 0 1 .5-.5h11a.5.5 0 0 1 0 1h-11a.5.5 0 0 1-.5-.5..."
      />
    </svg>
  </a>
</header>

<!-- ==================== SECTION APPELS À L'ACTION ==================== -->
<!-- Deux boutons CTA : "Connexions" et "Télécharger APP" -->
<div class="cta-container">
  <a href="#">Connexions</a>
  <a class="cta-connect" href="#">Télécharger APP</a>
</div>

<!-- ==================== SECTION OFFRE ==================== -->
<!-- Carte promotionnelle avec animation de rotation au survol -->
<div class="card-container">
  <p class="rotate-center">
    Offre 20€ <br />
    Mars 2026
  </p>
</div>
```

### CSS commenté

```css
/* ==================== HEADER / BURGER ==================== */

/* Conteneur principal du bouton burger
   - Gradient vert en arrière-plan
   - Centrage flexbox pour l'SVG
   - Bordure arrondie */
.header-brg__icon {
  background: var(--third-color);
  width: 6rem;
  height: 6rem;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 25px;
}

/* ==================== ANIMATIONS ==================== */

/* Animation : Rotation 360° en 0.6s
   - Se déclenche 3 fois de suite
   - Ease-in-out pour un effet naturel
   - Utilisée pour la carte offre au survol */
@keyframes rotate-center {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

/* Appliquer l'animation au texte de la carte */
.rotate-center {
  animation: rotate-center 0.6s ease-in-out both 3;
}

/* ==================== BOUTONS CTA ==================== */

/* Conteneur flexbox pour les boutons d'action
   - Centrage horizontal
   - Espacement de 3rem entre les boutons
   - Marge supérieure pour l'écartement du contenu */
.cta-container {
  display: flex;
  gap: 3rem;
  justify-content: center;
  margin-top: 5rem;
}

/* ==================== CARD OFFRE ==================== */

/* Conteneur de la carte avec gradient vert
   - Padding pour l'espacement interne
   - Bordure épaisse (4px) verte
   - Ombre pour la profondeur */
.card-container {
  width: fit-content;
  padding: 2.4rem 4rem;
  background: var(--third-color);
  border: 4px solid #38ef7d;
  border-radius: 2rem;
}
```

---

## 📝 À VOUS DE JOUER !

Voici un template à copier-coller pour vos commentaires :

```html
<!-- ==================== [NOM SECTION] ==================== -->
<!-- Description brève de ce bloc -->
<div class="[classe]">
  <!-- [Élément spécifique] -->
  <element>Contenu</element>
</div>
```

```css
/* ==================== [NOM SECTION] ==================== */

/* Description du bloc et son but */
.classe {
  /* Propriétés */
}

/* Cas spécifique / état du bloc */
.classe:hover {
  /* Propriétés au survol */
}
```

Souhaitez-vous que j'ajoute ces commentaires directement à votre `index.html` et `style.css` ?
