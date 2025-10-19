# Templates de Pull Request

Ce guide contient plusieurs templates de Pull Request pour différentes situations. Choisissez celui qui correspond à votre contribution.

---

## Template Standard (À Copier-Coller)

```markdown
## Description

[Décrivez brièvement ce que fait cette PR]

## Type de Changement

- [ ] Bug fix (correction d'un bug)
- [ ] Nouvelle fonctionnalité (ajout d'une feature)
- [ ] Breaking change (changement qui casse la compatibilité)
- [ ] Documentation (mise à jour de la doc)
- [ ] Style (formatage, CSS, UI)
- [ ] Refactorisation (ni bug fix ni feature)
- [ ] Performance (amélioration de performance)
- [ ] Tests (ajout ou modification de tests)
- [ ] Chore (build, CI, dépendances)

## Changements Apportés

- Change 1
- Change 2
- Change 3

## Comment Tester

1. Étape 1
2. Étape 2
3. Étape 3

## Checklist

- [ ] Mon code suit les conventions du projet
- [ ] J'ai testé mes changements
- [ ] J'ai mis à jour la documentation si nécessaire
- [ ] Tous les tests passent
- [ ] Mon code ne génère pas de nouveaux warnings
- [ ] J'ai commenté les parties complexes du code

## Issues Liées

Fixes #[numéro]
Related to #[numéro]

## Captures d'Écran (si applicable)

[Ajoutez des captures d'écran pour les changements UI]

## Notes Additionnelles

[Informations supplémentaires pour les reviewers]
```

---

## 🚀 Template Feature (Nouvelle Fonctionnalité)

```markdown
## Description

### Quoi ?

[Décrivez la nouvelle fonctionnalité]

### Pourquoi ?

[Expliquez pourquoi cette feature est nécessaire]

### Pour Qui ?

[Qui va bénéficier de cette feature ?]

## Changements Apportés

### Nouveaux Fichiers

- `fichier1.js` - [Description]
- `fichier2.js` - [Description]

### Fichiers Modifiés

- `fichier3.js` - [Ce qui a changé]
- `fichier4.js` - [Ce qui a changé]

## Comportement Attendu

**Avant cette PR :**
[Ce qui se passait avant]

**Après cette PR :**
[Ce qui se passe maintenant]

## Comment Tester

### Prérequis

- Prérequis 1
- Prérequis 2

### Étapes de Test

1. Aller sur [page/section]
2. Faire [action]
3. Vérifier que [résultat attendu]

### Cas de Test

- [ ] Test du cas normal
- [ ] Test avec données invalides
- [ ] Test des permissions
- [ ] Test de performance

## Captures d'Écran

### Avant

[Image avant]

### Après

[Image après]

## Issues & Documentation

Closes #[numéro]
Documentation: [lien]

## Points d'Attention

[Points spécifiques que les reviewers doivent vérifier]

## Checklist

- [ ] Code testé localement
- [ ] Tests unitaires ajoutés
- [ ] Tests d'intégration ajoutés (si nécessaire)
- [ ] Documentation mise à jour
- [ ] Pas de régression introduite
- [ ] Performance vérifiée
- [ ] Accessibilité vérifiée (si UI)
- [ ] Mobile responsive (si UI)
```

---

## Template Bug Fix

