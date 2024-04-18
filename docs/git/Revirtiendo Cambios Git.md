# Revirtiendo Cambios

La magia de git es que da la capacidad de desacer cambios que has hecho y volver a una versión del código anterior en casode cometer algún fallo.

## Desacer Camios no Commiteados

Si trabajas en algo y quieres deshacer los cambios que estabas haciendo al último commit hecho (_HEAD_) de un archivo completo.
Puedes usar el command `checkout`

```bash
git checkout -- archivo a borrar
```

Si quieres hacerlo de todos los archivos:

```bash
git checkout -- .
```

> En git se puede hacer las mismas cosas de distinto modo, tabién puedes hacecr `git revert HEAD`

## Deshacer Cambios Commiteados

Para deshacer cambios ya commiteados posemos usar `git revert`.
Este, crea un nuevo commit que deshace los cambios de un commit específico. No altera la historia de commits existente, en su lugar, agrega un nuevo commit que deshace los cambios del commit seleccionado.

```bash
git revert <commit>
```

Donde le pasas la id del commit que tendrás que mirar con `git log`.

Si quieres revertir cambios sabiendo que sno n cambios atras de _HEAD_ puedes hacerlo

```bash
git revert HEAD
git revert HEAD~5 # Revierte al commmit de 5 cambios atras
```

Tambiés puedes revertir una serie de cambios

```bash
git revert -n master~5..master~2
```

### Borrar Cambios de Forma Permanente

`git reset` a diferencia de `git revert` se utiliza para deshacer cambios, pero puede ser más drástico en su efecto, ya que puede eliminar commits y cambiar la historia de tu repositorio.

Este comando tiene tres modos principales:

- **`--soft`**: Con `git reset --soft`, el repositorio se restablece al commit especificado, pero los cambios del commit seleccionado se mantienen en el área de ensayo (staging area) y en tu directorio de trabajo. Esto significa que puedes rehacer los cambios y volver a confirmarlos si es necesario.

```bash
git reset --soft <commit>
```

- **`--mixed`**: Esta es la opción predeterminada si no se especifica ninguna opción con `git reset`. Con `git reset --mixed`, el repositorio se restablece al commit especificado y los cambios se eliminan del área de ensayo, pero se conservan en tu directorio de trabajo. Esto te permite revisar los cambios antes de volver a agregarlos al área de ensayo.

```bash
git reset --mixed <commit>
```

- **`--hard`**: Con `git reset --hard`, el repositorio se restablece al commit especificado y los cambios se eliminan tanto del área de ensayo como del directorio de trabajo. Esta opción es más drástica y elimina los cambios de forma permanente, así que úsala con precaución, ya que no hay forma de recuperar los cambios una vez aplicado este comando.

```bash
git reset --hard <commit>
```
