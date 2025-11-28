## Les bases du workflow

### Cycle de base : Working Directory → Staging → Repository

```bash
# Vérifier l'état des fichiers
git status

# Version courte et lisible
git status -s
git status --short

# Ajouter des fichiers au staging (index)
git add fichier.txt                    # Un fichier spécifique
git add src/                           # Un dossier
git add .                              # Tous les fichiers modifiés
git add *.js                           # Tous les fichiers .js
git add -A                             # Tous les fichiers (ajouts, modifs, suppressions)
git add -u                             # Seulement les fichiers déjà trackés

# Ajouter de manière interactive
git add -p                             # Choisir les changements à ajouter
git add -i                             # Mode interactif complet

# Valider les changements (commit)
git commit -m "Message de commit"

# Commit avec description détaillée
git commit -m "Titre du commit" -m "Description détaillée"

# Ajouter et commiter en une seule commande
git commit -am "Message"               # Seulement pour fichiers déjà trackés

# Modifier le dernier commit
git commit --amend -m "Nouveau message"
git commit --amend --no-edit           # Garder le même message

# Retirer un fichier du staging
git reset HEAD fichier.txt
git restore --staged fichier.txt       # Nouvelle syntaxe (Git 2.23+)
```

### Visualiser les différences

```bash
# Voir les modifications non staged
git diff

# Voir les modifications staged (prêtes à être commitées)
git diff --staged
git diff --cached

# Différences pour un fichier spécifique
git diff fichier.txt

# Différences entre deux branches
git diff main..feature-branch

# Statistiques des changements
git diff --stat
```
