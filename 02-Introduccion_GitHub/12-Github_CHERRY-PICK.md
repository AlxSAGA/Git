- Tags: #cherry-pick
---
# `git cherry-pick`

**Aplica los cambios de un commit específico** en tu rama actual. Como "copiar y pegar" un commit.

---
#### Comando Básico
```bash
git cherry-pick <hash-del-commit>
```
##### Para qué usarlo
- **Aplicar un fix específico** de otra rama
- **Recuperar un commit** que se perdió
- **Mover un cambio individual** sin traer toda la historia
---
##### Importante
- **Copia el commit** (crea uno nuevo con mismo contenido)
- **Puede generar conflictos** (resolver como en merge)
- **Diferente de merge/rebase** (solo commits específicos)
---
##### Ejemplo
```bash
# Traer un fix de la rama feature a main
git checkout main
git cherry-pick a1b2c3d
```

#### Cuándo Usar Cherry-Pick
##### Ideal para:
- Aplicar fixes específicos
- Mover commits individuales
- Recuperar commits perdidos
##### Evitar para:
- Mover muchos commits (mejor rebase)
- Historial complejo (mejor merge)
- Commits dependientes entre sí