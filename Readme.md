# Curso de Git

## Multiple ssh key

````bash

ssh-keygen -f ~/.ssh/heroblack -t rsa -b 4096 -C “inge.fabio.rojas@gmail.com”

ssh-keygen -f ~/.ssh/hackchan -t rsa -b 4096 -C “fabiorojas7@gmail.com”

eval `ssh-agent -s`
ssh-add heroblack
ssh-add hackchan
ssh-add -l

vim ~/.ssh/config
```txt
 Host hackchan
 HostName github.com
 IdentityFile ~/.ssh/hackchan
 #-------------------------------
 Host heroblack
 HostName github.com
 IdentityFile ~/.ssh/heroblack
```

````

## Configuracion

```bash
git config
git config --list --show-origin
git config --global user.name  "Fabio  Rojas"
git config --global user.email  "fabiorojas7@gmail.com"

#Colocando una terminal mas agradable para git en centos
#1.INSTALL ZSH
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

#2.PLUGINS
 #2.1 NVM
 git clone https://github.com/lukechilds/zsh-nvm ~/.oh-my-zsh/custom/plugins/zsh-nvm
 #2.2 AUTOSUGGESTION
 git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

plugins=(git zsh-autosuggestions zsh-nvm)
```

## comandos basicos

```bash
echo "# git" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:hackchan/git.git
git push -u origin master
```

## Basic

```bash
git show
git dif
git log
#remover un archivo del Staging Area al Working Directory
git rm --cached .\Readme.md
git reset HEAD  .\Readme.md
```

## Collaborating

```bash
git remote
git remote -v

git remote add <name>               <url>
git remote add origin git@github.com:hackchan/git.git
git remote rm origin
git remote rename origin hero
git remote show origin
```

## Sacar del Stagin Area

```bash
git restore --staged <file>
git checkout -- <file>...
git reset HEAD <file>
#Este es el comando para sacar archivos del área de #Staging. No para borrarlos ni nada de eso, solo para que #los últimos cambios de estos archivos no se envíen al #último commit, a menos que cambiemos de opinión y los #incluyamos de nuevo en staging
git reset HEAD
```

## Eliminar Archivos

```bash
#Elimina los archivos del área de Staging y del próximo commit pero los mantiene en nuestro disco duro.
git rm --cached

#Elimina los archivos de Git y del disco duro. Git siempre #guarda todo, por lo que podemos acceder al registro de la #existencia de los archivos, de modo que podremos #recuperarlos si es necesario (pero debemos usar comandos #más avanzados).
git rm --force
```

## Regresar en el tiempo

```bash
#Borra todo. Todo todito, absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.
git reset 82333bb --hard #Equivale hacer git reset y luego git checkout
#Borramos todo el historial y los registros de Git pero #guardamos los cambios que tengamos en Staging, así #podemos aplicar las últimas actualizaciones a un nuevo #commit.
git reset 82333bb --soft
#profundizar
git reset 3434634 --mixed
```

## Obtener cambios del repositorio remoto

```
#bajamos cambios con fetch los deja en otra rama oculta llamada origin/master la ventaja es que podemos ver que cambios son antes de fusionar a nuestro proyecto.
git fetch
git merge origin/master
#para descargar y hacer la actualizacion de una vez
git pull
git pull --no-edit origin master
git log --all --decorate --oneline
git pull --rebase
```

# Branch

```bash
git checkout -b <nueva-rama>
git branch <nueva-rama>
git checkout <nueva-rama>

#ver todas las ramas
git branch -va

#merge a master
git checkout master
git merge master
#subir rama
git push <remote_name> <branch_name>
#borrar rama
git branch -d <branch_name>

git show-branch --all
#Ayuda grafica
gitk
```

## Git Diff

```
#por defecto git diff compara los archivos que estan en el working directory pero  si se necesita comparar un archivo que esta en el stagin

git diff --staged

# comparo dos commits
git diff HEAD~2 HEAD

```

# Git Show

```
#git show muestra los cambios del ultimo commit (HEAD commit)
git show

```

# Git log

```bash
git log
git log --oneline
git reflog
git log --stat
git log --grep="#1234"
git log -p
git log --oneline -n 2
git log  -n 2
git log -m
git log --no-merges
git log --since="2 weeks ago"
git log --since="2 weeks ago" and --until="1 day ago"
git log -p -m --first-parent
git log 3
```

# Git revert

```bash
#Acabo de subir las claves bancarias a github :O para
#eliminar dicho cambio
git revert HEAD  O git revert HEAD --no-edit O git revert HEAD...HEAD~2 --no-edit
git push origin master
```

# Resolviendo conflictos

```bash
git checkout --ours staging.txt
git checkout --theirs staging.txt

git add stagin.txt
git commit --no-edit
```

# Git Blame

```bash
git blame list.html
git blame -L 6,8 list.html
```

# Git Bisect

```bash
git bisect start
git bisect bad
git bisect good HEAD~5
cat list.html
git bisect good
cat list.html
git bisect bad
```

# Git Cherry-pick

```bash
git cherry-pick 0244a2f19abf4a38ac77b6c376512c0e0a86d9d4

#si hay conflictos
git mergetool
git add --all
git cherry-pick --continue

#si queremos abortar
git cherry-pick --abort
```

# Git rebase

```bash

```

# Github

```bash
git pull origin master --allow-unrelated-histories
```

# Git alias

```bash
#alias de linux
alias minilog="git log --all --graph --decorate --oneline"
#alias de git
git config --global alias.minilog 'git log --all --graph --decorate --oneline'
```

# Git tag

```bash
#En git hay dos tipos de etiquetas Ligeras y Anotadas
#1. Anotadas
git tag -a v0.0.1 "estable proyecto login"
git tag
git show-ref --tags
git push origin --tags

#borra tag en local
git tag -d dormido
#borra tag en remoto
git push origin :ref/tags/dormido
```
