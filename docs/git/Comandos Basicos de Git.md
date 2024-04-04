# Trabajando con Git

Para iniciar un repositorio de Git (Carpeta en la que se va a aplicar el control de versiones) ejecutaremos:

```powershell
git init
```

Este comando creará una carpeta oculta `.git` en la que se guardará toda la información, esta carpeta no debemos tocarla.

Una vez inicializado el repositorio podremos ya empezar a guardar las versiones del proyecto.

## Commits

Un "commit" en Git es un registro de cambios en un repositorio de código.
Se usa para guardar los cambios que has realizado en los archivos del proyecto, junto con un mensaje descriptivo que explica qué cambios se han realizado.

>Los mensajes deben de ser descriptivos. De nada sirve un mensaje que ponga `gfhfgh` a la hora de buscar un error en el código.

Para hacer un commit se pasan por dos etapas, una etapa de `stage`. En esta etapa se marcan los archivos que se quieran commitear.

Para esto se utiliza el commando:

```powershell
git add path/to/the/file.java
```

Si quieres añadir todos los cambios, puedes hacerlo mediante el uso de `.` o `*`

```powershell
git add .
```

Con `git status` podremos ver que archivos estan en stage y los que no.

Para commitear los cambios marcados en etapa stage usaremos:

```powershell
git commit -m "Mensaje del commit"
```

Con el parametro `-m` Le inicamos el mensaje, si no lo incluimos se abrirá el editor que tengamos y ahí pondremos el mensaje.

Para commitear todos los cambios y saltarnos la etapa de stage podremos usar el parametro `-a`:

```powershell
git commit -am "Ejemplo"
```

Para quitar un archivo de stage simplemente ejecute:

```powershell
git reset HEAD archivo/a/quitar.md
```

Si nos limitamos a poner `git reset HEAD` serán todos los cambios

## Revertir Cambios

Cuando estamos trabajando y queremos hacer rollback para dejar el archivo exactamente como estaba en el último commit

```powershell
git checkout -- archivo.txt
```

En el caso de darnos cuenta de un error ya commiteado podemos revertir los cambios hasta el commit deseado podemos usar `git revert` en el cual le pasaremos el identificador del commit

```powershell
git revert abc123
```

Para ver este identificador podremos usar `git log` el cual tiene varios parametros utiles, entre los que destacan `--oneline` o `--graph`

```powershell
git log --oneline --graph
```

## Diferencias entre los Commits

El comando `git diff` es muy útil, permite ver las diferencias entre distintos estados de un repositorio.

Sirve para visualizar diferencias entre distintas cosas, por ejemplo si ejecutas `git diff` ves la diferencia entre lo que hay en el directorio de trabajo y lo que hay en stage. También sirve para ver la diferencia entre el stage y el último commit `git diff --cached`, esto puede ser útil para revisar los cambios antes de commitearlos.

Los más útiles bajo mi opinión son:

```bash
git diff HEAD
```

Que muestra las diferencias entre el directorio de trabajo y el último commit. Y también es útil

```bash
git diff <commit1> <commit2>
```

Este muestra la diferencia entre dos commits. (Tienes que pasar el identificador del commit, `git log`).
