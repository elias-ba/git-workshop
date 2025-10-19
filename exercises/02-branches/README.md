# Exercice 2 : Les Branches

## Objectif

Maîtriser la création, la gestion et la fusion des branches Git.

**Durée estimée :** 30-40 minutes

---

## Ce que vous allez apprendre

- Créer et changer de branche
- Travailler sur plusieurs branches en parallèle
- Fusionner des branches (merge)
- Résoudre des conflits de merge
- Supprimer des branches
- Visualiser l'historique des branches

---

## Prérequis

- Avoir terminé l'Exercice 1 (ou connaître les bases : init, add, commit)
- Un dépôt Git initialisé

---

## Instructions

### Partie 1 : Créer et Naviguer entre les Branches

1. **Créez un nouveau projet ou utilisez celui de l'exercice 1**

   ```bash
   mkdir projet-branches
   cd projet-branches
   git init
   ```

2. **Créez un fichier initial sur la branche main**

   ```bash
   echo "# Mon Projet" > README.md
   git add README.md
   git commit -m "Initial commit"
   ```

3. **Vérifiez sur quelle branche vous êtes**

   ```bash
   git branch
   # Vous devriez voir * main
   ```

4. **Créez une nouvelle branche pour une fonctionnalité**

   ```bash
   git branch feature/header
   ```

5. **Listez toutes les branches**

   ```bash
   git branch
   # Vous devriez voir :
   # * main
   #   feature/header
   ```

6. **Changez vers la nouvelle branche**

   ```bash
   git checkout feature/header
   # OU avec la nouvelle syntaxe
   git switch feature/header
   ```

7. **Vérifiez que vous avez changé de branche**
   ```bash
   git branch
   # Maintenant * devrait être sur feature/header
   ```

### Partie 2 : Travailler sur une Branche

8. **Créez un nouveau fichier dans votre branche**

   ```bash
   echo "<header>Mon Header</header>" > header.html
   git add header.html
   git commit -m "Add header component"
   ```

9. **Modifiez le README dans cette branche**

   ```bash
   echo "" >> README.md
   echo "## Header Feature" >> README.md
   echo "Nous avons ajouté un header." >> README.md
   git add README.md
   git commit -m "Update README with header info"
   ```

10. **Vérifiez l'historique de cette branche**
    ```bash
    git log --oneline
    # Vous devriez voir vos 3 commits
    ```

### Partie 3 : Comprendre la Séparation des Branches

11. **Retournez sur la branche main**

    ```bash
    git checkout main
    ```

12. **Listez les fichiers**

    ```bash
    ls
    # header.html n'existe PAS ici !
    ```

13. **Vérifiez le contenu du README**

    ```bash
    cat README.md
    # Les modifications de la branche feature/header n'y sont pas
    ```

14. **Voyez l'historique de main**
    ```bash
    git log --oneline
    # Vous ne voyez que le commit initial
    ```

**Observation importante :** Les fichiers et commits de `feature/header` n'existent que sur cette branche. C'est ça la magie des branches !

### Partie 4 : Créer une Deuxième Branche

15. **Créez et changez vers une autre branche (en une commande)**

    ```bash
    git checkout -b feature/footer
    ```

16. **Créez un fichier footer**

    ```bash
    echo "<footer>Mon Footer</footer>" > footer.html
    git add footer.html
    git commit -m "Add footer component"
    ```

17. **Visualisez toutes vos branches**
    ```bash
    git log --graph --oneline --all
    # Vous verrez l'arbre des branches
    ```

### Partie 5 : Merger une Branche (Fast-Forward)

18. **Retournez sur main**

    ```bash
    git checkout main
    ```

19. **Mergez la branche footer dans main**

    ```bash
    git merge feature/footer
    # Vous verrez "Fast-forward"
    ```

20. **Vérifiez que footer.html est maintenant dans main**

    ```bash
    ls
    # footer.html est là !
    cat footer.html
    ```

21. **Vérifiez l'historique**
    ```bash
    git log --oneline
    # Le commit de footer est maintenant dans main
    ```

### Partie 6 : Merger avec un Merge Commit

