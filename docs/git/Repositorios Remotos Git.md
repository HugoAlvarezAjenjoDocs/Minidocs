# Repositorios Remotos Git

Los repositorios que creamos con `git init` son repositorios locales en nuestro ordenador, pero para trabajar de manera colaborativa se utilizan repositorios remotos. Plataformas como Github o Gitlab ofrecen estos servicios.

La forma de trabajar con ellos no es muy diferente. No nos vamos a centrar en aspectos concretos de cada plataforma (crear repositorios github, autenticarse, tokens...), solo nos vamos a centraren como trabajar sobre ellos.

Cuando quies añadir un repositorio remoto utilizas:

```powershell
git remote add origin direccion_del_repositorio
```

Esto te agrega la direccion al repositorio para trabajar.

Si quieres clonar un repositorio para trabajar a el pero no lo tienes en tu máquina local:

```powershell
git clone direccion_del_repositorio
```

## Trabajando Con repositorios

Ya teniendo el repositorio en tu máquina local si ejecutas `git fetch` mira si hay cambios del repositorio remoto comparado con tu repositorio local. En el caso de que haya cambios, puedes ejecutar:

```powershell
git pull
```

En este momento, puedes empezar a trabajar como en local y hacer los commits necesarios. Una vez ya terminado tienes que llevar los cambios al repositorio remoto:

```powershell
git push origin main
```

>origin es el nombre del repositorio remoto y main es el nombre de la rama principal o la que quieres usar.

Si el repositorio esta vacio tendrás que usar:

```powershell
git push -u origin main
```

---

>Si estras trabajando de forma colaborativa es posible que se provoque un merge conflict que se da cuando dos cambios sobre lo mismo han pasado y tendrás que solucionarlo a mano.
