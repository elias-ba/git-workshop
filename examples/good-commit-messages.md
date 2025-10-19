# Guide des Bons Messages de Commit

## Pourquoi les Bons Messages de Commit Sont Importants

Un bon message de commit :

- Explique le QUOI et le POURQUOI (pas le comment)
- Aide les autres développeurs à comprendre l'historique
- Facilite le debugging et le code review
- Rend le projet professionnel

**Pensez-y comme ça :** Vous revenez sur le code 6 mois plus tard. Votre message de commit vous aide-t-il à comprendre ce qui a été fait et pourquoi ?

---

## Format Recommandé

### Structure de Base

```
Type: Courte description (50 caractères max)

Explication détaillée si nécessaire (72 caractères par ligne)

- Point clé 1
- Point clé 2
- Point clé 3
```

### Les 7 Règles d'Or

1. **Séparer le sujet du corps** avec une ligne vide
2. **Limiter le sujet à 50 caractères**
3. **Capitaliser la première lettre** du sujet
4. **Ne pas terminer le sujet** par un point
5. **Utiliser l'impératif** dans le sujet
6. **Limiter le corps à 72 caractères** par ligne
7. **Expliquer le QUOI et le POURQUOI** dans le corps

---

## Exemples de BONS Messages

### Messages Courts et Descriptifs

```bash
git commit -m "Ajouter validation du formulaire de connexion"

git commit -m "Corriger le bug d'affichage sur mobile"

git commit -m "Refactoriser la fonction de calcul de prix"

git commit -m "Supprimer le code mort dans auth.js"

git commit -m "Mettre à jour les dépendances de sécurité"
```

### Messages Avec Corps

```bash
git commit -m "Optimiser les requêtes de base de données

Les requêtes N+1 causaient des problèmes de performance
sur la page des utilisateurs. Cette solution utilise
eager loading pour réduire le nombre de requêtes.

Performance avant: 150ms
Performance après: 25ms"
```

```bash
git commit -m "Ajouter authentification à deux facteurs

Implémente 2FA via TOTP pour améliorer la sécurité.
Les utilisateurs peuvent activer 2FA dans leurs paramètres.

- Ajouter génération de codes QR
- Implémenter vérification TOTP
- Ajouter codes de backup

Fixes #234"
```

### Messages Avec Références

```bash
# Référencer une issue
git commit -m "Corriger crash lors de l'upload (fixes #123)"

# Fermer automatiquement une issue
git commit -m "Ajouter export PDF (closes #456)"

# Référencer plusieurs issues
git commit -m "Améliorer performance (related to #789, #790)"
```

---

## Exemples de MAUVAIS Messages

### Trop Vague

```bash
# ❌ MAUVAIS
git commit -m "update"
git commit -m "fix"
git commit -m "changes"
git commit -m "stuff"
git commit -m "work in progress"
git commit -m "."
```

**Pourquoi c'est mauvais :** Impossible de comprendre ce qui a été fait.

**✅ MIEUX :**

```bash
git commit -m "Mettre à jour la version de React à 18.2"
git commit -m "Corriger bug de validation email"
git commit -m "Modifier le style du header"
```

### Trop Long

```bash
# ❌ MAUVAIS
git commit -m "Ajouter la fonctionnalité de connexion avec validation des champs, gestion des erreurs, redirection après succès et affichage des messages d'erreur"
```

**Pourquoi c'est mauvais :** Difficile à lire dans `git log --oneline`.

**✅ MIEUX :**

```bash
git commit -m "Ajouter page de connexion avec validation

- Validation des champs email et password
- Gestion des erreurs serveur
- Redirection vers dashboard après succès
- Messages d'erreur utilisateur-friendly"
```

### Pas Descriptif

```bash
# ❌ MAUVAIS
git commit -m "oops"
git commit -m "fix bug"
git commit -m "test"
git commit -m "final version"
git commit -m "really final version this time"
```

**✅ MIEUX :**

```bash
git commit -m "Corriger typo dans message d'erreur"
git commit -m "Corriger validation du format de date"
git commit -m "Ajouter tests unitaires pour auth"
```

---

## Types de Commits (Convention)

Utiliser des préfixes pour catégoriser vos commits :

```bash
feat: Ajouter nouvelle fonctionnalité
fix: Corriger un bug
docs: Modifier la documentation
style: Changements de style (format, espace)
refactor: Refactorisation du code
test: Ajouter ou modifier des tests
chore: Tâches de maintenance
perf: Amélioration de performance
```

