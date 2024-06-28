# git cheatsheet

ndpsoftware.com/git-cheatsheet.html

## git clone

importer un repository depuis 
  - internet (https ou ssh)
  - local `git clone /path/to/repo`

## git init

- inititer un repository
- création folder `.git`


## git add 

- indiquer ce que l'on va commit
- sélecter les modification que l'on veut commiter

- `git add .` sélectionner tout les modifications dans le répertoire
- `git add *.md` sélectionner tout les fichiers avec l'extension .md  

## git rm


- `git rm nom-du-fichier`

 - 'supprime' dans version actuelle le fichier
 - dans le folder

Si on veut garder le fichier `git rm --cache nom-du-fichier`, puis ensuite l'ajouter dans le `.gitignore`.


## git commit

- sauvegarde dans .git toutes les modifications indiquées par `git add`

`git commit` -> ouverture de l'éditeur pour écrire le commit message.
`git commit -m 'Commit message'` pour ajouter directement un message dans le commit.
`git commit -a` -> sélectionne toutes les modifications sur les fichiers suivies.
`git commit --amend` permet de modifier le dernier commit.

# git branch

`git branch` liste les branches
`git branch -b nom_de_la_branche` créer une nouvelle branche

# git checkout

`git checkout branch_name` permet de branche
`git checkout HEAD^` -> mettre le repository à l'état du précédant commit
`git checkout HEAD~n` -> retourne à l'état du n'.ème commit
`git checkout hash` -> retourne au commit indiqué

# git pull

- recupérer les commits qui sont sur un branche distante

# git push

- envoyer les commits sur la branche distante

# git fetch origin

- recupérer les branches

# git reset 

`git reset --soft`

 modifie uniquement l'index
 cas d'utilisation: on a fait un git add sur un fichier que l'on ne veut pas ajouté dans l'index0

`git reset --hard`

modifie l'index et l'espace de travail
les modifications que l'on a fait sont totalement supprimée

`git reset hash_de_commit` remet le repo à l'état du commit indiqué par le hash

# git merge

On veut merger une branche `feature-X` dans `main`.

- `git checkout main` -> se placer sur la branche main
- `git merge feature-X` -> merge de la branche feature-X dans main

Le merge créé un commit de merge.
On perd l'historique de la branche de `feature-X`

# git rebase


Le git rebase conserve les commits que l'on a sur la branche 

# git stash


- utile si on veut changer de branches et que notre espace n'est pas propre

- `git stash` enregister dans le stash (mémoire temporaire)
- `git stash pop` permet de réapliquer ce qui le stash dans l'espace de travail 