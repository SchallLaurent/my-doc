## Alias utiles

Les alias permettent de créer des raccourcis pour les commandes fréquentes.

```bash
# Créer des alias
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status

# Alias avancés
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
git config --global alias.visual 'log --graph --oneline --all'
git config --global alias.amend 'commit --amend --no-edit'

# Utilisation
git co main              # git checkout main
git st                   # git status
git visual               # git log --graph --oneline --all
```

**Mes alias recommandés :**

```bash
# Ajouter dans ~/.gitconfig
[alias]
    # Raccourcis basiques
    co = checkout
    br = branch
    ci = commit
    st = status

    # Status court
    s = status -s

    # Log amélioré
    lg = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit

    # Voir les branches
    branches = branch -a

    # Dernier commit
    last = log -1 HEAD --stat

    # Annuler le dernier commit (soft)
    undo = reset --soft HEAD^

    # Amender sans changer le message
    amend = commit --amend --no-edit

    # Voir les contributeurs
    contributors = shortlog -sn

    # Stash avec message
    save = stash save

    # Nettoyer les branches mergées
    cleanup = "!git branch --merged | grep -v '\\*' | xargs -n 1 git branch -d"
```
