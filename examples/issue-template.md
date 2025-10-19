# Templates d'Issues

Ce guide contient des templates d'issues pour votre projet. Les templates d'issues aident les contributeurs à fournir les informations nécessaires.

---

## Structure des Templates

Pour utiliser ces templates automatiquement sur GitHub, créez ces fichiers :

```
.github/
└── ISSUE_TEMPLATE/
    ├── bug_report.md
    ├── feature_request.md
    ├── documentation.md
    └── question.md
```

---

## Template : Bug Report

**Fichier :** `.github/ISSUE_TEMPLATE/bug_report.md`

```markdown
---
name: Bug Report
about: Signaler un bug pour nous aider à améliorer le projet
title: "[BUG] "
labels: "bug"
assignees: ""
---

## Description du Bug

<!-- Décrivez clairement et de manière concise le bug -->

## Étapes pour Reproduire

<!-- Étapes pour reproduire le comportement -->

1. Aller sur '...'
2. Cliquer sur '...'
3. Scroller jusqu'à '...'
4. Observer l'erreur

## Comportement Attendu

<!-- Décrivez ce qui devrait se passer normalement -->

## Comportement Actuel

<!-- Décrivez ce qui se passe actuellement (le bug) -->

## Captures d'Écran

<!-- Si applicable, ajoutez des captures d'écran pour illustrer le problème -->

## Environnement

**Desktop (complétez les informations suivantes) :**

- OS: [ex: Windows 11, macOS 13, Ubuntu 22.04]
- Navigateur: [ex: Chrome, Firefox, Safari]
- Version: [ex: 119.0]

**Smartphone (complétez les informations suivantes) :**

- Device: [ex: iPhone 14, Samsung Galaxy S23]
- OS: [ex: iOS 17.1, Android 13]
- Navigateur: [ex: Safari, Chrome]
- Version: [ex: 17.1]

## Contexte Additionnel

<!-- Ajoutez tout autre contexte pertinent à propos du problème -->

## Logs/Messages d'Erreur

<!-- Si applicable, collez les messages d'erreur ou logs -->
```

[Coller les logs ici]

```

## ⚠️ Impact

<!-- Quelle est la sévérité du bug ? -->

- [ ] Bloquant (impossible de continuer)
- [ ] Majeur (fonctionnalité principale impactée)
- [ ] Mineur (petit problème mais contournable)
- [ ] Cosmétique (problème visuel uniquement)

## 💡 Solution Proposée (optionnel)

<!-- Si vous avez une idée de comment corriger ce bug, partagez-la -->
```

---

## Template : Feature Request

**Fichier :** `.github/ISSUE_TEMPLATE/feature_request.md`

```markdown
---
name: Feature Request
about: Suggérer une nouvelle fonctionnalité pour ce projet
title: "[FEATURE] "
labels: "enhancement"
assignees: ""
---

## Résumé de la Fonctionnalité

<!-- Résumez en une phrase la fonctionnalité proposée -->

## Problème à Résoudre

<!-- Décrivez le problème que cette fonctionnalité résoudrait -->
<!-- Ex: "Je suis toujours frustré quand [...]" -->

**Qui est affecté par ce problème ?**

- [ ] Utilisateurs finaux
- [ ] Développeurs
- [ ] Administrateurs
- [ ] Tous

## Solution Proposée

<!-- Décrivez la solution que vous aimeriez voir implémentée -->

### Comportement Attendu

1. L'utilisateur peut...
2. Le système fait...
3. Le résultat est...

### Interface Utilisateur (si applicable)

<!-- Décrivez ou dessinez l'interface que vous imaginez -->

## Alternatives Considérées

<!-- Décrivez les solutions alternatives que vous avez envisagées -->

## Cas d'Usage

<!-- Donnez des exemples concrets d'utilisation -->

**Scénario 1 :**
```

