# Commits Avanzados

Hasta ahora solo hemos hecho commits de archivos completos, pero si has usado IntelliJ o VSCode te habrás dado cuenta que puedes commitear ciertos cambios que tú selecciones de un archivo mientras que otros no los tocas.

Esto en terminal se realiza mediante el siguiente comando:

```bash
git add -p <archivo>
```

Esto te mostrará un menú interactivo en el cual tú eliges que cambios añadir o no añadir.

```bash
diff --git a/archivo.txt b/archivo.txt
index 4b9b6c2..30304ea 100644
--- a/archivo.txt
+++ b/archivo.txt
@@ -1,3 +1,5 @@
 Hola
+Contenido 1
 Contenido en la rama principal
+Contenido 2
 Esto es un stage
(1/1) Stage this hunk [y,n,q,a,d,s,e,?]? 
```

El menú al principio no parace muy intuitivo, pero lo acaba siendo tras un par de usos además que si no sabes que hace cada letra, si utilizas `?` te las explica de forma clara.

El resumen rapido es:

- y - stage this hunk
- n - do not stage this hunk
- q - quit; do not stage this hunk or any of the remaining ones
- a - stage this hunk and all later hunks in the file
- d - do not stage this hunk or any of the later hunks in the file
- s - split the current hunk into smaller hunks
- e - manually edit the current hunk
- ? - print help
