# AAACT's Digital Accessibility and Inclusive Design (DAID) Team Website

<div lang="fr">
<p><a href="#version-française">Passer à la version française</a></p>
</div>

---

## Project purpose

This project creates a simple, maintainable, and accessible bilingual website for the AAACT Accessibility Digital Design Team.

The site will:

- support English and French content
- follow Government of Canada design patterns
- use the GC Design System as the interface foundation
- be easy to edit and expand over time
- integrate with GitHub and Netlify workflows
- prioritize accessibility from the start

---

## Planned stack

- Eleventy (11ty)
- Node.js
- npm
- Nunjucks
- HTML, CSS, and minimal JavaScript
- GC Design System (web components)
- GitHub
- Netlify

---

## Project principles

- Accessibility first
- Bilingual from the beginning
- Keep the architecture simple
- Prefer maintainability over complexity
- Avoid unnecessary frameworks
- Use semantic HTML and progressive enhancement
- Keep JavaScript minimal
- Keep commits small, focused, and easy to review

---

## Accessibility expectations

The project should include:

- semantic landmarks
- proper heading structure
- skip links
- keyboard accessibility
- visible focus styles
- descriptive links
- accessible forms
- strong colour contrast
- minimal reliance on JavaScript for core features
- no flashing or distracting motion by default

---

## Initial content areas

- Home
- About the team
- Services
- Resources
- Contact

---

## Suggested homepage sections

- Hero / introduction
- What we do
- Featured resources
- Latest updates
- Contact / get in touch

---

## Expected project structure

```text
src/
  _data/
  _includes/
	layouts/
	partials/
  assets/
	css/
	js/
  en/
  fr/
```

---

## Working rules for AI-assisted scaffolding

When generating files for this project:

- provide full files, not partial snippets
- keep dependencies minimal
- use clear, predictable file names
- comment code only where it helps understanding
- prefer solutions that are easy for a small team to maintain
- keep output ready to paste directly into files
- keep commits small and logically grouped
- do not mix unrelated changes in the same commit

---

## Commit expectations

Commits should stay small and manageable.

Preferred commit flow:

1. project scaffolding
2. Eleventy configuration
3. base layouts and partials
4. bilingual structure and sample content
5. GC Design System integration
6. styling and accessibility improvements
7. Netlify configuration
8. documentation updates

Each commit should include:

- a short, clear subject line
- a helpful body describing what changed and why

---

## Documentation requirements

All project documentation should be provided in both English and French.

This includes, where applicable:

- `README.md`
- setup instructions
- contribution guides
- planning documents
- user-facing documentation

Code comments may remain in English.

---

## Status

This repository is currently being scaffolded.

---

## Notes

This project should remain flexible enough to grow into a fuller team or service website over time without requiring a complete rebuild.

---

<div lang="fr" id="version-française">

# Site de l’Accessibilité numérique et conception inclusive de AAACT

---

## Objectif du projet

Ce projet vise à créer un site web bilingue simple, maintenable et accessible pour l’équipe de conception numérique accessible AAACT.

Le site devra :

- prendre en charge le contenu en anglais et en français
- suivre les modèles de conception du gouvernement du Canada
- utiliser le Système de design GC comme base d’interface
- être facile à modifier et à faire évoluer
- s’intégrer aux flux de travail GitHub et Netlify
- placer l’accessibilité au cœur du projet

---

## Technologies prévues

- Eleventy (11ty)
- Node.js
- npm
- Nunjucks
- HTML, CSS et JavaScript minimal
- Système de design GC (composants web)
- GitHub
- Netlify

---

## Principes du projet

- Accessibilité avant tout
- Bilingue dès le départ
- Garder une architecture simple
- Privilégier la maintenabilité à la complexité
- Éviter les frameworks inutiles
- Utiliser du HTML sémantique et l’amélioration progressive
- Limiter l’utilisation de JavaScript
- Garder des commits petits, ciblés et faciles à réviser

---

## Exigences en matière d’accessibilité

Le projet devrait inclure :

- des repères sémantiques
- une structure de titres appropriée
- des liens d’évitement
- une navigation complète au clavier
- des styles de focus visibles
- des liens descriptifs
- des formulaires accessibles
- un contraste de couleurs suffisant
- une dépendance minimale au JavaScript pour les fonctionnalités principales
- aucune animation clignotante ou distrayante par défaut

---

## Sections initiales

- Accueil
- À propos de l’équipe
- Services
- Ressources
- Contact

---

## Sections suggérées pour la page d’accueil

- Introduction / bannière principale
- Ce que nous faisons
- Ressources en vedette
- Dernières nouvelles
- Contact / nous joindre

---

## Structure de projet prévue

```text
src/
  _data/
  _includes/
	layouts/
	partials/
  assets/
	css/
	js/
  en/
  fr/
```

---

## Règles de travail pour la génération assistée par IA

Lors de la génération de fichiers pour ce projet :

- fournir des fichiers complets, pas des extraits
- limiter les dépendances
- utiliser des noms de fichiers clairs et prévisibles
- commenter le code seulement lorsque cela aide à la compréhension
- privilégier des solutions faciles à maintenir pour une petite équipe
- produire du contenu prêt à être copié directement dans les fichiers
- garder des commits petits et logiquement regroupés
- ne pas mélanger des changements non liés dans un même commit

---

## Exigences relatives aux commits

Les commits doivent rester petits et faciles à gérer.

Ordre recommandé :

1. initialisation du projet
2. configuration d’Eleventy
3. layouts et partials de base
4. structure bilingue et contenu exemple
5. intégration du Système de design GC
6. styles et améliorations d’accessibilité
7. configuration Netlify
8. mises à jour de la documentation

Chaque commit doit inclure :

- un titre court et clair
- une description utile expliquant les changements et leur raison

---

## Exigences relatives à la documentation

Toute la documentation du projet doit être fournie en anglais et en français.

Cela inclut, selon le cas :

- `README.md`
- les instructions d’installation
- les guides de contribution
- les documents de planification
- la documentation destinée aux utilisateurs

Les commentaires dans le code peuvent rester en anglais.

---

## État du projet

Ce dépôt est actuellement en cours de mise en place.

---

## Remarques

Ce projet doit rester suffisamment flexible pour évoluer vers un site d’équipe ou de service plus complet au fil du temps, sans nécessiter une reconstruction complète.

</div>
