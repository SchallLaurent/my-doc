## Collaboration

### Travailler avec des remotes

```bash
# Voir les remotes configurés
git remote -v

# Ajouter un remote
git remote add origin https://github.com/username/repo.git

# Renommer un remote
git remote rename origin upstream

# Supprimer un remote
git remote remove origin

# Modifier l'URL d'un remote
git remote set-url origin https://github.com/username/new-repo.git
```

### Récupérer et envoyer des modifications

```bash
# Récupérer les modifications depuis le remote (sans merge)
git fetch origin

# Récupérer toutes les branches
git fetch --all

# Récupérer et fusionner (fetch + merge)
git pull origin main
git pull                               # Depuis la branche trackée

# Pull avec rebase au lieu de merge
git pull --rebase origin main

# Envoyer vos commits
git push origin main
git push                               # Vers la branche trackée

# Pousser une nouvelle branche et créer le tracking
git push -u origin feature-login
git push --set-upstream origin feature-login

# Forcer le push (ATTENTION : réécrit l'historique distant)
git push --force
git push --force-with-lease            # Plus sécurisé

# Pousser tous les tags
git push --tags
```

### Tracking de branches

```bash
# Créer une branche locale qui track une branche distante
git checkout -b feature origin/feature
git checkout --track origin/feature    # Nom identique automatique

# Définir le tracking pour la branche courante
git branch --set-upstream-to=origin/main

# Voir les branches et leur tracking
git branch -vv
```
