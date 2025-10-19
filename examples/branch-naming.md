# Guide de Nommage des Branches

## Pourquoi des Conventions de Nommage ?

Un bon nom de branche :

- Indique immédiatement le but de la branche
- Facilite la navigation dans le dépôt
- Améliore la collaboration en équipe
- Rend l'historique Git plus lisible
- Permet l'automatisation (CI/CD, hooks)

**Principe de base :** Votre nom de branche doit expliquer ce que fait la branche en quelques mots.

---

## Format Général

### Structure Recommandée

```
<type>/<description-courte>

Exemples :
feature/user-authentication
bugfix/login-validation
hotfix/security-patch
```

### Avec Numéro d'Issue (Optionnel)

```
<type>/<issue-number>-<description>

Exemples :
feature/123-user-authentication
bugfix/456-login-validation
```

---

## Types de Branches

### feature/ - Nouvelles Fonctionnalités

Pour développer de nouvelles fonctionnalités.

```bash
feature/user-profile
feature/payment-integration
feature/dark-mode
feature/email-notifications
feature/search-functionality
```

**Quand utiliser :**

- Ajout d'une nouvelle fonctionnalité
- Développement d'un nouveau module
- Création de nouvelles pages/composants

---

### bugfix/ - Corrections de Bugs

Pour corriger des bugs non critiques.

```bash
bugfix/login-error
bugfix/date-formatting
bugfix/image-upload
bugfix/navigation-issue
bugfix/form-validation
```

**Quand utiliser :**

- Bug trouvé en développement
- Bug rapporté par les utilisateurs
- Problème qui peut attendre le prochain déploiement

---

### hotfix/ - Corrections Urgentes

Pour corrections critiques en production.

```bash
hotfix/security-vulnerability
hotfix/payment-failure
hotfix/data-loss
hotfix/server-crash
```

**Quand utiliser :**

- Bug critique en production
- Problème de sécurité
- Perte de données
- Service down

**Important :** Hotfix part généralement de `main` (ou `production`) et merge directement dedans.

---

### refactor/ - Refactorisation

Pour améliorer le code sans changer les fonctionnalités.

```bash
refactor/user-service
refactor/database-queries
refactor/component-structure
refactor/api-endpoints
```

**Quand utiliser :**

- Amélioration de la structure du code
- Optimisation de performance
- Nettoyage du code
- Réduction de la dette technique

---

### docs/ - Documentation

Pour modifications de la documentation uniquement.

```bash
docs/api-documentation
docs/readme-update
docs/installation-guide
docs/contributing-guidelines
```

**Quand utiliser :**

- Mise à jour du README
- Ajout de commentaires
- Documentation de l'API
- Guides utilisateur

---

### test/ - Tests

Pour ajout ou modification de tests.

```bash
test/unit-tests-auth
test/integration-tests
test/e2e-checkout
test/api-tests
```

**Quand utiliser :**

- Ajout de tests unitaires
- Tests d'intégration
- Tests end-to-end
- Amélioration de la couverture de tests

---

### style/ - Style et Formatage

Pour changements de style (UI) ou formatage de code.

```bash
style/button-design
style/header-layout
style/code-formatting
style/responsive-mobile
```

**Quand utiliser :**

- Changements CSS/styles
- Formatage du code (Prettier, ESLint)
- Ajustements visuels
- Améliorations UI

---

### chore/ - Tâches de Maintenance

Pour tâches de maintenance et configuration.

```bash
chore/update-dependencies
chore/configure-webpack
chore/setup-ci
chore/clean-unused-files
```

**Quand utiliser :**

- Mise à jour de dépendances
- Configuration d'outils
- Scripts de build
- Nettoyage du projet

---

### experiment/ - Expérimentations

Pour tester des idées sans engagement.

```bash
experiment/new-architecture
experiment/alternative-ui
experiment/performance-test
experiment/ai-integration
```

**Quand utiliser :**

- Proof of concept
- Tester une nouvelle technologie
- Expérimentations non garanties de merger

---

## Règles de Nommage

### Règle 1 : Utiliser des Minuscules

```bash
# ✅ BON
feature/user-authentication

# ❌ MAUVAIS
Feature/User-Authentication
feature/UserAuthentication
FEATURE/USER_AUTHENTICATION
```

### Règle 2 : Utiliser des Tirets (pas d'espaces ni underscores)

```bash
# ✅ BON
feature/user-authentication
bugfix/login-form-validation

# ❌ MAUVAIS
feature/user_authentication
feature/user authentication
feature/userAuthentication
```

### Règle 3 : Être Descriptif mais Concis

```bash
# ✅ BON
feature/user-profile
bugfix/email-validation
refactor/auth-service

# ❌ TROP LONG
feature/implement-complete-user-profile-page-with-avatar-upload-and-settings

# ❌ TROP VAGUE
feature/stuff
bugfix/fix
feature/update
```

