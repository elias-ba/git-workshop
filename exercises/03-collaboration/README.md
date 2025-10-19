# Exercice 3 : Collaboration avec GitHub

## Objectif

Apprendre à collaborer avec d'autres développeurs en utilisant GitHub : fork, pull requests, code review, et synchronisation.

**Durée estimée :** 40-50 minutes

---

## Ce que vous allez apprendre

- Forker un dépôt
- Cloner votre fork
- Ajouter un remote upstream
- Créer une Pull Request (PR)
- Faire du code review
- Synchroniser votre fork avec l'upstream
- Collaborer en équipe
- Gérer les conflits sur les PRs

---

## Prérequis

- Compte GitHub créé
- Git configuré avec votre nom et email
- Avoir terminé les exercices 1 et 2 (ou connaître les bases et les branches)
- Authentification GitHub configurée (SSH ou token)

---

## Instructions

### Partie 1 : Forker et Cloner un Dépôt

1. **Allez sur le dépôt du workshop sur GitHub**

   ```
   https://github.com/[VOTRE-FORMATEUR]/git-workshop
   ```

2. **Cliquez sur le bouton "Fork" en haut à droite**

   - Cela crée une copie du dépôt sur VOTRE compte GitHub
   - Attendez que le fork soit terminé

3. **Vérifiez que vous êtes sur VOTRE fork**

   ```
   URL devrait être : https://github.com/[VOTRE-USERNAME]/git-workshop
   ```

