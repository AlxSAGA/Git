- Tags: #Reflog

# Git Reflog - Tu Salvavidas de Git
Es el **registro de referencia** de Git que muestra el **historial completo de todos los cambios** en tus referencias (ramas, HEAD, etc.). Es tu **bitácora de navegación** en Git.

#### ¿Por qué es tan importante?
- **Recuperar commits perdidos** (¡tu salvavidas!)
- **Ver todo lo que has hecho** (inclusive cambios "borrados")
- **Encontrar estados anteriores** del repositorio
---
#### Comandos Esenciales
##### Ver reflog completo
```bash
git reflog
```
##### Ver reflog específico
```bash
git reflog show <rama>    # Reflog de una rama específica
git reflog show HEAD      # Reflog de HEAD
```
---
#### Casos de Uso Prácticos

##### 1. Recuperar commit después de `reset --hard`
```bash
# Después de un reset destructivo
git reflog
# Encontrar el hash del commit perdido
git reset --hard HEAD@{1}
```
##### 2. Recuperar rama eliminada
```bash
# Si borraste una rama por error
git reflog
# Encontrar el último commit de la rama
git branch rama-perdida <hash>
```
##### 3. Ver historial de cambios recientes
```bash
git reflog --date=relative
```
---
#### 📊 Entender la Salida
Ejemplo de salida:
```
a1b2c3d (HEAD -> main) HEAD@{0}: commit: Add new feature
d4e5f6g HEAD@{1}: reset: moving to HEAD~1
c7h8i9j HEAD@{2}: commit: Fix login bug
```
- **`HEAD@{0}`**: Estado actual
- **`HEAD@{1}`**: Estado anterior
- **`HEAD@{2}`**: Dos estados atrás
---
---
#### Tips

##### El reflog es local
- Solo muestra **tus acciones locales**
- No se sincroniza con el remoto
- **Expira después de 90 días** (por defecto)
##### Configurar tiempo de expiración
```bash
# Cambiar tiempo de expiración (ej: 180 días)
git config gc.reflogExpire 180.days
git config gc.reflogExpireUnreachable 180.days
```
##### Limpieza manual
```bash
git reflog expire --expire=now --all
git gc --prune=now
```
---
---
#### Buenas Prácticas
1. **Revisa el reflog** antes de pánicos
2. **Usa `--dry-run`** antes de acciones destructivas
3. **Crea branches de respaldo** si vas a experimentar
4. **¡El reflog es tu amigo!** No temas usarlo
**¡Recuerda:** `git reflog` es tu caja negra de Git. Siempre hay esperanza después de un accidente! 🚑