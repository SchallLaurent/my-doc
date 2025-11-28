## Commandes par contexte

### Démarrer un nouveau projet

```bash
mkdir mon-projet
cd mon-projet
git init
echo "# Mon Projet" >> README.md
git add README.md
git commit -m "chore: initial commit"
git branch -M main
git remote add origin https://github.com/username/mon-projet.git
git push -u origin main
```

### Contribuer à un projet open source

```bash
# 1. Fork sur GitHub puis cloner
git clone https://github.com/votre-username/projet-fork.git
cd projet-fork

# 2. Ajouter l'upstream
git remote add upstream https://github.com/auteur-original/projet.git

# 3. Créer une branche
git checkout -b fix/bug-description

# 4. Faire vos modifications et commiter
git add .
git commit -m "fix: resolve bug in component"

# 5. Garder à jour avec upstream
git fetch upstream
git rebase upstream/main

# 6. Pousser et créer une PR
git push -u origin fix/bug-description
```

### Corriger un bug en production

```bash
# 1. Créer une branche hotfix depuis main
git checkout main
git checkout -b hotfix/critical-bug

# 2. Corriger le bug
# ... modifications ...
git add .
git commit -m "hotfix: fix critical authentication bug"

# 3. Merger dans main et develop
git checkout main
git merge --no-ff hotfix/critical-bug
git tag -a v1.0.1 -m "Hotfix 1.0.1"

git checkout develop
git merge --no-ff hotfix/critical-bug

# 4. Pousser tout
git push origin main
git push origin develop
git push origin --tags

# 5. Supprimer la branche hotfix
git branch -d hotfix/critical-bug
```
