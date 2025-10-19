# Guide de Contribution

Merci de votre intérêt pour contribuer au Git & GitHub Workshop ! 🎉

Ce document vous guide à travers le processus de contribution. Nous accueillons toutes les contributions : corrections de bugs, nouvelles fonctionnalités, améliorations de la documentation, et plus encore.

---

## Table des Matières

- [Code de Conduite](#code-de-conduite)
- [Comment Contribuer](#comment-contribuer)
- [Premier Pas](#premier-pas)
- [Processus de Contribution](#processus-de-contribution)
- [Standards de Code](#standards-de-code)
- [Conventions de Commits](#conventions-de-commits)
- [Pull Requests](#pull-requests)
- [Issues](#issues)
- [Questions](#questions)

---

## Code de Conduite

En participant à ce projet, vous acceptez de respecter notre code de conduite. Soyez respectueux, inclusif et constructif dans toutes vos interactions.

**Principes :**

- Soyez accueillant envers tous
- Respectez les opinions divergentes
- Acceptez les critiques constructives
- Concentrez-vous sur ce qui est bon pour la communauté
- Faites preuve d'empathie

**Non toléré :**

- Langage ou comportement discriminatoire
- Harcèlement sous toute forme
- Trolling ou commentaires insultants
- Attaques personnelles ou politiques

---

## Comment Contribuer

Il existe de nombreuses façons de contribuer à ce projet :

### Partager des Idées

- Proposer de nouvelles fonctionnalités
- Suggérer des améliorations
- Donner du feedback

### Signaler des Bugs

- Ouvrir une issue avec le template "Bug Report"
- Fournir des détails complets pour reproduire le bug

### Améliorer la Documentation

- Corriger des typos
- Clarifier des sections confuses
- Ajouter des exemples
- Traduire la documentation

### Contribuer du Code

- Corriger des bugs
- Implémenter de nouvelles fonctionnalités
- Améliorer les performances
- Ajouter des tests

### Améliorer le Design

- Améliorer l'UI/UX
- Créer des illustrations
- Améliorer l'accessibilité

### Tester

- Tester les nouvelles fonctionnalités
- Faire du QA
- Signaler les problèmes

### Aider la Communauté

- Répondre aux questions
- Aider les nouveaux contributeurs
- Partager vos connaissances

---

## Premier Pas

### Bon pour Débuter

Cherchez les issues avec ces labels :

- `good first issue` - Parfait pour les débutants
- `help wanted` - Nous avons besoin d'aide
- `documentation` - Améliorations de la doc

### Comprendre le Projet

Avant de contribuer :

1. Lisez le [README.md](README.md)
2. Parcourez les [exercices](exercises/)
3. Regardez les [exemples](examples/)
4. Consultez les [issues existantes](../../issues)
5. Rejoignez les [discussions](../../discussions)

---

## Processus de Contribution

### 1. Fork le Dépôt

Cliquez sur le bouton "Fork" en haut de la page.

### 2. Clone Votre Fork

```bash
git clone https://github.com/VOTRE-USERNAME/git-workshop.git
cd git-workshop
```

### 3. Configurer l'Upstream

```bash
git remote add upstream https://github.com/ORIGINAL-OWNER/git-workshop.git
```

### 4. Créer une Branche

```bash
# Toujours partir de main à jour
git checkout main
git pull upstream main

# Créer votre branche
git checkout -b type/description-courte
```

**Exemples :**

```bash
git checkout -b feature/add-exercise-4
git checkout -b bugfix/fix-typo-readme
git checkout -b docs/improve-installation-guide
```

Consultez le [guide de nommage des branches](examples/branch-naming.md) pour plus de détails.

### 5. Faire Vos Modifications

- Écrivez du code propre et lisible
- Suivez les conventions du projet
- Commentez le code complexe
- Testez vos modifications

### 6. Commit Vos Changements

```bash
git add .
git commit -m "type: description claire du changement"
```

Consultez les [conventions de commits](#conventions-de-commits) ci-dessous.

### 7. Sync avec Upstream

```bash
git fetch upstream
git merge upstream/main
```

Résolvez les conflits si nécessaire.

### 8. Push vers Votre Fork

```bash
git push origin votre-branche
```

### 9. Créer une Pull Request

1. Allez sur votre fork sur GitHub
2. Cliquez sur "Compare & pull request"
3. Remplissez le template de PR
4. Soumettez la PR

Consultez le [guide des Pull Requests](#pull-requests) pour plus de détails.

---

## Standards de Code

### Structure des Fichiers

```
git-workshop/
├── docs/                 # Documentation
├── exercises/           # Exercices pratiques
│   ├── 01-basics/
│   ├── 02-branches/
│   └── 03-collaboration/
├── examples/            # Exemples et guides
└── participants/        # Liste des participants
```

### Style Markdown

- Utilisez des titres ATX (`#` pas `===`)
- Une ligne vide avant et après les titres
- Listes avec tirets `-` (pas `*` ou `+`)
- Blocs de code avec triple backticks et langage
- Lignes max 120 caractères (documentation)

**Exemple :**

````markdown
# Titre Principal

Description claire et concise.

## Sous-Titre

- Item 1
- Item 2

```bash
commande exemple
```
````

```

### Langue

- Documentation principale : **Français**
- Code/Exemples : Français ou Anglais selon le contexte
- Commentaires de code : Français de préférence

### Accessibilité

- Utilisez des textes alternatifs pour les images
- Évitez les liens "cliquez ici"
- Utilisez des titres de section clairs
- Testez avec un lecteur d'écran si possible

---

## 📝 Conventions de Commits

Nous utilisons des commits sémantiques pour un historique clair.

### Format

```

<type>: <description>

[corps optionnel]

[footer optionnel]

````

### Types

- `feat` - Nouvelle fonctionnalité
- `fix` - Correction de bug
- `docs` - Documentation uniquement
- `style` - Formatage, style (pas de changement de code)
- `refactor` - Refactorisation
- `test` - Ajout/modification de tests
- `chore` - Maintenance, configuration

### Exemples

```bash
# Bons commits
feat: add exercise 4 on advanced Git
fix: correct typo in README installation section
docs: improve branch naming guide with examples
style: format code according to prettier config
refactor: reorganize exercises directory structure
test: add tests for exercise validation
chore: update dependencies to latest versions

# Mauvais commits
update stuff
fix bug
changes
asdfgh
WIP
````

### Règles

1. **Utiliser l'impératif** : "add" pas "added" ou "adds"
2. **Première lettre minuscule** : "add" pas "Add"
3. **Pas de point final** dans la description
4. **Maximum 50 caractères** pour la ligne de sujet
5. **Corps explicatif** si nécessaire (72 caractères par ligne)

Consultez le [guide des commits](examples/good-commit-messages.md) pour plus de détails.

---

## Pull Requests

### Avant de Soumettre

- [ ] Mon code suit les conventions du projet
- [ ] J'ai testé mes modifications
- [ ] J'ai ajouté/mis à jour la documentation
- [ ] J'ai ajouté/mis à jour les tests si nécessaire
- [ ] Mes commits suivent les conventions
- [ ] J'ai synchronisé avec upstream/main
- [ ] Tous les tests passent
- [ ] J'ai relu mon code

### Template de PR

Utilisez le template fourni et remplissez toutes les sections :

```markdown
## Description

[Décrivez vos changements]

## Type de Changement

- [ ] Bug fix
- [ ] Nouvelle fonctionnalité
- [ ] Breaking change
- [ ] Documentation

## Changements Apportés

- Change 1
- Change 2

## Comment Tester

1. Étape 1
2. Étape 2

## Checklist

- [ ] Code testé
- [ ] Documentation mise à jour

## Issues Liées

Fixes #123
```

Consultez le [guide des PR](examples/pr-template.md) pour plus de détails.

### Taille de PR

**Préféré :**

- Petite : 1-100 lignes
- Moyenne : 100-400 lignes

**À éviter :**

- Grande : 1000+ lignes

Si votre PR est trop grande, découpez-la en plusieurs PRs plus petites.

### Revue de Code

**Si vous êtes l'auteur :**

- Répondez à tous les commentaires
- Faites les changements demandés
- Soyez ouvert aux suggestions
- Remerciez les reviewers

**Si vous êtes reviewer :**

- Soyez constructif et bienveillant
- Expliquez vos suggestions
- Approuvez si tout est bon
- Remerciez l'auteur

### Merge

Les mainteneurs mergeront votre PR après :

- Revue et approbation
- Tous les tests passent
- Aucun conflit
- Conventions respectées

---

## Issues

### Avant de Créer une Issue

1. **Cherchez d'abord** si l'issue existe déjà
2. **Vérifiez** la documentation
3. **Testez** avec la dernière version

### Créer une Issue

1. Utilisez le bon template :

   - 🐛 Bug Report
   - ✨ Feature Request
   - 📝 Documentation
   - ❓ Question
   - 🔧 Setup Issue

2. Remplissez toutes les sections
3. Soyez clair et concis
4. Ajoutez des captures d'écran
5. Incluez les logs d'erreur

### Bonne Issue

```markdown
## Description du Bug

Le bouton "Sauvegarder" ne fonctionne pas sur mobile.

## Étapes pour Reproduire

1. Ouvrir l'app sur mobile
2. Modifier le profil
3. Cliquer sur "Sauvegarder"
4. Observer qu'il ne se passe rien

## Comportement Attendu

Le profil devrait être sauvegardé.

## Environnement

- Device: iPhone 13
- OS: iOS 17.1
- Navigateur: Safari
```

Consultez le [guide des issues](examples/issue-templates.md) pour plus de détails.

---

## Questions

### Où Poser des Questions

- **Issues** - Pour bugs et features
- **Discussions** - Pour questions générales
- **Twitter** - [@eliaswalyba](https://twitter.com/eliaswalyba)

### Obtenir de l'Aide

Si vous êtes bloqué :

1. Lisez la documentation
2. Cherchez dans les issues/discussions
3. Posez votre question avec contexte
4. Soyez patient et respectueux

---

## Ressources pour Contributeurs

### Guides Internes

- [Cheat Sheet Git](docs/cheatsheet.md)
- [Guide d'Authentification](docs/authentication.md)
- [Nommage des Branches](examples/branch-naming.md)
- [Messages de Commit](examples/good-commit-messages.md)
- [Templates de PR](examples/pr-template.md)

### Ressources Externes

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com)
- [How to Contribute to Open Source](https://opensource.guide/how-to-contribute/)

---

## Reconnaissance

Nous reconnaissons toutes les contributions :

- Votre nom dans [participants/README.md](participants/README.md)
- Mention dans les release notes
- Badge "Contributor" sur votre profil GitHub

---

## Contact

**Mainteneur Principal :** Elias W. BA

- Twitter: [@eliaswalyba](https://twitter.com/eliaswalyba)
- GitHub: [@eliaswalyba](https://github.com/eliaswalyba)

---

## Note Importante

### Pour les Participants du Workshop

Si vous avez participé au workshop du 18 octobre 2025 et souhaitez simplement ajouter votre nom à la liste des participants :

1. Fork ce dépôt
2. Ajoutez votre nom dans `participants/README.md`
3. Créez une Pull Request

C'est un exercice parfait pour pratiquer le workflow de contribution ! Consultez [participants/README.md](participants/README.md) pour les instructions détaillées.

### Pour les Contributeurs Externes

Toutes les contributions sont les bienvenues ! Que vous soyez :

- Développeur débutant cherchant à faire sa première contribution
- Développeur expérimenté voulant améliorer le projet
- Rédacteur technique améliorant la documentation
- Designer proposant des améliorations visuelles

Nous apprécions votre temps et vos efforts ! 🙏

---

## 🎉 Merci !

Merci de contribuer au Git & GitHub Workshop ! Chaque contribution, grande ou petite, aide à améliorer ce projet et à aider plus de gens à apprendre Git.

**Happy Contributing! 🚀**

---

## License

En contribuant à ce projet, vous acceptez que vos contributions soient sous la même [licence MIT](LICENSE) que le projet.