**Sweet spot :** 2-4 mots maximum

### Règle 4 : Utiliser des Verbes d'Action (Optionnel)

```bash
# ✅ BON
feature/add-user-profile
bugfix/fix-login-error
refactor/improve-performance

# Aussi acceptable :
feature/user-profile
bugfix/login-error
refactor/performance
```

### Règle 5 : Préfixer avec Numéro d'Issue si Applicable

```bash
# ✅ BON
feature/123-user-authentication
bugfix/456-login-validation
hotfix/789-security-patch

# Format alternatif :
feature/GH-123-user-authentication
feature/JIRA-456-user-authentication
```

### Règle 6 : Éviter les Caractères Spéciaux

```bash
# ✅ BON
feature/user-auth

# ❌ MAUVAIS
feature/user@auth
feature/user#auth
feature/user&auth
feature/user%auth
```

**Caractères acceptés :** lettres (a-z), chiffres (0-9), tirets (-), slashes (/)

---

## Patterns Courants

### Pattern 1 : Type/Description

```bash
feature/dark-mode
bugfix/responsive-layout
hotfix/payment-error
```

**Le plus simple et le plus courant.**

### Pattern 2 : Type/Issue-Description

```bash
feature/123-dark-mode
bugfix/456-responsive-layout
hotfix/789-payment-error
```

**Idéal pour lier aux issues/tickets.**

### Pattern 3 : Type/Module-Description

```bash
feature/auth-social-login
bugfix/payment-validation
refactor/api-error-handling
```

**Utile pour grands projets avec modules distincts.**

### Pattern 4 : Username/Type/Description

```bash
elias/feature/dark-mode
john/bugfix/login-error
marie/refactor/database
```

**Pour équipes où plusieurs personnes travaillent sur des features similaires.**

---

## Exemples Réels par Scénario

### Scénario : E-commerce

```bash
feature/shopping-cart
feature/product-filters
feature/checkout-process
bugfix/price-calculation
hotfix/payment-gateway
refactor/product-catalog
test/cart-functionality
```

### Scénario : Application Mobile

```bash
feature/push-notifications
feature/offline-mode
feature/biometric-auth
bugfix/camera-permissions
hotfix/crash-on-startup
style/dark-theme
```

### Scénario : API Backend

```bash
feature/user-endpoints
feature/authentication-jwt
bugfix/rate-limiting
hotfix/database-connection
refactor/error-middleware
test/api-integration
docs/api-documentation
```

### Scénario : Site Web

```bash
feature/contact-form
feature/blog-section
bugfix/mobile-menu
style/homepage-redesign
refactor/css-architecture
docs/content-guidelines
```

---

## Conventions par Équipe/Entreprise

### Convention GitFlow

```bash
feature/nom-feature
release/version-number
hotfix/nom-hotfix
support/nom-support

Exemples :
feature/user-dashboard
release/1.2.0
hotfix/critical-bug
```

### Convention GitHub Flow (Simplifié)

```bash
Pas de préfixe obligatoire, mais descriptif

Exemples :
user-authentication
fix-login-bug
update-readme
```

### Convention GitLab Flow

```bash
Similaire à GitFlow mais avec environnements

feature/nom-feature
production/fix
staging/test

Exemples :
feature/payment-integration
production/security-patch
staging/performance-test
```

---

## Anti-Patterns (À Éviter)

### Noms Trop Génériques

```bash
# MAUVAIS
feature/new-stuff
bugfix/fix
feature/update
feature/changes
feature/test
```

**Pourquoi c'est mauvais :** Impossible de savoir ce que fait la branche.

### Noms Trop Longs

```bash
# MAUVAIS
feature/implement-complete-user-authentication-system-with-email-verification-and-password-reset-functionality
```

**Pourquoi c'est mauvais :** Difficile à taper, difficile à lire.

### Pas de Type

```bash
# MAUVAIS
user-authentication
login-bug
new-feature
```

**Pourquoi c'est mauvais :** On ne sait pas si c'est une feature, un bug, etc.

### Mélange de Conventions

```bash
# MAUVAIS dans un même projet
feature/user-auth
Fix_login_bug
NEW-FEATURE-payment
UserProfile
```

**Pourquoi c'est mauvais :** Incohérent, donne une impression d'amateurisme.

### Caractères Spéciaux

```bash
# MAUVAIS
feature/user@auth
feature/login#bug
feature/payment$system
```

**Pourquoi c'est mauvais :** Peut causer des problèmes avec Git ou les shells.

### Espaces

```bash
# MAUVAIS
feature/user authentication
bugfix/login error
```

**Pourquoi c'est mauvais :** Problèmes avec la ligne de commande.

---

## Exercice Pratique

Transformez ces mauvais noms en bons noms :

### Exercice 1