```markdown
## Description du Bug

### Comportement Actuel (Bugué)

[Décrivez ce qui ne fonctionne pas]

### Comportement Attendu

[Décrivez ce qui devrait se passer]

### Reproduction du Bug

1. Aller sur [page]
2. Cliquer sur [élément]
3. Observer [problème]

### Environnement

- OS: [Windows/Mac/Linux]
- Navigateur: [Chrome/Firefox/Safari]
- Version: [numéro]

## Solution Implémentée

### Cause Racine

[Expliquez la cause du bug]

### Correctif Appliqué

[Expliquez comment vous l'avez corrigé]

### Fichiers Modifiés

- `fichier1.js` - [Modification]
- `fichier2.js` - [Modification]

## Tests

### Tests Ajoutés

- [ ] Test de régression pour ce bug
- [ ] Tests des cas limites
- [ ] Tests des scénarios d'erreur

### Vérification Manuelle

1. [Étape de test 1]
2. [Étape de test 2]
3. [Étape de test 3]

**Résultat attendu :** [Description]

## Avant / Après

### Avant (avec le bug)

[Capture d'écran ou GIF]

### Après (bug corrigé)

[Capture d'écran ou GIF]

## Issues

Fixes #[numéro]

## Effets Secondaires Potentiels

[Listez les parties du code qui pourraient être affectées]

## Checklist

- [ ] Bug reproduit avant le fix
- [ ] Bug corrigé et vérifié
- [ ] Tests de régression ajoutés
- [ ] Pas d'effets secondaires détectés
- [ ] Documentation mise à jour si nécessaire
```

---

## Template Refactorisation

```markdown
## Refactorisation

### Objectif

[Pourquoi ce refactoring est nécessaire]

### Problème Actuel

[Quel est le problème avec le code actuel ?]

- Problème 1
- Problème 2

### Solution Proposée

[Comment le refactoring résout ces problèmes]

- Amélioration 1
- Amélioration 2

## Changements Techniques

### Architecture

[Changements dans l'architecture]

### Patterns Utilisés

[Design patterns ou approches utilisés]

### Fichiers Affectés

- `fichier1.js` - [Changement]
- `fichier2.js` - [Changement]

## Métriques

### Avant

- Lignes de code: [nombre]
- Complexité cyclomatique: [nombre]
- Duplication: [pourcentage]

### Après

- Lignes de code: [nombre]
- Complexité cyclomatique: [nombre]
- Duplication: [pourcentage]

## Validation

- [ ] Tous les tests existants passent
- [ ] Aucune régression fonctionnelle
- [ ] Performance maintenue ou améliorée
- [ ] Code plus lisible/maintenable

## Contexte

Related to #[numéro]

## Notes pour les Reviewers

[Points spécifiques à vérifier pendant la review]
```

---

## Template Documentation

```markdown
## Mise à Jour de la Documentation

### Type de Documentation

- [ ] README
- [ ] Documentation API
- [ ] Guide utilisateur
- [ ] Documentation technique
- [ ] Commentaires de code
- [ ] Wiki

### Changements Apportés

#### Ajouté

- [Ce qui a été ajouté]

#### Modifié

- [Ce qui a été modifié]

#### Supprimé

- [Ce qui a été supprimé]

### Motivation

[Pourquoi ces changements de documentation sont nécessaires]

### Fichiers Modifiés

- `fichier1.md` - [Changement]
- `fichier2.md` - [Changement]

## Checklist

- [ ] Orthographe et grammaire vérifiées
- [ ] Liens fonctionnels testés
- [ ] Captures d'écran à jour
- [ ] Exemples de code testés
- [ ] Format markdown correct
- [ ] Table des matières mise à jour (si applicable)

## Contexte

Closes #[numéro]
```

---

## Template UI/Style

```markdown
## Changements UI/Style

### Description

[Décrivez les changements visuels]

### Motivation

[Pourquoi ces changements sont nécessaires]

## Aperçu Visuel

### Desktop

**Avant :**
[Image/GIF]

**Après :**
[Image/GIF]

### Mobile

**Avant :**
[Image/GIF]

**Après :**
[Image/GIF]

### Tablette (si applicable)

**Avant :**
[Image/GIF]

**Après :**
[Image/GIF]

## Détails Techniques

### CSS Modifié

- Fichier: `style.css`
- Changements: [Liste]

### Composants Affectés

- Composant 1
- Composant 2

### Navigateurs Testés

- [ ] Chrome
- [ ] Firefox
- [ ] Safari
- [ ] Edge

### Responsive

- [ ] Desktop (1920x1080)
- [ ] Laptop (1366x768)
- [ ] Tablette (768x1024)
- [ ] Mobile (375x667)

## ♿ Accessibilité

- [ ] Contraste vérifié (WCAG AA)
- [ ] Navigation au clavier testée
- [ ] Screen reader testé
- [ ] Textes alternatifs ajoutés

## Checklist

- [ ] Design approuvé par l'équipe
- [ ] Responsive sur tous les écrans
- [ ] Performance vérifiée
- [ ] Accessibilité respectée
- [ ] Cross-browser testé

## Issues & Design

Closes #[numéro]
Design Figma: [lien]
```

