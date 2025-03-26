#  Dépôt GitHub avec Clé SSH personnalisée

Pour cloner et gérer un dépo à l'aide d'une **clé SSH personnalisée** pour une meilleure sécurité et une gestion multi-comptes GitHub.

##  Configuration SSH utilisée

La clé SSH a été générée avec la commande suivante :

```bash
ssh-keygen -t ed25519 -C "ilyas@mail.fr" -f ~/.ssh/id_ed25519_cielnewton_gh
```

### Fichier de configuration SSH (`~/.ssh/config`)

```bash
# Compte GitHub cielnewton
Host github-cielnewton
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519_cielnewton_gh
```

##  Clonage du dépôt

Le dépôt a été cloné avec :

```bash
git clone git@github-cielnewton:cielnewton/vide.git
```

- `github-cielnewton` : alias défini dans le fichier `config`
- `cielnewton` : nom d’utilisateur GitHub
- `vide` : nom du dépôt distant

##  Prérequis

- Avoir `git` installé
- Avoir une clé SSH valide
- La clé doit être ajoutée dans GitHub (Settings > SSH and GPG keys)

##  Commandes Git utiles

```bash
git status       # Voir l'état du dépôt
git add .        # Ajouter tous les fichiers modifiés
git commit -m "message"   # Créer un commit
git push -u origin main        # Envoyer les modifications vers GitHub

git log	               #Affiche l'historique des commits.​
git diff	             #Montre les différences entre les modifications non indexées et l'index, ou entre l'index et le dernier commit.​
git checkout <branche>	#Permet de basculer entre les branches ou de restaurer des fichiers .​
git branch	          #Liste, crée ou supprime des branches.​
git merge <branche>	  #Fusionne la branche spécifiée dans la branche courante.​
git reset --hard <commit>	#Réinitialise le répertoire de travail et l'index à l'état du commit spécifié, supprimant les modifications ultérieures.​
git revert <commit>	  #Crée un nouveau commit qui annule les modifications du commit spécifié.​
git stash	            #Met de côté les modifications en cours pour y revenir plus tard.​
git stash pop	        #Récupère les modifications précédemment mises de côté avec git stash.​
git reflog	          #Affiche l'historique des références mises à jour dans le dépôt local.
```

##  Bonnes pratiques

- Ne jamais partager votre **clé privée**
- Utiliser un fichier `config` pour gérer plusieurs comptes GitHub
- Protéger vos clés avec une **passphrase**

---

>  Pour plus d’infos : [GitHub Docs - SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)