22. **Mergez la branche header dans main**

    ```bash
    git merge feature/header
    ```

23. **Regardez le message de commit automatique**

    - Git ouvrira un éditeur avec un message par défaut
    - Sauvegardez et fermez (`:wq` dans vim, ou Ctrl+X dans nano)

24. **Vérifiez que header.html est maintenant dans main**

    ```bash
    ls
    # header.html et footer.html sont tous les deux là !
    ```

25. **Visualisez l'historique graphique**
    ```bash
    git log --graph --oneline --all
    # Vous verrez le merge commit avec deux parents
    ```

### Partie 7 : Créer un Conflit de Merge

26. **Créez une branche pour modifier le README**

    ```bash
    git checkout -b update-readme-v1
    echo "" >> README.md
    echo "Version 1 du texte" >> README.md
    git add README.md
    git commit -m "Update README version 1"
    ```

27. **Retournez sur main et créez une autre branche**

    ```bash
    git checkout main
    git checkout -b update-readme-v2
    echo "" >> README.md
    echo "Version 2 du texte" >> README.md
    git add README.md
    git commit -m "Update README version 2"
    ```

28. **Mergez la première branche dans main**

    ```bash
    git checkout main
    git merge update-readme-v1
    ```

29. **Essayez de merger la deuxième branche**
    ```bash
    git merge update-readme-v2
    # CONFLIT ! 🔥
    ```

### Partie 8 : Résoudre le Conflit

30. **Vérifiez le statut**

    ```bash
    git status
    # Vous verrez "both modified: README.md"
    ```

31. **Ouvrez README.md dans votre éditeur**

    ```bash
    cat README.md
    # Vous verrez quelque chose comme :
    # <<<<<<< HEAD
    # Version 1 du texte
    # =======
    # Version 2 du texte
    # >>>>>>> update-readme-v2
    ```

32. **Résolvez le conflit**

    - Éditez le fichier pour garder les deux versions :

    ```markdown
    # Mon Projet

    ## Header Feature

    Nous avons ajouté un header.

    Version 1 du texte
    Version 2 du texte
    ```

    - Supprimez les marqueurs `<<<<<<<`, `=======`, et `>>>>>>>`

33. **Marquez le conflit comme résolu**

    ```bash
    git add README.md
    ```

34. **Finalisez le merge**

    ```bash
    git commit -m "Resolve merge conflict between v1 and v2"
    ```

35. **Vérifiez que le merge est terminé**
    ```bash
    git status
    # Devrait dire "nothing to commit"
    ```

### Partie 9 : Nettoyer les Branches

36. **Listez toutes les branches**

    ```bash
    git branch
    ```

37. **Supprimez les branches mergées**

    ```bash
    git branch -d feature/header
    git branch -d feature/footer
    git branch -d update-readme-v1
    git branch -d update-readme-v2
    ```

38. **Vérifiez qu'il ne reste que main**

    ```bash
    git branch
    # Seulement * main
    ```

39. **Visualisez l'historique final**
    ```bash
    git log --graph --oneline --all
    ```

---

## Challenges Bonus

### Challenge 1 : Workflow Complet

Simulez un vrai workflow de développement :

1. Créez une branche `feature/navbar`
2. Ajoutez 3 commits dedans
3. Créez une branche `bugfix/typo` depuis main
4. Faites 1 commit dedans
5. Mergez les deux branches dans main
6. Supprimez les branches

### Challenge 2 : Résolution de Conflit Complexe

1. Créez deux branches qui modifient le MÊME fichier aux MÊMES lignes
2. Mergez-les pour créer un conflit
3. Résolvez le conflit en gardant le meilleur des deux versions

### Challenge 3 : Annuler un Merge

1. Créez une branche et mergez-la dans main
2. Réalisez que c'était une erreur
3. Utilisez `git reset --hard HEAD~1` pour annuler le merge
4. ⚠️ ATTENTION : Cette commande supprime des commits !

### Challenge 4 : Visualisation

Utilisez ces commandes pour mieux comprendre vos branches :

