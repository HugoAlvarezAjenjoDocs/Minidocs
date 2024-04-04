# Git (Control de Versiones)

Git es un sistema de control de versiones que te ayuda a rastrear cambios en tus archivos y colaborar con otros en proyectos de software.
Con Git, puedes realizar un seguimiento de las diferentes versiones de tus archivos, revertir cambios si es necesario y fusionar el trabajo de diferentes personas de manera eficiente.
Es especialmente útil para equipos de desarrollo de software que trabajan en proyectos complejos, ya que proporciona una forma estructurada de gestionar y compartir código.
Con Git, puedes trabajar de forma colaborativa y mantener un historial claro de todos los cambios realizados en tus proyectos.

## Instalación

Para instalar git tienes que ir a su [pagina oficial](https://git-scm.com/). Descargarte el instalador y ejecutarlo.

En el proceso de instalación, te permitirá configurar git. Entre las que destacan la selección del editor por defecto, por defecto utiliza vim, pero se puede cambiar a VSCode.
También esta la del nombre por defecto de la rama principal, si dejamos que Git decida, la nombrará como `Master`, en este caso aconsejo cambiarla a `main` que es el nombre estándar que se utiliza actualmente.

Una vez instalado, veremos que tendremos instalados varios programas. En windows cambe destacar que tenemos Git CMD y Git Bash, este último es para usarlo como con una terminal de Bash (Linux), en cualquier caso los comandos de Git son exactamente los mismos. Yo los ejecuto desde PowerShell

También tenemos instalada Git GUI que es por si no queremos usar la consola pero al trabajar con Git se suele hacer con linea de comandos por lo que no la recomiendo.

Para comprobar su correcto funcionamiento ejecutaremos

```powershell
git --version
```

## Configuración básica

Puedes configurar Git desde la linea de comandos con `git config`, si utilizas también el párametro `--global` la diferencia es que mientras que uno hace una configuracion concreta en un repositorio, con gobal se aplican cambios generales por defecto.

Para establecer tu nombre y tu email:

```powershell
git config --global user.name "Tu nombre"
git config --global user.email "Email@gmail.com"
```

Para cambiar tu editor por defecto puedes utilizar:

```powershell
git config --global core.editor "code --wait"
```

Esto lo que hace es establecer code (VSCode) como editor por defecto y esperar a que se cierre el editor.
Para cualquier otro editor basta con escibirlo tal y como lo abririas por terminal. `notepad`, `notepad++`, `vim`, `nvim`, `atom`...

Si no has cambiado la configuración de master a main, recomiendo que lo hagas, desde terminal se puede hacer con:

```bash
git config --global init.defaultBranch main
```

Si quieres abrir el archivo de configuración y ediralo en el editor que hayas seleccionado, puedes hacerlo con:

```powershell
git config --global -e
```

## Ayuda

Al igual que en windows o bash con `help` o `man` git tiene un manual para saber que hace cada comando.

```powershell
git help # Ayuda de git general
git help COMMAND # Ayuda de un comando especifico
```
