# Merge Conflict

Un merge conflict ocurre cuando dos ramas diferentes contienen cambios incompatibles en el mismo archivo, y Git no puede determinar automáticamente cómo fusionar esos cambios.
En este caso, requiere intervención manual del usuario para resolver el conflicto, decidiendo qué cambios mantener y cómo combinarlos adecuadamente.

Para solucionar el conflicto, antes de nada hay que localizarlo, `git status`. Para corregirlo tendrás que editar el archivo que da el conflicto ya que git lo ha escrito esperando a mas informacion. Por ejemplo:

```
Hola
<<<<<<< HEAD
Contenido en la rama principal
=======
Contenido en la rama1
>>>>>>> rama1
```

Esto es un conflicto simulado entre dos ramas, una main y otra rama1. En tal caso tendras que borrar las lineas para quedarte con el contenido que quieres, en este caso me quedare con el contenido de la rama main.

```
Hola
Contenido en la rama principal
```

Ahora le tenemos que informar a git que se ha solucionado:

```bash
git add .
git merge --continue
```

Los editores modernos y clientes de git como Code, IntelliJ o Gitkracken te ayuda a hacer esto de modo visual con una GUI pero esta es la forma que se haría desde consola.
