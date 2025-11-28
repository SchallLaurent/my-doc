## Best Practices

### Messages de commit

**Convention Conventional Commits :**

```bash
# Format
<type>(<scope>): <subject>

<body>

<footer>

# Types courants
feat:     # Nouvelle fonctionnalité
fix:      # Correction de bug
docs:     # Documentation
style:    # Formatage, point-virgules manquants, etc.
refactor: # Refactorisation du code
test:     # Ajout de tests
chore:    # Maintenance, dépendances

# Exemples
git commit -m "feat(auth): add JWT authentication"
git commit -m "fix(api): resolve null pointer exception in user service"
git commit -m "docs: update README with installation steps"
git commit -m "refactor(components): extract Button into separate file"
```

### Workflow recommandé

```bash
# 1. Créer une branche pour chaque feature
git checkout -b feature/user-profile

# 2. Travailler et commiter régulièrement
git add .
git commit -m "feat: add user profile component"

# 3. Garder la branche à jour avec main
git fetch origin
git rebase origin/main

# 4. Pousser la branche
git push -u origin feature/user-profile

# 5. Créer une Pull Request sur GitHub/GitLab

# 6. Après merge, supprimer la branche
git checkout main
git pull
git branch -d feature/user-profile
```

### Règles d'or

1. **Commiter souvent** : petits commits ciblés plutôt que gros commits
2. **Messages clairs** : expliquer le "pourquoi", pas le "quoi"
3. **Jamais de force push sur main/develop** : sauf en cas d'urgence
4. **Tester avant de commiter** : s'assurer que le code fonctionne
5. **Rebase vs Merge** :
   - Rebase pour garder un historique linéaire (branches feature)
   - Merge pour préserver l'historique complet (main)
6. **Ne pas commiter** :
   - Fichiers générés (node_modules, dist, build)
   - Fichiers de configuration locale (.env, .idea)
   - Fichiers sensibles (clés API, mots de passe)

### Gitflow

Workflow structuré pour projets en équipe :

```bash
# Branches principales
main        # Code en production
develop     # Code en développement

# Branches de support
feature/*   # Nouvelles fonctionnalités
release/*   # Préparation de release
hotfix/*    # Corrections urgentes en prod

# Exemple de workflow
git checkout develop
git checkout -b feature/new-login
# ... développement ...
git checkout develop
git merge --no-ff feature/new-login
git branch -d feature/new-login
```
