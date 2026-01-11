- Tags: #GitPull

# `git pull` - Traer Cambios del Repositorio Remoto

**Descarga los últimos cambios** del repositorio remoto y **los fusiona** con tu rama local. Es la combinación de `git fetch` + `git merge`.
**Nota** Puede traer conflictos
#### Uso Básico
##### 📥 Traer cambios de la rama actual:
```bash
git pull
```
##### Traer cambios de rama específica:
```bash
git pull origin main
```
##### Traer cambios con rebase (más limpio):
```bash
git pull --rebase
```

---
---
#### Errores Comunes y Soluciones

##### "Merge conflict"
```bash
# Ocurre cuando hay cambios contradictorios
# Resolver conflictos manualmente
git status               # Ver archivos conflictivos
# Editar archivos, luego:
git add .
git commit
```
##### "Non-fast-forward"
```bash
# Git no puede fusionar automáticamente
git pull --rebase        # Intentar con rebase
# o
git stash
git pull
git stash pop
```
##### "Please commit your changes"
```bash
# Tienes cambios sin commitear
git stash        # Guardar cambios temporales
git pull
git stash pop    # Recuperar cambios
```
---
## Flujo de Trabajo Típico

```mermaid
graph LR
    A[🌐 Repositorio remoto] --> B[📥 git fetch]
    B --> C[🔄 git merge]
    C --> D[💻 Rama local actualizada]
```
---
---
#### Diferencia entre `git pull` y `git fetch`

### **git pull = git fetch + git merge**
```bash
# Equivalente a:
git fetch origin
git merge origin/main
```
### **git fetch solo descarga:**
```bash
git fetch origin   # Solo trae cambios, no fusiona
git log origin/main # Ver qué hay nuevo
```
---
---