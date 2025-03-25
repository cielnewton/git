#  Dépôt GitHub avec Clé SSH personnalisée

Ce dépôt a été cloné et géré à l'aide d'une **clé SSH personnalisée** pour une meilleure sécurité et une gestion multi-comptes GitHub facilitée.

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
git push         # Envoyer les modifications vers GitHub
```

##  Bonnes pratiques

- Ne jamais partager votre **clé privée**
- Utiliser un fichier `config` pour gérer plusieurs comptes GitHub
- Protéger vos clés avec une **passphrase**

---

>  Pour plus d’infos : [GitHub Docs - SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)
