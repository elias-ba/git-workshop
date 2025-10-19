# Participants du Workshop Git & GitHub

Bienvenue ! Ce fichier est l'endroit idéal pour pratiquer votre première contribution open source.

## Exercice de Collaboration

Ajoutez votre nom à la liste ci-dessous en suivant les étapes !

## Comment Contribuer

### Étape 1 : Forker le Repository

1. Cliquez sur le bouton **"Fork"** en haut à droite de cette page
2. Cela crée une copie du repo sur votre compte GitHub

### Étape 2 : Cloner Votre Fork

```bash
# Remplacez VOTRE-USERNAME par votre nom d'utilisateur GitHub
git clone https://github.com/VOTRE-USERNAME/git-workshop.git
cd git-workshop
```

### Étape 3 : Créer une Branche

```bash
# Créez une branche avec votre nom
git checkout -b add-votre-nom
```

### Étape 4 : Ajouter Votre Nom

Ouvrez `participants/README.md` et ajoutez votre ligne dans la liste ci-dessous :

```markdown
- [Votre Nom](https://github.com/votre-username) - Ville, Pays
```

### Étape 5 : Commiter et Pousser

```bash
# Ajouter le fichier modifié
git add participants/README.md

# Créer un commit
git commit -m "Add [Votre Nom] to participants"

# Pousser vers votre fork
git push origin add-votre-nom
```

### Étape 6 : Créer une Pull Request

1. Allez sur votre fork sur GitHub
2. Cliquez sur **"Compare & pull request"**
3. Ajoutez un titre : `Add [Votre Nom] to participants`
4. Ajoutez une description (optionnel)
5. Cliquez sur **"Create pull request"**

**Félicitations ! 🎉 Vous venez de faire votre première Pull Request !**

---

## Liste des Participants

### Workshop du 18 Octobre 2025

- [Elias W. BA](https://github.com/eliaswalyba) - Thiès, Senegal - Facilitateur
- [Mark Landers](https://github.com/marklanders01) - Inspiration

<!-- Ajoutez votre nom ci-dessous -->

---

## Contributeurs

Merci à tous ceux qui ont contribué à ce workshop !

<!-- La liste sera automatiquement générée par GitHub -->

---

## Ressources

- [Guide complet des Pull Requests](https://docs.github.com/en/pull-requests)
- [Comment faire une bonne PR](../examples/pr-template.md)
- [Code of Conduct](https://docs.github.com/en/site-policy/github-terms/github-community-code-of-conduct)

---

**Note :** Si vous rencontrez des problèmes, n'hésitez pas à ouvrir une [issue](../../issues) ou à demander de l'aide sur Twitter [@eliaswalyba](https://twitter.com/eliaswalyba)
