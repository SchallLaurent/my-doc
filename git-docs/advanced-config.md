## Configuration avancée

### .gitignore

```bash
# Créer un fichier .gitignore
touch .gitignore

# Exemples de patterns
node_modules/
*.log
.env
dist/
build/
.DS_Store
*.swp

# Ignorer tout sauf certains fichiers
*
!README.md
!src/

# Forcer l'ajout d'un fichier ignoré
git add -f fichier-ignore.txt
```

### .gitattributes

```bash
# Normalisation des fins de ligne
* text=auto
*.js text eol=lf
*.bat text eol=crlf

# Fichiers binaires
*.png binary
*.jpg binary
```

### Hooks

Les hooks sont des scripts qui s'exécutent automatiquement à certains moments.

```bash
# Emplacement des hooks
.git/hooks/

# Exemples de hooks
pre-commit        # Avant un commit
pre-push          # Avant un push
post-merge        # Après un merge
```

**Exemple de pre-commit hook :**

```bash
#!/bin/sh
# .git/hooks/pre-commit

# Exécuter les tests
npm test

# Linter
npm run lint

# Si erreur, empêcher le commit
if [ $? -ne 0 ]; then
    echo "Tests ou lint en erreur. Commit annulé."
    exit 1
fi
```