### Exemples

```bash
git commit -m "feat: Ajouter export CSV des utilisateurs"
git commit -m "fix: Corriger calcul de TVA"
git commit -m "docs: Mettre à jour le README"
git commit -m "style: Formater le code selon Prettier"
git commit -m "refactor: Extraire logique de validation"
git commit -m "test: Ajouter tests pour login"
git commit -m "chore: Mettre à jour les dépendances"
git commit -m "perf: Optimiser chargement des images"
```

---

## Utilisation des Emojis (Optionnel)

Certaines équipes utilisent des emojis pour plus de visibilité :

```bash
✨ feat: Nouvelle fonctionnalité
🐛 fix: Bug fix
📝 docs: Documentation
💄 style: UI/Style
♻️ refactor: Refactorisation
✅ test: Tests
🔧 chore: Configuration
⚡ perf: Performance
🔒 security: Sécurité
```

### Exemples

```bash
git commit -m "✨ Ajouter dark mode"
git commit -m "🐛 Corriger bug de pagination"
git commit -m "📝 Ajouter documentation API"
git commit -m "⚡ Optimiser temps de chargement"
```

---

## Templates de Messages

### Nouvelle Fonctionnalité

```
feat: [Titre de la fonctionnalité]

[Description de ce que fait la fonctionnalité]

[Pourquoi elle a été ajoutée]

[Détails techniques importants si nécessaire]
```

### Correction de Bug

```
fix: [Description du bug corrigé]

Le bug se produisait quand [contexte]

Solution: [explication courte]

Fixes #[numéro-issue]
```

### Refactorisation

```
refactor: [Partie du code refactorisée]

Raison: [pourquoi le refactoring était nécessaire]

Changements:
- [changement 1]
- [changement 2]
```

---

## Vérifier Vos Messages

Avant de commiter, posez-vous ces questions :

1. **Est-ce que quelqu'un peut comprendre ce que j'ai fait sans lire le code ?**
2. **Est-ce que j'ai expliqué le POURQUOI, pas seulement le QUOI ?**
3. **Est-ce que le message est utile dans 6 mois ?**
4. **Est-ce que le sujet fait moins de 50 caractères ?**
5. **Est-ce que j'utilise l'impératif ?** ("Ajouter" pas "Ajouté" ou "Ajoute")

---

## Outils Utiles

### Commitizen (CLI)

Aide à écrire des commits structurés :

```bash
npm install -g commitizen
git cz  # Au lieu de git commit
```

### Commitlint

Vérifie que vos messages suivent les conventions :

```bash
npm install --save-dev @commitlint/cli @commitlint/config-conventional
```

---

## Exemples du Monde Réel

### Linux Kernel

```
mm: fix race in anon_vma prepare/reuse patch

The locking in anon_vma_prepare() and anon_vma_fork() is
complicated due to the need to handle private vma lists.
```

### React

```
feat: add useTransition hook

Adds a new hook to help coordinate with Concurrent Mode.
The hook returns an array with a startTransition function
and a pending state indicator.

The startTransition function wraps state updates that may
cause a component to suspend.
```

### VS Code

```
fix: prevent multiple language service restarts

Fixes a race condition that could cause TypeScript language
service to restart multiple times when switching between
branches.

Fixes #12345
```

---

## Résumé : Le Message de Commit Parfait

```bash
# Format court
git commit -m "Type: Description courte et précise"

# Format complet
git commit -m "Type: Description courte et précise

Explication détaillée du changement et de sa raison.

- Point important 1
- Point important 2

Fixes #123"
```

---

## Exercice Pratique

Transformez ces mauvais messages en bons messages :

1. ❌ `git commit -m "update"`

   - ✅ Votre version : **\*\*\*\***\_**\*\*\*\***

2. ❌ `git commit -m "fix bug"`

   - ✅ Votre version : **\*\*\*\***\_**\*\*\*\***

3. ❌ `git commit -m "changes to login"`
   - ✅ Votre version : **\*\*\*\***\_**\*\*\*\***

Voir les [solutions](../exercises/solutions/commit-messages-solutions.md)

---

## Ressources

- [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [Angular Commit Guidelines](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#commit)

---

**Remember:** Un bon message de commit est un cadeau à votre futur moi et à votre équipe !
