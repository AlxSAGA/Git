- Tags: #PullRequest
---
# **Pull Request (PR)** - Solicitud de Cambios
Un **Pull Request** es una **solicitud para fusionar cambios** de una rama a otra (normalmente de tu fork a un repo original). Es la forma de **contribuir a proyectos** en GitHub/GitLab.

##### 1. Revisión de código (Code Review)
- Otros desarrolladores revisan tus cambios
- Discuten mejoras y fixes
##### 2. Integración controlada
- Tests automáticos se ejecutan
- Verificar que no rompe nada
##### 3. Documentación de cambios
- Explicación de qué y por qué se cambió
- Relación con issues/tickets

#### Crear un Pull Request
##### 1. Desde GitHub Web:
- Navegar a TU fork
- Click "Compare & pull request"
- Llenar título y descripción
- Click "Create pull request"
##### 2. Desde GitHub CLI:
```bash
gh pr create --title "Mi feature" --body "Descripción de cambios"
```
##### 3. Desde Git tradicional:
- Push cambios a tu fork
- Ir a GitHub manualmente
- Crear PR desde la interfaz web
### Estados de un PR
###### **Open** - Esperando revisión
###### **In review** - Siendo revisado
###### **Approved** - Aprobado para merge
###### **Changes requested** - Necesita correcciones
###### **Merged** - Fusionado exitosamente
###### **Closed** - Rechazado o abandonado


### Tipos de PR

###### **Feature** - Nueva funcionalidad

###### **Bug fix** - Corrección de errores

###### **Documentation** - Mejoras docs

###### **Refactor** - Mejoras de código

###### **Style** - Cambios de formato
---

### Herramientas de PR
###### **GitHub Actions** - CI/CD automático
###### **Reviewers** - Asignar revisores
###### **Labels** - Etiquetar tipo de PR
###### **Assignees** - Asignar responsables
###### **Linked issues** - Vincular con tickets