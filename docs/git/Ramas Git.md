# Ramas en Git

En Git, las ramas son versiones independientes de un proyecto que permiten el desarrollo paralelo de diferentes características o soluciones.
Se utilizan para experimentar, aislar cambios, implementar nuevas funcionalidades y mantener versiones estables y de desarrollo separadas.
Las ramas facilitan la colaboración en equipo al proporcionar un entorno flexible para trabajar en diferentes partes del proyecto simultáneamente.

Al trabajar con ramas se utilizan principalmente cuatro comandos `git branch`, `git switch`, `git checkout` y `git merge`.

## Creación de Ramas

`git branch` sirve principalmente para la creación y eliminación de ramas:

```bash
git branch # Muestra todas las ramas
git branch nueva-rama # Crea una nueva rama (Desde HEAD)
git branch nueva-rama <commit> # Crea una nueva rama desde un commit especifico
git branch -d rama-a-eliminar # Borra una rama (Lo hace si ya has hecho merge de ella)
```

Otros de interesantes:

```bash
git branch -D <branch> # Borra una rama
git branch -m name # Renombra la rama actual
git branch -m nombre-antiguo nombre-nuevo # Renombra una rama
git branch -a # Lista las ramas remotas
```

## Moverse entre Ramas

Para moverse entre ramas hay dos formas, con `checkout` y con `switch`.

`git switch` como su nombre dice es cambiar de una rama a otra (Es una alternativa segura a `checkout` por lo que se recomienda usar)

```bash
git switch rama1 # Cambia a rama1 (ya creada)
git switch -c rama1 # Crea y cambia a rama1
```

Por otro lado, `git checkout` funciona exactamente igual a `git switch` pero es más una navaja multiusos ya que como hemos visto anteriormente, se utiliza tambien para desacer cambios y muchas cosas más asique desaconsejo su uso.

## Combinar Ramas

Cuando quieres combinar ramas se utiliza `git merge`. Dado el siguiente caso:

[![](https://mermaid.ink/img/pako:eNp9UEFugzAQ_AracxQKtCThmkStVFU9tL1xWewFW8U2MutKEeLvNUHKJWr3NDuz2hnNBMJJggo6zc8eB1XbJI5wxmi-x41HK1TSEnLwdK8fX87H1_evz8Sgtv_Ifz5YMWzAkI8_ZEw2LUoNrMhQDVWEEv13DbWd4x0Gdh8XK6BiH2gDYZDIdNLYeTRQtdiPN_YsNTt_I3uHkuI6AV-GtYNxsRbOtrpb-OD7SCvmYazSdJG3sScVmm3MmY5aKvSsfg5lWublHvOCyl2BT0UhRZMd9m3-mLVy95DlCPO8Abr6v62FX3uffwGPnnzp?type=png)](https://mermaid.live/edit#pako:eNp9UEFugzAQ_AracxQKtCThmkStVFU9tL1xWewFW8U2MutKEeLvNUHKJWr3NDuz2hnNBMJJggo6zc8eB1XbJI5wxmi-x41HK1TSEnLwdK8fX87H1_evz8Sgtv_Ifz5YMWzAkI8_ZEw2LUoNrMhQDVWEEv13DbWd4x0Gdh8XK6BiH2gDYZDIdNLYeTRQtdiPN_YsNTt_I3uHkuI6AV-GtYNxsRbOtrpb-OD7SCvmYazSdJG3sScVmm3MmY5aKvSsfg5lWublHvOCyl2BT0UhRZMd9m3-mLVy95DlCPO8Abr6v62FX3uffwGPnnzp)

Si nos encontramos en la rama `main` y ejecutamos

```bash
git merge feature
```

A la rama `main` se le incorporaran los cambios de la rama `feature`:

[![](https://mermaid.ink/img/pako:eNqFkU1vgzAMhv8K8hmVARttubbVJk3TDttuXNzEkGgkQcGZVCH--0Ir9dJ95OS8j789gXCSoIZO86PHQTU2iU84YzTf2kePVqikJeTg6Zbvng6759eP98Sgtn_gXxP8k8yQ7-inaEghsugo4yzTQhpgRYYaqKMp0X820Ng5-mFg93ayAmr2gVIIg0SmvcbOo4G6xX68qgep2fmr2DuUFL8T8Gm4bG1cSgtnW90tevB9lBXzMNZZtuBV3KwKx1XsMxu1VOhZfW2rrCqqDRYlVesSH8pSimO-3bTFfd7K9V1eIMxzCnSu_3I50flS8zedEIyH?type=png)](https://mermaid.live/edit#pako:eNqFkU1vgzAMhv8K8hmVARttubbVJk3TDttuXNzEkGgkQcGZVCH--0Ir9dJ95OS8j789gXCSoIZO86PHQTU2iU84YzTf2kePVqikJeTg6Zbvng6759eP98Sgtn_gXxP8k8yQ7-inaEghsugo4yzTQhpgRYYaqKMp0X820Ng5-mFg93ayAmr2gVIIg0SmvcbOo4G6xX68qgep2fmr2DuUFL8T8Gm4bG1cSgtnW90tevB9lBXzMNZZtuBV3KwKx1XsMxu1VOhZfW2rrCqqDRYlVesSH8pSimO-3bTFfd7K9V1eIMxzCnSu_3I50flS8zedEIyH)