---

## Template Hotfix

```markdown
## HOTFIX - [Titre Descriptif]

### Urgence: [CRITIQUE / HAUTE / MOYENNE]

### Problème Critique

[Décrivez le problème en production]

### Impact

- Utilisateurs affectés: [nombre ou %]
- Fonctionnalités impactées: [liste]
- Perte financière potentielle: [si applicable]

### Cause Racine

[Expliquez la cause du problème]

### Solution

[Décrivez la solution implémentée]

### Vérification

- [ ] Fix testé en local
- [ ] Fix testé en staging
- [ ] Pas d'effets secondaires détectés
- [ ] Rollback plan en place

### Plan de Déploiement

1. [Étape 1]
2. [Étape 2]
3. [Étape 3]

### Plan de Rollback

En cas de problème:

1. [Étape rollback 1]
2. [Étape rollback 2]

### Issues

Fixes #[numéro] (CRITICAL)

### Contact

@mention-dev-on-call
```

---

## Exemple de PR Complète (Réel)

Voici un exemple concret d'une bonne PR :

```markdown
## Description

Ajout d'un système d'authentification à deux facteurs (2FA) via TOTP pour améliorer la sécurité des comptes utilisateurs.

## Type de Changement

- [x] Nouvelle fonctionnalité
- [ ] Bug fix
- [ ] Breaking change

## Changements Apportés

### Backend

- Ajout de l'endpoint `POST /api/auth/2fa/enable`
- Ajout de l'endpoint `POST /api/auth/2fa/verify`
- Génération de QR codes pour TOTP
- Stockage sécurisé des secrets 2FA
- Validation des codes TOTP

### Frontend

- Nouvelle page de configuration 2FA dans les paramètres
- Modal de vérification 2FA au login
- Affichage des codes de backup
- Instructions utilisateur claires

### Base de Données

- Migration ajoutant les colonnes `two_factor_secret` et `two_factor_enabled`

## Comment Tester

### Activer 2FA

1. Se connecter avec un compte de test
2. Aller dans Paramètres → Sécurité
3. Cliquer sur "Activer 2FA"
4. Scanner le QR code avec Google Authenticator
5. Entrer le code à 6 chiffres
6. Sauvegarder les codes de backup

### Tester le Login avec 2FA

1. Se déconnecter
2. Se reconnecter avec email/password
3. Entrer le code 2FA depuis l'app
4. Vérifier l'accès au compte

### Tester la Désactivation

1. Aller dans Paramètres → Sécurité
2. Cliquer sur "Désactiver 2FA"
3. Confirmer avec le code actuel
4. Vérifier que le login ne demande plus de code

## Captures d'Écran

### Page de Configuration 2FA

![Configuration](https://via.placeholder.com/600x400)

### QR Code pour Setup

![QR Code](https://via.placeholder.com/300x300)

### Modal de Vérification

![Verification](https://via.placeholder.com/400x300)

## Checklist

- [x] Code testé localement
- [x] Tests unitaires ajoutés (couverture: 95%)
- [x] Tests d'intégration ajoutés
- [x] Documentation API mise à jour
- [x] Documentation utilisateur ajoutée
- [x] Migration de base de données testée
- [x] Pas de données sensibles dans les logs
- [x] Cryptage des secrets vérifié

## Issues Liées

Closes #234
Related to #189 (amélioration sécurité)

## Notes pour les Reviewers

- Le secret 2FA est crypté avec AES-256 avant stockage
- Les codes de backup sont générés avec crypto.randomBytes
- Les codes TOTP expirent après 30 secondes (standard)
- La librairie `speakeasy` est utilisée pour TOTP
- Attention particulière à la gestion d'erreurs dans `/api/auth/2fa/verify`

## Performance

- Temps de réponse `/api/auth/2fa/enable`: ~50ms
- Temps de réponse `/api/auth/2fa/verify`: ~30ms
- Pas d'impact sur le login sans 2FA

## Sécurité

- Secrets 2FA cryptés au repos
- Rate limiting sur la vérification (5 tentatives/minute)
- Codes de backup hashés avec bcrypt
- Pas de logs des secrets ou codes
```