En tant que [type d'utilisateur]
Je veux [action]
Afin de [bénéfice]

```

**Scénario 2 :**
```

En tant que [type d'utilisateur]
Je veux [action]
Afin de [bénéfice]

```

## 🎨 Mockups/Designs (optionnel)

<!-- Si vous avez des mockups, dessins ou liens Figma, ajoutez-les ici -->

## 📈 Priorité Suggérée

<!-- Quelle importance a cette feature pour vous ? -->

- [ ] Critique (bloque mon utilisation)
- [ ] Haute (amélioration significative)
- [ ] Moyenne (ce serait bien d'avoir)
- [ ] Basse (nice to have)

## 🔗 Fonctionnalités Liées

<!-- Listez les issues ou features liées -->

- Related to #
- Depends on #

## 📝 Contexte Additionnel

<!-- Ajoutez tout autre contexte, screenshots ou informations pertinentes -->

## 💰 Volonté de Contribuer

<!-- Seriez-vous prêt à implémenter cette feature ? -->

- [ ] Je peux implémenter cette feature
- [ ] Je peux aider à la tester
- [ ] Je peux aider à la documenter
- [ ] J'aimerais juste la suggérer
```

---

## Template : Documentation

**Fichier :** `.github/ISSUE_TEMPLATE/documentation.md`

```markdown
---
name: Documentation
about: Améliorer ou corriger la documentation
title: "[DOCS] "
labels: "documentation"
assignees: ""
---

## Type de Demande

- [ ] Documentation manquante
- [ ] Documentation incorrecte
- [ ] Documentation obsolète
- [ ] Documentation peu claire
- [ ] Traduction
- [ ] Autre

## Localisation

<!-- Où se trouve (ou devrait se trouver) cette documentation ? -->

**Fichier/Page :** [ex: README.md, docs/installation.md]
**Section :** [ex: "Installation", "API Reference"]
**Lien :** [si applicable]

## Problème Actuel

<!-- Qu'est-ce qui ne va pas avec la documentation actuelle ? -->

**Citation actuelle (si applicable) :**
```

[Coller le texte actuel ici]

```

## ✅ Amélioration Proposée

<!-- Comment devrait être la documentation ? -->

**Texte proposé :**
```

[Proposer le nouveau texte ici]

```

## 🎯 Public Cible

<!-- Qui bénéficiera de cette amélioration ? -->

- [ ] Débutants
- [ ] Utilisateurs intermédiaires
- [ ] Utilisateurs avancés
- [ ] Développeurs contributeurs

## 📚 Ressources Additionnelles

<!-- Liens vers d'autres ressources qui pourraient aider -->

- [Lien 1]
- [Lien 2]

## 💡 Exemples

<!-- Si applicable, donnez des exemples de ce qui devrait être documenté -->

```

[Exemple de code ou d'utilisation]

```

## ✍️ Volonté de Contribuer

- [ ] Je peux écrire cette documentation
- [ ] J'ai besoin d'aide pour l'écrire
- [ ] Je signale juste le problème
```

---

## Template : Question

**Fichier :** `.github/ISSUE_TEMPLATE/question.md`

````markdown
---
name: Question
about: Poser une question sur le projet
title: "[QUESTION] "
labels: "question"
assignees: ""
---

## Votre Question

<!-- Posez votre question clairement -->

## Contexte

<!-- Expliquez le contexte de votre question -->

### Ce que vous essayez de faire

<!-- Décrivez ce que vous essayez d'accomplir -->

### Ce que vous avez déjà essayé

<!-- Listez ce que vous avez déjà tenté -->

1.
2.
3.

## Recherches Effectuées

<!-- Où avez-vous déjà cherché la réponse ? -->

- [ ] J'ai lu la documentation
- [ ] J'ai cherché dans les issues existantes
- [ ] J'ai cherché sur Google/Stack Overflow
- [ ] J'ai lu le code source

**Liens consultés :**

- [Lien 1]
- [Lien 2]

## Environnement (si applicable)

- OS: [ex: Windows, macOS, Linux]
- Version du projet: [ex: 1.2.3]
- Langage/Framework: [ex: Node.js 18, React 18]

## Code ou Exemple (si applicable)

<!-- Partagez un extrait de code qui illustre votre question -->

```javascript
// Votre code ici
```
````

## Résultat Attendu

<!-- Quel résultat espérez-vous obtenir ? -->

````

---

## 🔧 Template : Configuration/Setup Issue

**Fichier :** `.github/ISSUE_TEMPLATE/setup_issue.md`

```markdown
---
name: Setup/Configuration Issue
about: Problème lors de l'installation ou de la configuration
title: '[SETUP] '
labels: 'setup, help wanted'
assignees: ''
---

## 🔧 Type de Problème

- [ ] Installation
- [ ] Configuration
- [ ] Dépendances
- [ ] Environnement
- [ ] Build
- [ ] Déploiement

## 📋 Étapes Suivies

<!-- Listez les étapes que vous avez suivies -->

1.
2.
3.

## ❌ Erreur Rencontrée

<!-- Décrivez l'erreur ou le problème -->

**Message d'erreur :**
````

[Coller le message d'erreur complet ici]

````

**Screenshot (si applicable) :**
<!-- Ajoutez une capture d'écran -->

## 💻 Environnement

**Système d'exploitation :**
- [ ] Windows [version: ]
- [ ] macOS [version: ]
- [ ] Linux [distribution: ]

**Versions :**
- Node.js: [ex: v18.16.0]
- npm/yarn: [ex: npm 9.5.1]
- Git: [ex: 2.40.0]
- Autre: [si applicable]

**Installation :**
- [ ] Installation globale
- [ ] Installation locale
- [ ] Via Docker
- [ ] Via binaire

## 📝 Configuration

<!-- Partagez votre fichier de configuration (sans infos sensibles) -->

```json
{
  "config": "here"
}
````

## Logs Complets

<!-- Partagez les logs complets de la commande qui échoue -->

```
[Coller les logs ici]
```

## Résultat Attendu

<!-- Que devrait-il se passer normalement ? -->

## Informations Additionnelles

<!-- Toute autre information pertinente -->

````

---

## 🎨 Template : UI/UX Issue

**Fichier :** `.github/ISSUE_TEMPLATE/ui_ux_issue.md`

```markdown
---
name: UI/UX Issue
about: Signaler un problème d'interface ou d'expérience utilisateur
title: '[UI/UX] '
labels: 'ui, ux, design'
assignees: ''
---

## 🎨 Type de Problème

- [ ] Problème visuel/style
- [ ] Problème d'utilisabilité
- [ ] Problème d'accessibilité
- [ ] Problème de responsive
- [ ] Problème de performance UI
- [ ] Amélioration de l'expérience

## 📍 Localisation

**Page/Composant :** [ex: Page d'accueil, Bouton de connexion]
**URL (si applicable) :** [lien]

## ❌ Problème Actuel

<!-- Décrivez le problème d'interface ou d'expérience -->

## ✅ Amélioration Proposée

<!-- Comment devrait-ce être ? -->

## 📸 Captures d'Écran

**Avant (actuel) :**
<!-- Ajoutez une capture d'écran du problème -->

**Après (proposé) :**
<!-- Si vous avez un mockup de la solution -->

## 🖥️ Environnement

**Device :**
- [ ] Desktop
- [ ] Tablette
- [ ] Mobile

**Navigateur :**
- [ ] Chrome
- [ ] Firefox
- [ ] Safari
- [ ] Edge
- [ ] Autre: [préciser]

**Résolution d'écran :** [ex: 1920x1080, 375x667]

## ♿ Impact sur l'Accessibilité

- [ ] Problème de contraste
- [ ] Navigation au clavier impossible
- [ ] Pas compatible screen reader
- [ ] Texte trop petit
- [ ] Autre: [préciser]

## 📊 Impact Utilisateur

- [ ] Bloque l'utilisation
- [ ] Frustrant mais contournable
- [ ] Mineur
- [ ] Amélioration esthétique

## 💡 Suggestions de Design

<!-- Si vous avez des idées de solution -->
````

---

## Template : Performance Issue

**Fichier :** `.github/ISSUE_TEMPLATE/performance_issue.md`

```markdown
---
name: Performance Issue
about: Signaler un problème de performance
title: "[PERF] "
labels: "performance"
assignees: ""
---

## Type de Problème de Performance

- [ ] Temps de chargement lent
- [ ] Utilisation excessive de mémoire
- [ ] Utilisation excessive de CPU
- [ ] Lag/Freeze de l'interface
- [ ] Requêtes réseau lentes
- [ ] Autre

## Localisation

**Où se produit le problème ?**

- Page/Composant: [ex: Dashboard, Liste des utilisateurs]
- Fonction/Méthode: [ex: fetchUsers(), calculateTotal()]

## Métriques

**Performance Actuelle :**

- Temps de chargement: [ex: 5 secondes]
- Utilisation mémoire: [ex: 500 MB]
- Temps de réponse API: [ex: 2 secondes]

**Performance Attendue :**

- Temps de chargement: [ex: < 1 seconde]
- Utilisation mémoire: [ex: < 100 MB]
- Temps de réponse API: [ex: < 500ms]

## Étapes pour Reproduire

1.
2.
3.

## Environnement

- OS: [ex: Windows 11]
- Navigateur: [ex: Chrome 119]
- Device: [ex: Desktop, Mobile]
- Connexion: [ex: Wifi, 4G, Fiber]

## Profiling (si disponible)

<!-- Si vous avez fait du profiling, partagez les résultats -->
```

[Résultats du profiling]

```

## 💡 Solution Proposée

<!-- Si vous avez une idée d'optimisation -->

## 📝 Contexte Additionnel

<!-- Informations supplémentaires -->
```

---

## Configuration : Issue Template Chooser

Pour personnaliser le sélecteur d'issues sur GitHub, créez :

**Fichier :** `.github/ISSUE_TEMPLATE/config.yml`

```yaml
blank_issues_enabled: false
contact_links:
  - name: 💬 Discussions
    url: https://github.com/VOTRE-USERNAME/VOTRE-REPO/discussions
    about: Pour les questions générales et discussions
  - name: 📚 Documentation
    url: https://votre-site-docs.com
    about: Consultez la documentation complète
  - name: 🐦 Twitter
    url: https://twitter.com/votre-handle
    about: Suivez-nous pour les actualités
```

---

## Bonnes Pratiques pour les Issues

### Pour les Créateurs d'Issues

✅ **À FAIRE :**

- Chercher si l'issue existe déjà
- Utiliser le bon template
- Fournir toutes les informations demandées
- Être clair et concis
- Ajouter des captures d'écran
- Tester avant de signaler

❌ **À ÉVITER :**

- Issues vagues ("ça marche pas")
- Dupliquer des issues existantes
- Mélanger plusieurs problèmes dans une issue
- Informations sensibles (mots de passe, tokens)
- Langage inapproprié

### Pour les Mainteneurs

✅ **À FAIRE :**

- Répondre rapidement
- Labelliser les issues
- Assigner les bonnes personnes
- Utiliser des milestones
- Fermer les duplicatas poliment
- Remercier les contributeurs

❌ **À ÉVITER :**

- Laisser les issues sans réponse
- Fermer sans explication
- Être condescendant
- Ignorer les questions

---

## Labels Recommandés

Créez ces labels sur GitHub :

### Type

- `bug` - Quelque chose ne fonctionne pas
- `enhancement` - Nouvelle fonctionnalité ou demande
- `documentation` - Amélioration ou ajout de documentation
- `question` - Question ou demande d'information
- `performance` - Problème de performance

### Priorité

- `priority: critical` - Problème critique
- `priority: high` - Haute priorité
- `priority: medium` - Priorité moyenne
- `priority: low` - Basse priorité

### Status

- `status: needs-triage` - Besoin d'être évalué
- `status: in-progress` - En cours de traitement
- `status: blocked` - Bloqué par autre chose
- `status: waiting-feedback` - Attente de retour

### Difficulté

- `good first issue` - Bon pour les débutants
- `help wanted` - Aide demandée
- `easy` - Facile à résoudre
- `hard` - Difficile, nécessite expertise

### Autres

- `duplicate` - Doublon d'une autre issue
- `wontfix` - Ne sera pas corrigé
- `invalid` - Issue invalide
- `security` - Problème de sécurité

---

## Exemple d'Issue Bien Rédigée

```markdown
## Description du Bug

Le bouton "Sauvegarder" dans le formulaire de profil ne répond pas au clic sur Safari iOS.

## Étapes pour Reproduire

1. Aller sur https://app.example.com/profile
2. Modifier le nom d'utilisateur
3. Cliquer sur le bouton "Sauvegarder"
4. Observer que rien ne se passe

## Comportement Attendu

Le profil devrait être sauvegardé et un message de confirmation devrait s'afficher.

## Comportement Actuel

Le bouton ne réagit pas au clic. Aucun message d'erreur n'apparaît.

## Captures d'Écran

[Vidéo du bug](https://example.com/video.mp4)

## Environnement

**Smartphone :**

- Device: iPhone 13
- OS: iOS 17.1
- Navigateur: Safari
- Version: 17.1

## Contexte Additionnel

Le bug se produit uniquement sur Safari iOS. Testé avec succès sur :

- Chrome iOS ✅
- Chrome Android ✅
- Chrome Desktop ✅
- Firefox Desktop ✅

## Logs/Messages d'Erreur

Console Safari (aucune erreur visible):
```

(empty)

```

## ⚠️ Impact

- [x] Majeur (fonctionnalité principale impactée)

Les utilisateurs iOS/Safari (environ 20% de notre base) ne peuvent pas modifier leur profil.

## 💡 Solution Proposée

Cela pourrait être lié au event handler. Suggère de vérifier si :
1. L'event `touchend` est bien géré sur iOS
2. Le bouton n'a pas de conflits CSS qui bloquent les interactions
```

---

## Checklist pour une Issue Parfaite

Avant de soumettre votre issue :

- [ ] J'ai cherché si cette issue existe déjà
- [ ] J'ai utilisé le bon template
- [ ] Le titre est clair et descriptif
- [ ] J'ai fourni toutes les informations demandées
- [ ] J'ai ajouté des captures d'écran (si applicable)
- [ ] J'ai testé dans plusieurs environnements
- [ ] J'ai inclus les logs d'erreur complets
- [ ] J'ai vérifié qu'il n'y a pas d'infos sensibles
- [ ] Le ton est respectueux et professionnel

---

## Ressources

- [About Issue Templates](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests)
- [Configuring Issue Templates](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository)
- [Issue Labels](https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/managing-labels)

---

**Des issues bien rédigées = Résolution plus rapide ! ⚡**
