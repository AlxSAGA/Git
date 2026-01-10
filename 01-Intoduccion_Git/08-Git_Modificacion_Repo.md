- Tags: #rm

**Modificando Repo**

| Comando           | Explicación                                                                           | Sintaxis y Ejemplos                                                                                                                                                 |                                                           |
| ----------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| **`git rm`**      | **Elimina archivos** del directorio de trabajo **y del área de staging**.             | `git rm <archivo>` (Elimina y deja unstaged)  <br>`git rm --cached <archivo>` (Solo del staging, no del filesystem)  <br>`git rm -f <archivo>` (Fuerza eliminación) |                                                           |
| **`git mv`**      | **Renombra o mueve** archivos **y prepara** el cambio para commit.                    | `git mv <archivo-viejo> <archivo-nuevo>`  <br>`git mv <archivo> <nueva-carpeta/>`                                                                                   |                                                           |
| **`git clean`**   | Elimina archivos no rastreados del WD                                                 | `git clean [opciones]`                                                                                                                                              | `git clean -n` (simulación)  <br>`git clean -f` (elimina) |
| **`git add -u`**  | Agrega al staging solo archivos modificados/eliminados                                | `git add -u`                                                                                                                                                        | `git add -u`                                              |
| **`git add -A`**  | Agrega todos los cambios (nuevos, modif, eliminados)                                  | `git add -A`                                                                                                                                                        | `git add -A`                                              |
**Nota** Una ves eliminado, etc un archivo de git cuando ejecutemos: `git status` tendremos que agregar ese cambio con
```bash
git add Nombre_archivo
```

Y luego Ejecutamos:
**-m** para dejar un mensaje corto
```bash
git commit -m "Mensaje" -a
```

**Nota** Para abrir nuestro editor predefinido solo ejecutamos:
```bash
git commit # Abre el editor y sube el commit cuando se cierra
```
##### Notas importantes:
- **`git rm` vs `rm`**: Usar `git rm` es equivalente a eliminar el archivo manualmente y luego hacer `git add` sobre esa eliminación.
- **`git mv` vs `mv`**: Similar a `git rm`, es equivalente a mover manualmente y luego hacer `git add` para ambos archivos (origen y destino).
- **`git restore`**: Es el comando moderno para deshacer cambios, que reemplaza en muchos casos a `git checkout -- <archivo>` y `git reset HEAD <archivo>`.
- **`git commit -a`**: Saltea el área de staging y hace commit de todos los archivos rastreados que han sido modificados (equivale a `git add -u` + `git commit`).