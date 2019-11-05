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

## Sacar del Stagin Area

```bash
git restore --staged <file>

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
git reset 82333bb --hard
#Borramos todo el historial y los registros de Git pero #guardamos los cambios que tengamos en Staging, así #podemos aplicar las últimas actualizaciones a un nuevo #commit.
git reset 82333bb --soft
#profundizar
git reset 3434634 --mixed
```
