# Configuration de git

## configuration des paramètres globaux

exécuter la commande `git config --global user.email email@orange.fr`
puis tester avec `git config --flobal user.email`

pareil pour le nom

`git config --global user.name "nom prenom`

## configuration des droits d'accès au repository (read/write)

`git remote set-url origin git@github.com:owner/repository`

### configuration du cache

`git config --global credential.helper 'cache --timeout=3600` cache d'1 heure

### génération d'une nouvelle clé ssh

`ssh-keygen -t rsa -b 4096 -C "email@orange.fr"` en appuyant sur ENTREE le message `Generating public/private rsa key pair`

sauvegarde de la clé dans le dossier racine ~ appuie sur ENTRRE

choix d'un **passphrase** compliqué

### Ajouter la clé à SSH-AGENT

démarer le service

`eval "$(ssh-agent -s)"` en appuyant sur ENTREE un pid doit s'afficher

puis ajout de la clé au ssh-agent

`ssh-add -k ~/.ssh/id_rsa`

### Ajout de la clé sur le compte github

cliquer sur **my profil** en haut à droite, choisir le **repository** dans **repositories**, **réglages**, **Deploy keys**, **add deploy keys** , choisir un titre dans la section **title** et copier le contenu de ~/.ssh/id_rsa.pub dans la section **key** puis **activer**

### sauvegarder le passphrase de la clé

`ssh-agent bash` saisir le passphrase
