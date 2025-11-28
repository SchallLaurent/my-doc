# 🔧 Git Docs

Documentation complète sur Git et le contrôle de version en ligne de commande.

## 📖 Contenu

Ce dossier contient des guides détaillés sur Git, organisés par thématiques pour faciliter l'apprentissage et la consultation rapide.

### 📚 Documents disponibles

#### Fondamentaux

- **[01-configuration-initiale.md](./config-init.md)** - Configuration de Git et première utilisation
- **[02-creer-repository.md](./create-repo.md)** - Initialiser et cloner des repositories
- **[03-workflow-base.md](./workflow-base.md)** - Cycle de travail : add, commit, diff

#### Branches et collaboration

- **[04-branches.md](./branch.md)** - Gestion des branches, merge et rebase
- **[05-collaboration.md](./collaboration.md)** - Remotes, fetch, pull, push

#### Historique et inspection

- **[06-historique.md](./history.md)** - Git log, show, blame
- **[07-annuler-modifications.md](./cancel-modif.md)** - Reset, revert, restore

#### Outils avancés

- **[08-stash.md](./stash.md)** - Mise de côté temporaire des modifications
- **[09-tags.md](./tags.md)** - Marquage de versions et releases
- **[10-configuration-avancee.md](./advanced-modif.md)** - .gitignore, hooks, .gitattributes

#### Dépannage et optimisation

- **[11-depannage.md](./troubleshooting-order.md)** - Résolution de problèmes, conflits, reflog
- **[12-alias.md](./alias-utils.md)** - Alias et raccourcis pour gagner en productivité
- **[13-best-practices.md](./best-pratices.md)** - Bonnes pratiques et workflows (Gitflow, Conventional Commits)

## 🎯 Comment utiliser cette documentation

### Pour débuter avec Git

Suivez les documents dans l'ordre numérique :

1. Configuration initiale
2. Créer un repository
3. Workflow de base
4. Branches
5. Collaboration

### Pour une recherche rapide

Utilisez la table des matières ci-dessus pour naviguer directement vers le sujet qui vous intéresse.

### Pour maîtriser Git

Consultez les documents avancés (stash, tags, configuration avancée) et les best practices une fois les fondamentaux acquis.

## 💡 Cas d'usage fréquents

### Je veux...

**...annuler mon dernier commit (sans perdre les modifications)**
→ Voir [07-annuler-modifications.md](./cancel-modif.md) - Section "Reset --soft"

**...mettre de côté mes modifications en cours**
→ Voir [08-stash.md](./stash.md)

**...résoudre un conflit de merge**
→ Voir [11-depannage.md](./troubleshooting-order.md) - Section "Résolution de conflits"

**...voir qui a modifié une ligne de code**
→ Voir [06-historique.md](./history.md) - Section "Git blame"

**...nettoyer mon historique avant de push**
→ Voir [04-branches.md](./branch.md) - Section "Rebase interactif"

**...créer une release/version**
→ Voir [09-tags.md](./tags.md)

**...configurer des alias pour aller plus vite**
→ Voir [12-alias.md](./alias-utils.md)

**...suivre les bonnes pratiques pour mes commits**
→ Voir [13-best-practices.md](./best-pratices.md) - Section "Messages de commit"

## 📋 Commandes essentielles (Quick Reference)

```bash
# Configuration
git config --global user.name "Votre Nom"
git config --global user.email "email@example.com"

# Workflow de base
git status                    # État des fichiers
git add .                     # Ajouter au staging
git commit -m "message"       # Créer un commit
git push                      # Envoyer vers le remote

# Branches
git branch                    # Lister les branches
git checkout -b feature       # Créer et basculer
git merge feature             # Fusionner une branche

# Collaboration
git clone <url>               # Cloner un repo
git pull                      # Récupérer et fusionner
git fetch                     # Récupérer sans fusionner

# Historique
git log --oneline --graph     # Historique visuel
git diff                      # Voir les modifications

# Annulation
git reset --soft HEAD~1       # Annuler dernier commit
git restore fichier.txt       # Restaurer un fichier
git revert <commit>           # Créer un commit inverse

# Stash
git stash                     # Mettre de côté
git stash pop                 # Récupérer et supprimer
```

### Types de branches

- **main/master** : Branche principale (code en production)
- **develop** : Branche de développement
- **feature/** : Nouvelles fonctionnalités
- **hotfix/** : Corrections urgentes
- **release/** : Préparation de versions

## 📚 Ressources externes

### Documentation officielle

- [Git Documentation](https://git-scm.com/doc)
- [Pro Git Book](https://git-scm.com/book/fr/v2) - Gratuit en français

### Tutoriels interactifs

- [Learn Git Branching](https://learngitbranching.js.org/) - Visualisation interactive
- [Git Immersion](https://gitimmersion.com/) - Tutoriel guidé pas à pas

### Cheat Sheets

- [GitHub Git Cheat Sheet](https://training.github.com/downloads/github-git-cheat-sheet.pdf)
- [Atlassian Git Cheat Sheet](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)

## 🤝 Contribution

Cette documentation évolue avec l'expérience. Les suggestions d'amélioration sont les bienvenues !

## ⚡ Tips & Tricks

### Gagner du temps

```bash
# Alias recommandés
git config --global alias.co checkout
git config --global alias.st status
git config --global alias.br branch
git config --global alias.ci commit
```

### Éviter les erreurs courantes

- ❌ Ne jamais `git push --force` sur `main`
- ❌ Ne pas commiter de fichiers sensibles (.env, clés API)
- ✅ Toujours `git pull` avant de `git push`
- ✅ Utiliser `.gitignore` dès le début du projet
- ✅ Faire des commits atomiques et réguliers

### Commandes pour sortir d'une situation délicate

```bash
# Annuler un merge en cours
git merge --abort

# Annuler un rebase en cours
git rebase --abort

# Récupérer un commit "perdu"
git reflog
git cherry-pick <commit-hash>

# Nettoyer complètement le working directory
git clean -fdx  # ⚠️ Attention : supprime tout
```

---

**Conseil** : Git s'apprend par la pratique. N'hésitez pas à expérimenter dans un repository de test avant de l'appliquer sur vos projets réels !

---
