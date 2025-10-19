# Git & GitHub Workshop

[![Workshop Date](https://img.shields.io/badge/Date-Oct%2018%2C%202025-blue)](https://calendar.app.google/HvwrRq8Tbq68a9...)
[![Duration](https://img.shields.io/badge/Duration-3%20Hours-green)](.)
[![Level](https://img.shields.io/badge/Level-Beginner-yellow)](.)
[![Language](https://img.shields.io/badge/Language-Français-red)](.)

> Apprenez Git et GitHub de zéro à héro en 3 heures. Workshop complet avec exercices pratiques et collaboration en temps réel.

## À Propos

Ce repository contient toutes les ressources du workshop Git & GitHub organisé le 18 octobre 2025. Que vous ayez participé au workshop ou que vous découvriez ce repo plus tard, vous trouverez ici tout ce dont vous avez besoin pour maîtriser Git et GitHub.

## Objectifs du Workshop

À la fin de ce workshop, vous serez capable de :

- Créer et gérer un dépôt Git
- Faire des commits et comprendre l'historique
- Travailler avec des branches
- Collaborer via GitHub (fork, PR, code review)
- Résoudre les conflits de merge
- Utiliser Git dans vos projets quotidiens

## Enregistrements

Les enregistrements du workshop sont disponibles sur YouTube :

- **[Partie 1 : Fondamentaux de Git](LIEN_YOUTUBE_PART1)** (1h30)
- **[Partie 2 : Branches & Collaboration](LIEN_YOUTUBE_PART2)** (1h30)

## Documentation

### Guides Complets

- **[Git Cheat Sheet](docs/cheatsheet.md)** - Toutes les commandes essentielles
- **[Guide d'Authentification](docs/authentication.md)** - Setup SSH et tokens GitHub
- **[Ressources Supplémentaires](docs/resources.md)** - Pour aller plus loin

### Exercices Pratiques

1. **[Exercice 1 : Les Bases](exercises/01-basics/)** - Init, add, commit, log
2. **[Exercice 2 : Branches](exercises/02-branches/)** - Créer, merger, gérer les branches
3. **[Exercice 3 : Collaboration](exercises/03-collaboration/)** - Fork, PR, code review

Chaque exercice inclut les instructions et les solutions.

### Examples

- **[Bons Messages de Commit](examples/good-commit-messages.md)**
- **[Nommage des Branches](examples/branch-naming.md)**
- **[Template de Pull Request](examples/pr-template.md)**

## Démarrage Rapide

### Prérequis

1. **Git installé** - [Télécharger Git](https://git-scm.com/downloads)
2. **Compte GitHub** - [Créer un compte](https://github.com/signup)
3. **Éditeur de code** - [VS Code recommandé](https://code.visualstudio.com)

### Vérification de l'Installation

```bash
# Vérifier Git
git --version

# Configurer Git
git config --global user.name "Votre Nom"
git config --global user.email "votre@email.com"

# Vérifier la configuration
git config --list
```

### Cloner ce Repository

```bash
# HTTPS
git clone https://github.com/VOTRE-USERNAME/git-workshop.git

# SSH
git clone git@github.com:VOTRE-USERNAME/git-workshop.git

# Entrer dans le dossier
cd git-workshop
```

## Contribuer

Ce repository est ouvert aux contributions ! Pour pratiquer Git, vous pouvez :

1. **Forker** ce repository
2. **Ajouter votre nom** dans `participants/README.md`
3. **Créer une Pull Request**

Consultez le guide détaillé dans [participants/README.md](participants/README.md).

## Progression

### Programme du Workshop

#### Heure 1 : Fondamentaux (9h00 - 10h30)

- Introduction à Git et GitHub
- Les trois zones de Git
- Créer et gérer des commits
- Inspecter l'historique
- Connexion à GitHub

#### Heure 2 : Branches (10h30 - 11h30)

- Comprendre les branches
- Créer et fusionner des branches
- Résoudre les conflits
- Push et pull

#### Heure 3 : Collaboration (11h30 - 12h30)

- Fork et Pull Requests
- Code review
- Bonnes pratiques
- Travail en équipe

## Commandes Essentielles

```bash
# Setup
git init                    # Initialiser un dépôt
git clone <url>            # Cloner un dépôt

# Workflow de base
git status                 # Voir l'état
git add <file>            # Ajouter au staging
git commit -m "message"   # Créer un commit
git log --oneline         # Voir l'historique

# Branches
git branch                # Lister les branches
git checkout -b <branch>  # Créer une branche
git merge <branch>        # Fusionner une branche

# Remote
git push origin main      # Pousser vers GitHub
git pull origin main      # Récupérer depuis GitHub
```

Consultez le [cheat sheet complet](docs/cheatsheet.md) pour toutes les commandes.

## Ressources Additionnelles

### Documentation Officielle

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com)

### Tutoriels Interactifs

- [Learn Git Branching](https://learngitbranching.js.org) - Visualisation interactive
- [GitHub Skills](https://skills.github.com) - Cours interactifs

### Livres

- [Pro Git](https://git-scm.com/book) - Gratuit, très complet

### Outils Utiles

- [GitKraken](https://www.gitkraken.com) - Interface graphique
- [GitHub Desktop](https://desktop.github.com) - Client GitHub officiel

## Facilitateur

**Elias W. BA**

- Twitter: [@eliaswalyba](https://twitter.com/eliaswalyba)
- GitHub: [@eliaswalyba](https://github.com/eliaswalyba)
- Email: [eliaswalyba@gmail.com]

## License

Ce projet est sous licence MIT - voir le fichier [LICENSE](LICENSE) pour plus de détails.

## Remerciements

Merci à tous les participants du workshop du 18 octobre 2025 ! Votre enthousiasme et vos questions ont rendu cette session exceptionnelle.

Un merci spécial à [@marklanders01](https://twitter.com/marklanders01) pour avoir inspiré ce workshop.

## Support

Des questions ? N'hésitez pas à :

- Ouvrir une [issue](../../issues)
- Me contacter sur [Twitter](https://twitter.com/eliaswalyba)
- Commenter sous les vidéos YouTube

---

⭐ Si ce workshop vous a été utile, n'hésitez pas à mettre une étoile sur ce repo !

**Happy Coding! 🚀**