```bash
# ❌ MAUVAIS
new-stuff

# ✅ VOTRE PROPOSITION
___________________________________
```

### Exercice 2

```bash
# ❌ MAUVAIS
fix

# ✅ VOTRE PROPOSITION
___________________________________
```

### Exercice 3

```bash
# ❌ MAUVAIS
Feature_User_Profile

# ✅ VOTRE PROPOSITION
___________________________________
```

### Exercice 4

```bash
# ❌ MAUVAIS
implement-complete-user-authentication-system-with-jwt

# ✅ VOTRE PROPOSITION
___________________________________
```

### Exercice 5

```bash
# ❌ MAUVAIS
update

# ✅ VOTRE PROPOSITION
___________________________________
```

<details>
<summary>Voir les solutions</summary>

### Solution 1

```bash
feature/user-dashboard
# OU
feature/admin-panel
# (selon ce que c'est)
```

### Solution 2

```bash
bugfix/login-validation
# OU
hotfix/payment-error
# (selon le contexte)
```

### Solution 3

```bash
feature/user-profile
```

### Solution 4

```bash
feature/jwt-authentication
# OU
feature/user-auth
```

### Solution 5

```bash
chore/update-dependencies
# OU
docs/update-readme
# (selon ce qui est mis à jour)
```

</details>

---

## Configuration d'Équipe

### Créer un Fichier de Convention

Créez `.github/BRANCH_NAMING.md` dans votre projet :

```markdown
# Convention de Nommage des Branches

Notre équipe utilise le format suivant :

`<type>/<description>`

## Types acceptés :

- feature/ - Nouvelles fonctionnalités
- bugfix/ - Corrections de bugs
- hotfix/ - Corrections urgentes
- refactor/ - Refactorisation
- docs/ - Documentation
- test/ - Tests
- style/ - Style/UI
- chore/ - Maintenance

## Règles :

1. Minuscules uniquement
2. Tirets pour séparer les mots
3. 2-4 mots maximum
4. Descriptif et clair

## Exemples :

- feature/user-authentication
- bugfix/login-validation
- hotfix/security-patch
```

### Git Hooks pour Validation

Créez `.git/hooks/pre-push` pour valider les noms :

```bash
#!/bin/bash

BRANCH_NAME=$(git symbolic-ref --short HEAD)
VALID_BRANCH_REGEX="^(feature|bugfix|hotfix|refactor|docs|test|style|chore)\/[a-z0-9\-]+$"

if ! [[ $BRANCH_NAME =~ $VALID_BRANCH_REGEX ]]; then
    echo "❌ Nom de branche invalide : $BRANCH_NAME"
    echo "✅ Format attendu : <type>/<description>"
    echo "   Exemples : feature/user-auth, bugfix/login-error"
    exit 1
fi

exit 0
```

Rendez-le exécutable :

```bash
chmod +x .git/hooks/pre-push
```

---

## Checklist de Nommage

Avant de créer une branche, vérifiez :

- [ ] J'ai utilisé un préfixe de type (feature/, bugfix/, etc.)
- [ ] Le nom est en minuscules
- [ ] J'ai utilisé des tirets (pas d'espaces ni underscores)
- [ ] Le nom fait 2-4 mots maximum
- [ ] Le nom est descriptif et clair
- [ ] Pas de caractères spéciaux
- [ ] Le nom respecte la convention de l'équipe

---

## Bonus : Alias Git Utiles

Ajoutez ces alias à votre `~/.gitconfig` :

```bash
[alias]
    # Créer une branche feature
    feat = "!f() { git checkout -b feature/$1; }; f"

    # Créer une branche bugfix
    bug = "!f() { git checkout -b bugfix/$1; }; f"

    # Créer une branche hotfix
    hot = "!f() { git checkout -b hotfix/$1; }; f"
```

Utilisation :

```bash
git feat user-authentication
# Crée et switch vers : feature/user-authentication

git bug login-error
# Crée et switch vers : bugfix/login-error

git hot security-patch
# Crée et switch vers : hotfix/security-patch
```

---

## Ressources

- [Git Branch Naming Convention](https://deepsource.io/blog/git-branch-naming-conventions/)
- [A Successful Git Branching Model](https://nvie.com/posts/a-successful-git-branching-model/)
- [GitHub Flow](https://guides.github.com/introduction/flow/)

---

## Résumé : Le Nom de Branche Parfait

```
<type>/<description-courte>

- Minuscules
- Tirets pour séparer
- 2-4 mots
- Descriptif et clair
- Préfixe de type
- Cohérent avec l'équipe

Exemples parfaits :
- feature/user-authentication
- bugfix/email-validation
- hotfix/security-patch
- refactor/api-endpoints
```

---

**Conseil final :** La consistance est plus importante que la perfection. Choisissez une convention avec votre équipe et respectez-la à 100% ! 🎯
