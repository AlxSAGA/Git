- Tags: #Restore

# `git restore`

#### ¿Para qué sirve?
**Revertir cambios** en tu directorio de trabajo o sacar archivos del área de staging.
#### Comandos Esenciales
##### Descarta cambios en el Working Directory
```bash
git restore <archivo>          # Descarta cambios en un archivo
git restore .                  # Descarta TODOS los cambios pendientes
git restore *.js              # Descarta todos los archivos .js
```
##### Saca archivos del Staging Area
```bash
git restore --staged <archivo>  # Saca un archivo del stage
git restore --staged .         # Saca TODOS los archivos del stage
```
##### Restaura versión específica
```bash
git restore --source=HEAD~1 <archivo>  # Versión del commit anterior
git restore --source=a1b2c3d <archivo> # Versión de un commit específico
```
---
#### Combinaciones Útiles
##### 🔍 Ver qué pasaría (simulación)
```bash
git restore --dry-run <archivo>    # Muestra qué se restauraría
```
##### Guarda cambios temporales antes de restaurar
```bash
git stash         # Guarda cambios temporales
git restore .     # Restaura
git stash pop     # Recupera cambios
```
---
---
## Recordatorio
- **`git restore`** es el reemplazo moderno de:
  - `git checkout -- <archivo>`
  - `git reset HEAD <archivo>`
- **¡Cuidado!** Los cambios desechados con `git restore` no se pueden recuperar.