- Tags: #Checkout

# `git checkout` (Modo Básico)

#### ¿Para qué sirve?
**Cambiar de rama** o **restaurar archivos** en tu directorio de trabajo desde el ultimo **commit** en el area **local**.
**Nota** Si ya esta preparado un archivo, Necesitamos `git reset`
#### Comandos Esenciales

##### Cambiar de rama
```bash
git checkout <nombre-rama>       # Cambia a una rama existente, NO recomendado
git checkout -b <nueva-rama>     # Crea una nueva rama y cambia a ella
git checkout -                   # Vuelve a la rama anterior
```
##### Restaurar archivos
```bash
# Recomendado usar git restore
git checkout -- <archivo>        # Descarta cambios en un archivo
git checkout -- .               # Descarta TODOS los cambios pendientes
git checkout HEAD -- <archivo>   # Restaura versión del último commit
```
##### Viajar en el tiempo
```bash
git checkout <commit-hash>      # Cambia a un commit específico (modo detached HEAD)
git checkout HEAD~1             # Cambia al commit anterior
```
---
#### Combinaciones Útiles

##### Cambiar y crear rama desde remoto
```bash
git checkout -b nueva-rama origin/main  # Crea rama local desde remoto
```
##### Recuperar archivo de otra rama
```bash
git checkout otra-rama -- <archivo>     # Trae un archivo de otra rama
```
---
---
## Recordatorio
- **`git checkout -- <archivo>`** descarta cambios **PERMANENTEMENTE**
- Usa **`git checkout -b`** para crear ramas nuevas rápidamente
- Al cambiar a commits antiguos estarás en estado **"detached HEAD"**
- Para salir de detached HEAD: `git checkout <nombre-rama>`