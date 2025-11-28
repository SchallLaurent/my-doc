## Tags

Les tags permettent de marquer des points spécifiques de l'historique (versions, releases).

```bash
# Créer un tag léger
git tag v1.0.0

# Créer un tag annoté (recommandé)
git tag -a v1.0.0 -m "Version 1.0.0"

# Tagger un commit spécifique
git tag -a v0.9.0 abc123 -m "Version 0.9.0"

# Lister les tags
git tag
git tag -l "v1.*"                      # Filtrer

# Voir les infos d'un tag
git show v1.0.0

# Pousser un tag
git push origin v1.0.0

# Pousser tous les tags
git push origin --tags

# Supprimer un tag local
git tag -d v1.0.0

# Supprimer un tag distant
git push origin --delete v1.0.0
git push origin :refs/tags/v1.0.0

# Checkout sur un tag
git checkout v1.0.0
```
