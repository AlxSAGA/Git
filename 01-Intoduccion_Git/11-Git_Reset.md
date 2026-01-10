- Tags: #Reset

# `git reset`

#### ¿Para qué sirve?
**Deshacer commits** y cambios en el área de staging, moviendo el puntero de la rama.
#### Modos Principales

##### `--soft` - Mantiene cambios en staging
```bash
git reset --soft HEAD~1        # Deshace commit pero mantiene cambios en staging
git reset --soft <commit-hash> # Vuelve a commit específico, cambios en staging
```

##### `--mixed` - Mantiene cambios en working directory (DEFAULT)
```bash
git reset --mixed HEAD~1       # Deshace commit y saca cambios del staging
git reset HEAD~1               # --mixed es el modo por defecto
```

##### `--hard` - Elimina todo (PELIGROSO)
```bash
git reset --hard HEAD~1        # Deshace commit y ELIMINA cambios permanentemente
git reset --hard <commit-hash> # Vuelve a commit y descarta todo lo posterior
```
---
---
#### USO PELIGROSO

##### ❌ Reset --hard con cambios no commitados
```bash
git reset --hard HEAD      # ELIMINA TODOS los cambios no commitados ⚠️
```
##### 🔍 Recuperar después de reset --hard
```bash
git reflog                 # Muestra historial de acciones
git reset --hard HEAD@{1}  # Recupera a estado anterior
```
---
## Tips Importantes

- **`--soft`**: Los cambios quedan **en staging**
- **`--mixed`**: Los cambios quedan **en working directory** (por defecto)
- **`--hard`**: **ELIMINA** cambios permanentemente ⚠️
- **Siempre verifica** con `git status` antes de reset
- Usa **`git reflog`** como salvavidas después de resets destructivos