4. **Clonez VOTRE fork (pas l'original !)**

   ```bash
   # Remplacez VOTRE-USERNAME par votre nom d'utilisateur
   git clone https://github.com/VOTRE-USERNAME/git-workshop.git

   # OU avec SSH si vous avez configuré SSH
   git clone git@github.com:VOTRE-USERNAME/git-workshop.git
   ```

5. **Entrez dans le dossier**

   ```bash
   cd git-workshop
   ```

6. **Vérifiez les remotes**
   ```bash
   git remote -v
   # Vous devriez voir :
   # origin  https://github.com/VOTRE-USERNAME/git-workshop.git (fetch)
   # origin  https://github.com/VOTRE-USERNAME/git-workshop.git (push)
   ```

### Partie 2 : Ajouter le Remote Upstream

7. **Ajoutez le dépôt original comme upstream**

   ```bash
   # Remplacez FORMATEUR-USERNAME par le nom du formateur
   git remote add upstream https://github.com/FORMATEUR-USERNAME/git-workshop.git
   ```

8. **Vérifiez les remotes à nouveau**
   ```bash
   git remote -v
   # Vous devriez maintenant voir :
   # origin    https://github.com/VOTRE-USERNAME/git-workshop.git
   # upstream  https://github.com/FORMATEUR-USERNAME/git-workshop.git
   ```

**Comprendre origin vs upstream :**

- **origin** = votre fork (où vous pouvez push)
- **upstream** = dépôt original (lecture seule pour vous)

### Partie 3 : Créer une Branche pour Votre Contribution

9. **Assurez-vous d'être sur main et à jour**

   ```bash
   git checkout main
   git pull origin main
   ```

10. **Créez une branche pour votre contribution**

    ```bash
    # Utilisez votre nom dans le nom de la branche
    git checkout -b add-[votre-nom]-to-participants

    # Exemple :
    # git checkout -b add-elias-to-participants
    ```

### Partie 4 : Faire Votre Contribution

11. **Ouvrez le fichier participants/README.md**

    ```bash
    # Avec votre éditeur préféré
    code participants/README.md
    # OU
    nano participants/README.md
    ```

12. **Ajoutez votre nom à la liste**

    ```markdown
    - [Votre Nom](https://github.com/votre-username) - Ville, Pays

    Exemple :

    - [Elias W. BA](https://github.com/eliaswalyba) - Thiès, Senegal
    ```

13. **Vérifiez vos modifications**

    ```bash
    git diff
    # Vous devriez voir votre ligne en vert
    ```

14. **Stagez et commitez**
    ```bash
    git add participants/README.md
    git commit -m "Add [Votre Nom] to participants list"
    ```

### Partie 5 : Pousser vers Votre Fork

15. **Poussez votre branche vers votre fork**

    ```bash
    git push origin add-[votre-nom]-to-participants
    ```

16. **Si Git vous demande de configurer upstream pour la branche**
    ```bash
    git push -u origin add-[votre-nom]-to-participants
    ```

### Partie 6 : Créer une Pull Request

17. **Allez sur GitHub dans votre navigateur**

    ```
    https://github.com/VOTRE-USERNAME/git-workshop
    ```

18. **Vous devriez voir un message jaune : "Compare & pull request"**

    - Cliquez sur ce bouton
    - Si vous ne le voyez pas, allez dans l'onglet "Pull requests" → "New pull request"

19. **Vérifiez la direction de la PR**

    ```
    base repository: FORMATEUR-USERNAME/git-workshop  base: main
    head repository: VOTRE-USERNAME/git-workshop      compare: add-[votre-nom]-to-participants
    ```

20. **Remplissez le formulaire de la PR**

    - **Titre :** `Add [Votre Nom] to participants`
    - **Description :**

      ```markdown
      ## Description

      Ajout de mon nom à la liste des participants du workshop.

      ## Checklist

      - [x] J'ai ajouté mon nom
      - [x] Le lien vers mon profil GitHub est correct
      - [x] J'ai respecté le format demandé
      ```

21. **Créez la Pull Request**
    - Cliquez sur "Create pull request"
    - **Félicitations ! Vous venez de créer votre première PR ! 🎉**

### Partie 7 : Code Review (En Équipe)

**Si vous travaillez avec un partenaire, échangez les rôles :**

22. **Allez sur la PR de votre partenaire**

    - Sur GitHub, allez sur le dépôt original
    - Cliquez sur "Pull requests"
    - Trouvez la PR de votre partenaire

23. **Examinez les changements**

    - Cliquez sur l'onglet "Files changed"
    - Vérifiez que le format est correct
    - Vérifiez qu'il n'y a qu'une seule ligne ajoutée

24. **Laissez un commentaire**

    - Cliquez sur le "+" à côté d'une ligne
    - Laissez un commentaire positif : "Looks good! 👍" ou "LGTM (Looks Good To Me)"
    - Cliquez sur "Start a review"

25. **Approuvez la PR**
    - Cliquez sur "Review changes" en haut à droite
    - Sélectionnez "Approve"
    - Ajoutez un commentaire : "Great contribution!"
    - Cliquez sur "Submit review"

### Partie 8 : Synchroniser Votre Fork

26. **Retournez dans votre terminal**

    ```bash
    # Revenez sur main
    git checkout main
    ```

27. **Récupérez les derniers changements de l'upstream**

    ```bash
    git fetch upstream
    ```

28. **Mergez les changements de l'upstream dans votre main**

    ```bash
    git merge upstream/main
    ```

29. **Poussez vers votre fork pour le mettre à jour**
    ```bash
    git push origin main
    ```

**À faire régulièrement :** Avant de créer une nouvelle branche, synchronisez toujours votre fork !

### Partie 9 : Gérer les Conflits sur une PR

**Simulation d'un conflit :**

30. **Créez une nouvelle branche**

    ```bash
    git checkout main
    git checkout -b update-readme
    ```

31. **Modifiez le README.md**

    ```bash
    echo "" >> README.md
    echo "## Ma Contribution" >> README.md
    echo "J'ai participé au workshop Git !" >> README.md
    git add README.md
    git commit -m "Add my contribution section"
    ```

32. **Poussez vers votre fork**

    ```bash
    git push origin update-readme
    ```

33. **Créez une PR (comme avant)**

    - Allez sur GitHub
    - Créez une Pull Request depuis cette branche

34. **Si le formateur vous signale un conflit**

    ```bash
    # Synchronisez avec upstream
    git checkout main
    git fetch upstream
    git merge upstream/main

    # Revenez sur votre branche
    git checkout update-readme

    # Mergez main dans votre branche
    git merge main

    # Résolvez les conflits si nécessaire
    # Puis :
    git add .
    git commit -m "Resolve merge conflict"

    # Poussez pour mettre à jour la PR
    git push origin update-readme
    ```

---

## Challenges Bonus

### Challenge 1 : Contribuer à un Vrai Projet Open Source

Trouvez un projet "beginner-friendly" :

1. Allez sur [goodfirstissue.dev](https://goodfirstissue.dev)
2. Trouvez une issue marquée "good first issue"
3. Suivez le même processus : fork → branch → commit → push → PR

### Challenge 2 : Collaborer à Deux

Avec un partenaire :

1. L'un ajoute son nom dans `participants/README.md`
2. L'autre ajoute le sien en même temps
3. Essayez de merger les deux PRs
4. Le deuxième devra résoudre un conflit !

### Challenge 3 : Créer une PR Parfaite

Créez une PR qui inclut :

- Un titre descriptif
- Une description complète avec "Fixes #X" (si applicable)
- Des captures d'écran (si changement UI)
- Une checklist cochée
- Des commits bien nommés

### Challenge 4 : Devenir Reviewer

Reviewez 3 PRs d'autres participants :

- Laissez des commentaires constructifs
- Suggérez des améliorations
- Approuvez les bonnes PRs

---

## Ce que vous avez appris

- Forker un dépôt sur GitHub
- Cloner votre fork localement
- Configurer origin et upstream
- Créer une branche pour chaque contribution
- Pousser vers votre fork
- Créer une Pull Request
- Faire du code review
- Approuver ou demander des changements
- Synchroniser votre fork avec l'upstream
- Résoudre les conflits sur les PRs

---

## Commandes Utilisées

```bash
# Fork & Clone
git clone <url-de-votre-fork>
git remote add upstream <url-original>
git remote -v

# Synchronisation
git fetch upstream
git merge upstream/main
git pull origin main

# Contribution
git checkout -b nom-de-branche
git add <fichiers>
git commit -m "message"
git push origin nom-de-branche

# Mise à jour de PR
git checkout ma-branche
git merge main
git push origin ma-branche
```

---

## Concepts Clés

### Fork

Une copie d'un dépôt sur votre compte GitHub. Vous avez les droits complets sur votre fork.

```
Dépôt Original (upstream)     Votre Fork (origin)
    @formateur/repo      →      @vous/repo
    (lecture seule)             (lecture/écriture)
```

### Pull Request (PR)

Une demande pour merger vos changements dans le dépôt original.

**Workflow :**

```
1. Fork le dépôt
2. Clone votre fork
3. Créer une branche
4. Faire des commits
5. Push vers votre fork
6. Créer une PR
7. Code review
8. Merge (par les mainteneurs)
```

### Upstream

Le dépôt original dont vous avez forké. Vous ne pouvez que lire (fetch) depuis upstream, pas écrire (push).

### Code Review

Processus où d'autres développeurs examinent votre code avant qu'il soit mergé.

**Commentaires de review :**

- **Comment** : Simple commentaire
- **Approve** : Le code est bon, peut être mergé
- **Request changes** : Des modifications sont nécessaires

---

## Bonnes Pratiques de Collaboration

### Avant de Commencer

```bash
# Toujours partir d'une base à jour
git checkout main
git pull upstream main
git checkout -b ma-nouvelle-feature
```

### Pendant le Développement

```bash
# Commits fréquents et descriptifs
git add fichier.js
git commit -m "Add user validation function"

# Pas de commits géants
git commit -m "fix stuff"  # ❌ MAUVAIS
git commit -m "Fix email validation regex"  # ✅ BON
```

### Avant de Créer une PR

```bash
# Vérifier que votre branche est à jour
git fetch upstream
git merge upstream/main

# Tester votre code
# S'assurer qu'il n'y a pas de bugs

# Push
git push origin ma-branche
```

### Lors de la PR

**Titre de PR :**

```
✅ BON : "Add user authentication feature"
❌ MAUVAIS : "updates"
```

**Description de PR :**

```markdown
## Description

Ajout de l'authentification utilisateur avec JWT

## Changements

- Créer endpoint /api/auth/login
- Ajouter middleware d'authentification
- Tests unitaires pour auth

## Comment tester

1. Lancer le serveur
2. POST sur /api/auth/login
3. Vérifier le token JWT

Fixes #42
```

### Pendant le Review

**Si vous êtes l'auteur :**

- Répondez à tous les commentaires
- Soyez ouvert aux suggestions
- Faites les changements demandés rapidement
- Remerciez les reviewers

**Si vous êtes reviewer :**

- Soyez constructif et bienveillant
- Expliquez le "pourquoi" de vos commentaires
- Suggérez des solutions
- Reconnaissez le bon travail

### Après le Merge

```bash
# Supprimer la branche locale
git checkout main
git branch -d ma-branche

# Supprimer la branche remote
git push origin --delete ma-branche

# Mettre à jour votre fork
git pull upstream main
git push origin main
```

---

## Erreurs Courantes à Éviter

### Erreur 1 : Forker vs Cloner

```bash
# ❌ MAUVAIS : Cloner le dépôt original directement
git clone https://github.com/formateur/repo.git
# Vous ne pourrez pas push !

# ✅ BON : Fork d'abord sur GitHub, puis clone votre fork
git clone https://github.com/vous/repo.git
```

### Erreur 2 : Pousser vers le Mauvais Remote

```bash
# ❌ MAUVAIS : Essayer de push vers upstream
git push upstream main
# Permission denied !

# ✅ BON : Push vers votre fork (origin)
git push origin ma-branche
```

### Erreur 3 : Créer une PR depuis Main

```bash
# ❌ MAUVAIS : Travailler directement sur main
git checkout main
# faire des changements
git commit -m "changes"
git push origin main
# La PR sera un cauchemar à maintenir !

# ✅ BON : Toujours créer une branche
git checkout -b feature/ma-feature
# faire des changements
git commit -m "Add feature"
git push origin feature/ma-feature
```

### Erreur 4 : Fork Pas à Jour

```bash
# ❌ MAUVAIS : Oublier de synchroniser votre fork
# Vos PRs auront des conflits

# ✅ BON : Synchroniser régulièrement
git fetch upstream
git merge upstream/main
git push origin main
```

### Erreur 5 : Commits Non Descriptifs

```markdown
❌ MAUVAIS :

- "update"
- "fix"
- "changes"
- "asdfgh"

✅ BON :

- "Add email validation to signup form"
- "Fix null pointer error in user service"
- "Update dependencies to fix security vulnerabilities"
```

---

## Vocabulaire de la Collaboration

- **Fork** : Copie d'un dépôt sur votre compte
- **Clone** : Copie locale d'un dépôt
- **Upstream** : Dépôt original
- **Origin** : Votre fork
- **PR (Pull Request)** : Demande de merge
- **Review** : Examen du code
- **LGTM** : "Looks Good To Me" - code approuvé
- **WIP** : "Work In Progress" - travail en cours
- **Merge conflict** : Conflit à résoudre manuellement
- **Maintainer** : Personne qui gère le dépôt original
- **Contributor** : Personne qui contribue au projet

---

## Questions de Réflexion

1. Quelle est la différence entre fork et clone ?
2. Pourquoi créer une branche pour chaque contribution ?
3. Comment synchroniser votre fork avec l'upstream ?
4. Que faire si votre PR a des conflits ?
5. Quand utiliser "Request changes" vs "Approve" en review ?

Les réponses sont dans [solution.md](solution.md) !

---

## Checklist de Contribution Parfaite

Avant de créer votre PR, vérifiez :

- [ ] J'ai forké et cloné correctement
- [ ] J'ai créé une branche depuis main à jour
- [ ] Mes commits ont des messages descriptifs
- [ ] Mon code fonctionne et est testé
- [ ] J'ai synchronisé avec upstream/main
- [ ] Il n'y a pas de conflits
- [ ] Le titre de PR est clair
- [ ] La description est complète
- [ ] J'ai référencé les issues (si applicable)
- [ ] J'ai relu mon code avant de submit

---

## Ressources Complémentaires

- [GitHub Flow Guide](https://guides.github.com/introduction/flow/)
- [About Pull Requests](https://docs.github.com/en/pull-requests)
- [Forking a Repository](https://docs.github.com/en/get-started/quickstart/fork-a-repo)
- [First Contributions](https://github.com/firstcontributions/first-contributions)

---

## Félicitations !

Vous savez maintenant collaborer comme un pro ! Vous pouvez :

- Contribuer à n'importe quel projet open source
- Travailler en équipe sur GitHub
- Faire des code reviews professionnels
- Gérer les PRs et les conflits

**Prochaine étape :** Contribuez à un vrai projet open source ! 🚀

---

**Vous avez terminé les 3 exercices ! Vous êtes maintenant un Git Hero ! 🎓**
