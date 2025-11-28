## Annuler des modifications

### Dans le working directory

```bash
# Annuler les modifications d'un fichier (non staged)
git checkout -- fichier.txt
git restore fichier.txt                # Nouvelle syntaxe

# Restaurer tous les fichiers
git restore .

# Restaurer depuis un commit spécifique
git restore --source=abc123 fichier.txt
```

### Dans le staging area

```bash
# Retirer du staging (unstage)
git reset HEAD fichier.txt
git restore --staged fichier.txt       # Nouvelle syntaxe

# Unstage tous les fichiers
git reset HEAD
git restore --staged .
```

### Annuler des commits

```bash
# Annuler le dernier commit (garder les modifications)
git reset --soft HEAD~1

# Annuler le dernier commit (modifications en working directory)
git reset HEAD~1
git reset --mixed HEAD~1               # Par défaut

# Annuler le dernier commit (SUPPRIMER les modifications)
git reset --hard HEAD~1                # ⚠️ DANGEREUX

# Annuler plusieurs commits
git reset --hard HEAD~3

# Créer un nouveau commit qui annule un commit précédent
git revert abc123                      # Préférable pour l'historique public

# Revert sans créer de commit immédiatement
git revert -n abc123
```

### Récupérer des commits perdus

```bash
# Voir l'historique de toutes les références
git reflog

# Récupérer un commit "perdu"
git reset --hard abc123
git cherry-pick abc123
```
