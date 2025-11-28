## Stash - Mise de côté temporaire

Le stash permet de mettre de côté des modifications en cours sans les commiter.

```bash
# Stasher les modifications
git stash
git stash save "Message descriptif"

# Stasher en incluant les fichiers non trackés
git stash -u
git stash --include-untracked

# Stasher également les fichiers ignorés
git stash -a
git stash --all

# Lister les stash
git stash list

# Voir le contenu d'un stash
git stash show
git stash show -p stash@{0}            # Avec les différences

# Appliquer le dernier stash
git stash apply

# Appliquer un stash spécifique
git stash apply stash@{2}

# Appliquer et supprimer le stash
git stash pop

# Supprimer un stash
git stash drop stash@{0}

# Supprimer tous les stash
git stash clear

# Créer une branche depuis un stash
git stash branch nouvelle-branche
```
