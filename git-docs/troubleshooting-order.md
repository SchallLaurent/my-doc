## Commandes de dépannage

### Nettoyage

```bash
# Supprimer les fichiers non trackés
git clean -n                           # Voir ce qui serait supprimé (dry-run)
git clean -f                           # Supprimer les fichiers
git clean -fd                          # Supprimer fichiers et dossiers
git clean -fX                          # Seulement les fichiers ignorés
git clean -fx                          # Tout (ignorés et non ignorés)

# Optimiser le repository
git gc                                 # Garbage collection
git gc --aggressive --prune=now        # Nettoyage agressif
```

### Résolution de problèmes

```bash
# Vérifier l'intégrité du repository
git fsck

# Réparer un repository corrompu
git fsck --full
git reflog expire --expire=now --all
git gc --prune=now --aggressive

# Résoudre "detached HEAD"
git checkout main
git branch temp                        # Sauvegarder les commits orphelins
git checkout main
git merge temp

# Synchroniser avec le remote après un force push
git fetch origin
git reset --hard origin/main           # ⚠️ Perte des modifications locales

# Trouver quel commit a introduit un bug (bisect)
git bisect start
git bisect bad                         # Commit actuel est mauvais
git bisect good abc123                 # Commit abc123 était bon
# Git checkout automatiquement des commits
# Tester et marquer : git bisect good/bad
git bisect reset                       # Terminer
```

### Résolution de conflits

```bash
# Voir les fichiers en conflit
git status

# Éditer les fichiers et chercher les marqueurs
<<<<<<< HEAD
Votre version
=======
Leur version
>>>>>>> branch-name

# Après résolution
git add fichier-resolu.txt
git commit

# Utiliser un outil de merge
git mergetool

# Accepter une version (la leur ou la nôtre)
git checkout --ours fichier.txt        # Garder notre version
git checkout --theirs fichier.txt      # Garder leur version
```
