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
```

## Git Diff

```
#por defecto git diff compara los archivos que estan en el working directory pero  si se necesita comparar un archivo que esta en el stagin

git diff --staged

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

```