---

## Conseils pour Rédiger une Bonne PR

### 1. Titre Clair et Descriptif

```markdown
# ✅ BON

Add two-factor authentication via TOTP
Fix login validation error on special characters
Refactor user service to improve testability

# ❌ MAUVAIS

Update
Fix bug
Changes
```

### 2. Description Complète

**Incluez toujours :**

- **Quoi** : Ce qui a été fait
- **Pourquoi** : La raison du changement
- **Comment** : L'approche technique utilisée

### 3. Instructions de Test Détaillées

Les reviewers doivent pouvoir tester sans demander d'aide.

### 4. Captures d'Écran pour les Changements UI

Une image vaut mille mots. Utilisez des GIFs pour les interactions.

### 5. Référencez les Issues

```markdown
Fixes #123 # Ferme automatiquement l'issue
Closes #456 # Ferme automatiquement l'issue
Related to #789 # Lie sans fermer
```

### 6. Soyez Honnête sur les Limitations

```markdown
## Limitations Connues

- Ne fonctionne pas sur IE11 (non supporté)
- Performance à optimiser pour >10k éléments
- TODO: Ajouter les tests e2e
```

### 7. Facilitez le Travail des Reviewers

```markdown
## Points d'Attention pour Review

- Vérifier la gestion d'erreurs ligne 234
- Valider l'algorithme de tri ligne 567
- Commenter sur le choix de librairie (section X)
```

---

## Taille Idéale d'une PR

### Taille Recommandée

- **Petite** : 1-100 lignes (~10 min de review)
- **Moyenne** : 100-400 lignes (~30 min de review)
- **Grande** : 400-1000 lignes (~1h de review)

### À Éviter

- **Énorme** : 1000+ lignes
  - Difficile à reviewer
  - Prend trop de temps
  - Plus de bugs passent inaperçus

**Solution :** Découper en plusieurs PRs plus petites.

---

## Template Automatique GitHub

Pour que GitHub utilise automatiquement ce template, créez :

`.github/PULL_REQUEST_TEMPLATE.md`

Contenu :

```markdown
## Description

<!-- Décrivez vos changements -->

## Type de Changement

- [ ] Bug fix
- [ ] Nouvelle fonctionnalité
- [ ] Breaking change
- [ ] Documentation

## Checklist

- [ ] Mon code suit les conventions du projet
- [ ] J'ai testé mes changements
- [ ] J'ai mis à jour la documentation

## Issues Liées

Fixes #
```

---

## Ressources

- [GitHub Pull Request Best Practices](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests)
- [The Art of Pull Requests](https://hackernoon.com/the-art-of-pull-requests-6f0f099850f9)
- [How to Write the Perfect Pull Request](https://github.blog/2015-01-21-how-to-write-the-perfect-pull-request/)

---

## Checklist Finale

Avant de soumettre votre PR :

- [ ] Titre clair et descriptif
- [ ] Description complète (Quoi, Pourquoi, Comment)
- [ ] Type de changement sélectionné
- [ ] Instructions de test détaillées
- [ ] Captures d'écran (si UI)
- [ ] Checklist complétée
- [ ] Issues référencées
- [ ] Code auto-reviewé
- [ ] Conflits résolus
- [ ] Tests passent en local

---

**Une bonne PR est une PR qui se merge rapidement ! 🚀**
