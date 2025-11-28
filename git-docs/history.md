## Historique et inspection

### Voir l'historique

```bash
# Historique des commits
git log

# Format condensé (une ligne par commit)
git log --oneline

# Avec le graphe des branches
git log --graph --oneline --all

# Limiter le nombre de commits
git log -n 5
git log -5

# Historique d'un fichier spécifique
git log -- fichier.txt

# Voir les changements dans chaque commit
git log -p
git log --patch

# Statistiques des modifications
git log --stat

# Filtrer par auteur
git log --author="Laurent"

# Filtrer par date
git log --since="2 weeks ago"
git log --after="2024-01-01"
git log --before="2024-12-31"

# Rechercher dans les messages de commit
git log --grep="fix"

# Format personnalisé
git log --pretty=format:"%h - %an, %ar : %s"
```

**Codes de format :**

- `%h` : hash court
- `%H` : hash complet
- `%an` : nom de l'auteur
- `%ae` : email de l'auteur
- `%ad` : date
- `%ar` : date relative
- `%s` : sujet (message)

### Inspecter des commits

```bash
# Voir les détails d'un commit
git show HEAD
git show abc123

# Voir un fichier à un commit spécifique
git show abc123:src/app.js

# Qui a modifié chaque ligne d'un fichier
git blame fichier.txt

# Blame avec plus de contexte
git blame -L 10,20 fichier.txt        # Lignes 10 à 20
```
