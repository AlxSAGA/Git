
- Tags: #Commits

# Modificar y Deshacer Commits `git commit --amend`
**Modifica el último commit** (mensaje, archivos o autor)
##### Cambiar mensaje del último commit
```bash
git commit --amend -m "Nuevo mensaje"
```

##### Agregar cambios al repositorio remoto
- **`--force`**: Sobrescribe el remoto sin importar nada ⚠️ (peligroso)
- **`--force-with-lease`**: Verifica que nadie más haya hecho push antes de sobrescribir (más seguro)
```bash
git push --force-with-lease
```
##### Agregar archivos olvidados al último commit
```bash
git add archivo-olvidado.py
git commit --amend --no-edit  # Mantiene el mensaje anterior
```
##### Cambiar autor del último commit
```bash
git commit --amend --author "Nombre <email>"
```
---
---
#### `git revert` - Deshacer de forma segura
**Crea un nuevo commit que deshace cambios anteriores**
##### Revertir último commit
```bash
git revert HEAD
```
##### Revertir commit específico
```bash
git revert a1b2c3d
```
##### Revertir merge commit
```bash
git revert -m 1 <merge-commit-hash>
```
---
#### `git rebase -i` para Reescritura de Historia
**Editar múltiples commits interactivamente**
##### ✂️ Reordenar, editar, combinar commits
```bash
git rebase -i HEAD~3  # Últimos 3 commits

# Una ves terminado los cambios y tendremos nuevos hashes
git rebase --continue
```
### 🎯 Comandos en rebase interactivo:
- `pick` - Mantener commit
- `reword` - Cambiar mensaje
- `edit` - Editar commit
- `squash` - Combinar con anterior
- `drop` - Eliminar commit
---
---
## REGLA DE ORO

##### Para commits LOCALES (no subidos):
```bash
# Usa --amend, reset, rebase -i libremente
```
##### Para commits PÚBLICOS (ya subidos):
```bash
# Usa SOLO git revert para evitar problemas
# Nunca hagas reset --hard de commits públicos
```
---
#### Tips

##### Ver historia de cambios
```bash
git reflog  # Muestra TODAS las acciones, incluso las "perdidas"
```
##### Recuperar commit después de reset --hard
```bash
git reflog
git reset --hard HEAD@{1}  # Volver a estado anterior
```
##### Estado seguro para probar
```bash
git stash        # Guardar cambios temporales
# Probar comandos peligrosos
git stash pop    # Recuperar cambios
```
**¡Recuerda:** Nunca reescribas historia de commits que ya hayas compartido con otros!