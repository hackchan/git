# Curso de Git

## Configuracion

```bash
git config
git config --list --show-origin
git config --global user.name  "Fabio  Rojas"
git config --global user.email  "fabiorojas7@gmail.com"
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