```bash
git log --graph --oneline --decorate --all
git log --graph --pretty=format:'%h - %s (%ar) <%an>'
```

---

## Ce que vous avez appris

- Créer une branche avec `git branch` ou `git checkout -b`
- Changer de branche avec `git checkout` ou `git switch`
- Comprendre que chaque branche a son propre état
- Merger des branches avec `git merge`
- Comprendre Fast-forward vs Merge commit
- Créer et résoudre des conflits de merge
- Supprimer des branches avec `git branch -d`
- Visualiser l'historique avec `git log --graph`

---

## Commandes Utilisées

```bash
# Créer et naviguer
git branch <nom>                 # Créer une branche
git branch                       # Lister les branches
git checkout <nom>               # Changer de branche
git checkout -b <nom>            # Créer et changer
git switch <nom>                 # Changer (nouvelle syntaxe)
git switch -c <nom>              # Créer et changer (nouvelle syntaxe)

# Merger
git merge <branche>              # Merger une branche
git merge --abort                # Annuler un merge en cours

# Nettoyer
git branch -d <nom>              # Supprimer une branche (safe)
git branch -D <nom>              # Forcer la suppression

# Visualiser
git log --graph --oneline --all  # Voir l'arbre des branches
git branch -v                    # Branches avec dernier commit
```

---

## Concepts Clés

### Fast-Forward Merge

Quand la branche cible n'a pas avancé depuis la création de la branche à merger, Git déplace simplement le pointeur.

```
Avant :      main: A---B
                         \
             feature:     C---D

Après :      main: A---B---C---D
```

### Merge Commit

Quand les deux branches ont avancé, Git crée un commit de merge avec deux parents.

```
Avant :      main: A---B---E
                         \
             feature:     C---D

Après :      main: A---B---E---M
                         \     /
             feature:     C---D
```

### Conflit de Merge

Se produit quand les deux branches ont modifié les mêmes lignes d'un fichier.

**Marqueurs de conflit :**

```
<<<<<<< HEAD
Votre version (branche actuelle)
=======
Leur version (branche à merger)
>>>>>>> nom-de-la-branche
```

---

## Questions de Réflexion

1. Quelle est la différence entre `git branch` et `git checkout -b` ?
2. Pourquoi est-il important de supprimer les branches après merge ?
3. Comment éviter les conflits de merge ?
4. Que se passe-t-il avec les fichiers quand vous changez de branche ?
5. Quelle est la différence entre Fast-forward et Merge commit ?

Les réponses sont dans [solution.md](solution.md) !

---

## Erreurs Courantes à Éviter

```bash
# ❌ MAUVAIS : Créer une branche depuis une mauvaise branche
git checkout feature/ancienne
git checkout -b feature/nouvelle  # Nouvelle branche part de l'ancienne !

# ✅ BON : Toujours partir de main à jour
git checkout main
git pull origin main
git checkout -b feature/nouvelle
```

```bash
# ❌ MAUVAIS : Essayer de changer de branche avec des modifications non commitées
git checkout autre-branche
# Erreur !

# ✅ BON : Commiter ou stasher d'abord
git add .
git commit -m "WIP"
# OU
git stash
git checkout autre-branche
```

```bash
# ❌ MAUVAIS : Forcer la suppression sans vérifier
git branch -D feature/importante  # Perte de travail !

# ✅ BON : Utiliser -d qui refuse si non mergée
git branch -d feature/importante
# Git vous avertira si vous risquez de perdre du travail
```

---

## Notes Personnelles

Espace pour vos notes :

```
Ce que j'ai appris aujourd'hui...




Difficultés rencontrées...




Questions à approfondir...
```

---

## Ressources Complémentaires

- [Git Branching - Basic Branching and Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
- [Learn Git Branching](https://learngitbranching.js.org) - Visualisation interactive
- [Atlassian Git Branching Tutorial](https://www.atlassian.com/git/tutorials/using-branches)

---

**Félicitations ! Vous maîtrisez maintenant les branches Git ! 🎉**

**Prêt pour le dernier exercice ?** → [Exercice 3 : Collaboration](../03-collaboration/README.md)
