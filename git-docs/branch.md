## Branches

### Gestion des branches

```bash
# Lister les branches
git branch                             # Branches locales
git branch -r                          # Branches distantes
git branch -a                          # Toutes les branches
git branch -v                          # Avec le dernier commit

# Créer une nouvelle branche
git branch feature-login

# Créer et basculer sur une nouvelle branche
git checkout -b feature-login
git switch -c feature-login            # Nouvelle syntaxe (Git 2.23+)

# Basculer sur une branche existante
git checkout main
git switch main                        # Nouvelle syntaxe

# Renommer une branche
git branch -m ancien-nom nouveau-nom
git branch -m nouveau-nom              # Renommer la branche courante

# Supprimer une branche
git branch -d feature-login            # Suppression sécurisée
git branch -D feature-login            # Forcer la suppression

# Supprimer une branche distante
git push origin --delete feature-login
```

### Fusionner des branches (merge)

```bash
# Se placer sur la branche de destination
git checkout main

# Fusionner une branche
git merge feature-login

# Merge sans fast-forward (crée toujours un commit de merge)
git merge --no-ff feature-login

# Annuler un merge en cours
git merge --abort

# Continuer après résolution de conflits
git add .
git commit
```

### Rebaser (rebase)

```bash
# Rebaser la branche courante sur main
git rebase main

# Rebase interactif pour modifier l'historique
git rebase -i HEAD~3                   # 3 derniers commits

# Continuer après résolution de conflits
git add .
git rebase --continue

# Abandonner le rebase
git rebase --abort

# Skip un commit problématique
git rebase --skip
```

**Options du rebase interactif :**

- `pick` : garder le commit
- `reword` : modifier le message
- `edit` : modifier le contenu
- `squash` : fusionner avec le commit précédent
- `fixup` : comme squash mais supprime le message
- `drop` : supprimer le commit
