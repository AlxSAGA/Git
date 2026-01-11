- Tags: #gitpush

# 🚀 `git push` - Subir Cambios al Repositorio Remoto
**Nota** Ya debemos tener creado nuestro repositorio desde github
```bash
git push -u origin main # Solo la primera vaes para un nuevo repo
```
**Sube tus commits locales** al repositorio remoto (GitHub, GitLab, etc.). Sincroniza tu trabajo local con el resto del equipo.
**Nota** Para subir un repo local, Priemero necestiamos crear un repositorio en github, **( Create a new Repositorio )** que se llame iguales
#### Uso Básico

##### Subir cambios por primera vez:
```bash
git push -u origin main
```
- `-u`: Establece upstream (relación tracking)
- `origin`: Nombre del remote
- `main`: Rama destino
##### Subir cambios posteriores:
```bash
git push
```
---
#### Casos de Uso Comunes
##### 📤 Subir nueva rama:
```bash
git push -u origin nueva-rama
```
##### Subir tags:
```bash
git push --tags
# o un tag específico
git push origin v1.0.0
```
##### Eliminar rama remota:
```bash
git push origin --delete rama-vieja
```
##### Forzar push (¡Cuidado!):
```bash
git push --force
# Mejor alternativa segura:
git push --force-with-lease
```
---
---
## Flujo de Trabajo Típico

```mermaid
graph LR
    A[📝 Trabajo local] --> B[💾 git add]
    B --> C[✅ git commit]
    C --> D[🚀 git push]
    D --> E[🌐 Repositorio remoto]
```

---
#### Buenas Prácticas

##### Antes de push
```bash
git pull          # Sincronizar cambios remotos
git status        # Verificar estado
git log --oneline # Revisar commits a subir
```
##### Push frecuente:
- Push regular para evitar conflictos
- Push por feature/completado
- Nunca push directo a main sin review
---
---