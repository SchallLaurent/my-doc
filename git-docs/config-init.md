## Configuration initiale

### Première configuration

```bash
# Configurer votre identité (obligatoire)
git config --global user.name "Laurent"
git config --global user.email "laurent@example.com"

# Définir l'éditeur par défaut
git config --global core.editor "code --wait"  # VSCode
git config --global core.editor "vim"          # Vim

# Configurer la branche par défaut
git config --global init.defaultBranch main

# Activer la coloration syntaxique
git config --global color.ui auto

# Voir toutes les configurations
git config --list

# Voir une configuration spécifique
git config user.name
```

### Niveaux de configuration

```bash
# --system : pour tous les utilisateurs du système
git config --system core.editor "vim"

# --global : pour l'utilisateur courant (tous les repos)
git config --global user.name "Laurent"

# --local : uniquement pour le repo courant (par défaut)
git config --local user.email "work@example.com"
```
