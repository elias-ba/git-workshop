# Exercice 1 : Les Fondamentaux de Git

## Objectif

Apprendre à créer un dépôt Git, faire des commits, et inspecter l'historique.

**Durée estimée :** 20-30 minutes

---

## Ce que vous allez apprendre

- Initialiser un dépôt Git
- Créer des commits
- Voir l'historique
- Modifier des commits
- Comprendre les trois zones de Git

---

## Prérequis

- Git installé sur votre machine
- Un terminal ouvert
- Un éditeur de texte

---

## Instructions

### Partie 1 : Initialisation

1. **Créez un nouveau dossier pour votre projet**

   ```bash
   mkdir mon-premier-projet
   cd mon-premier-projet
   ```

2. **Initialisez Git**

   ```bash
   git init
   ```

3. **Vérifiez que Git est initialisé**

   ```bash
   ls -la
   # Vous devriez voir un dossier .git
   ```

4. **Vérifiez le statut**
   ```bash
   git status
   ```

### Partie 2 : Premier Commit

5. **Créez un fichier README.md**

   ```bash
   echo "# Mon Premier Projet" > README.md
   ```

6. **Vérifiez le statut**

   ```bash
   git status
   # README.md devrait apparaître en rouge (untracked)
   ```

7. **Ajoutez le fichier au staging**

   ```bash
   git add README.md
   ```

8. **Vérifiez le statut à nouveau**

   ```bash
   git status
   # README.md devrait maintenant être en vert (staged)
   ```

9. **Créez votre premier commit**

   ```bash
   git commit -m "Initial commit: add README"
   ```

10. **Vérifiez l'historique**
    ```bash
    git log
    # Vous devriez voir votre commit avec votre nom et email
    ```

### Partie 3 : Plus de Commits

11. **Ajoutez du contenu au README**

    ```bash
    echo "" >> README.md
    echo "## Description" >> README.md
    echo "Ceci est mon premier projet avec Git." >> README.md
    ```

12. **Voyez les différences**

    ```bash
    git diff
    # Vous verrez les lignes ajoutées en vert
    ```

13. **Créez un deuxième commit**

    ```bash
    git add README.md
    git commit -m "Add project description"
    ```

14. **Créez un nouveau fichier**

    ```bash
    echo "print('Hello, Git!')" > hello.py
    ```

15. **Créez un troisième commit**

    ```bash
    git add hello.py
    git commit -m "Add hello.py script"
    ```

16. **Vérifiez l'historique complet**
    ```bash
    git log --oneline
    # Vous devriez voir vos 3 commits
    ```

### Partie 4 : Modifier un Commit

17. **Oups ! Vous avez oublié quelque chose**

    ```bash
    echo "# Ceci est un commentaire" >> hello.py
    ```

18. **Ajoutez cette modification au dernier commit**

    ```bash
    git add hello.py
    git commit --amend --no-edit
    ```

19. **Vérifiez que le commit a été modifié**
    ```bash
    git log --oneline
    git show HEAD
    ```

### Partie 5 : Inspecter l'Historique

20. **Voyez l'historique de manière visuelle**

    ```bash
    git log --graph --oneline --all
    ```

21. **Voyez les détails d'un commit spécifique**

    ```bash
    git show HEAD~1
    # Cela montre le commit d'avant
    ```

22. **Voyez qui a modifié chaque ligne**
    ```bash
    git blame README.md
    ```

---

## Challenges Bonus

Si vous avez fini rapidement, essayez ces défis :

### Challenge 1 : Créer 5 commits

Créez 5 fichiers différents avec 5 commits différents. Utilisez des messages de commit descriptifs.

### Challenge 2 : Annuler un commit

Créez un commit, puis annulez-le avec `git reset HEAD~1`. Que se passe-t-il avec vos fichiers ?

### Challenge 3 : Historique détaillé

Explorez les options de `git log` :

```bash
git log --stat
git log -p
git log --since="1 hour ago"
```

### Challenge 4 : Différences entre commits

Comparez deux commits :

```bash
git diff HEAD~2 HEAD
```

---

## Ce que vous avez appris

- Initialiser un dépôt Git avec `git init`
- Ajouter des fichiers au staging avec `git add`
- Créer des commits avec `git commit`
- Voir l'historique avec `git log`
- Modifier le dernier commit avec `git commit --amend`
- Voir les différences avec `git diff`
- Comprendre le cycle : Working Directory → Staging → Repository

---

## Commandes Utilisées

```bash
# Initialisation
git init                          # Créer un dépôt Git
git status                        # Voir l'état actuel

# Commits
git add <fichier>                # Ajouter au staging
git commit -m "message"          # Créer un commit
git commit --amend --no-edit     # Modifier le dernier commit

# Historique
git log                          # Voir l'historique complet
git log --oneline                # Historique compact
git log --graph --oneline --all  # Historique visuel
git show <commit>                # Voir un commit spécifique

# Différences
git diff                         # Voir les changements non stagés
git blame <fichier>              # Voir qui a modifié chaque ligne
```

---

## Questions de Réflexion

1. Quelle est la différence entre la working directory et la staging area ?
2. Pourquoi utiliser `git commit --amend` au lieu de créer un nouveau commit ?
3. Comment voir les 5 derniers commits ?
4. Que se passe-t-il si vous modifiez un fichier après `git add` mais avant `git commit` ?

Les réponses sont dans [solution.md](solution.md) !

---

## Ressources

- [Documentation Git - Getting Started](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)
- [Visualizing Git](https://git-school.github.io/visualizing-git/)

---

## Notes

Prenez des notes sur ce que vous avez appris :

```
Vos notes ici...
```

---

**Prêt pour l'exercice suivant ?** → [Exercice 2 : Les Branches](../02-branches/README.md)
