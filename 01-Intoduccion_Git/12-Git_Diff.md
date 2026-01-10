- Tags: #Diff #show #log

# `git diff`

#### ¿Para qué sirve?
**Comparar diferencias** entre archivos, commits, branches y más.
```bash
# Muestra la data del archivo y tambien solo muestra el commit, Lo que ya esta commiteado
git show "nombre_archivo"
```

Muestra informacion Como identificador del **commit**, **Autor** 
**Head** Inidca hacia a donde apunta el puntero, puede ser a la rama **master**, etc
```bash
git log
git log --oneline # Muestra acortado el commit, Probabilidad de commits repetidos, por se corto

# Modificar para que muestre el commit acortado con mas de 7 caracteres
git config --global core.abbrev <Numero>
```
#### Comparaciones Esenciales

##### Working Directory vs Staging
```bash
git diff                 # Muestra cambios no staged
git diff -- <archivo>    # Cambios no staged en archivo específico
```
##### Staging vs Último Commit
```bash
git diff --staged        # Muestra cambios staged para commit
git diff --cached        # --cached es alias de --staged
```
##### Working Directory vs Último Commit
```bash
git diff HEAD           # Todos los cambios (staged + unstaged)
git diff HEAD -- <archivo> # Cambios totales en archivo específico
```
---
#### Comparaciones con Historia

##### 🔍 Entre Commits
```bash
git diff commit1 commit2     # Compara dos commits específicos
git diff HEAD~2 HEAD        # Último commit vs hace 2 commits
git diff a1b2c3 d4e5f6      # Compara por hash de commit
```

```bash
git diff --name-only hash1 hash2 # Comparamos solo el nombre de los archivos modificados
```
##### Entre Branches
```bash
git diff main develop        # Compara dos branches
git diff HEAD main          # Tu trabajo actual vs main
```
##### Estadísticas de cambios
```bash
git diff --stat             # Muestra resumen de archivos modificados
git diff --numstat          # Estadísticas numéricas
```
---
---
#### Tips Avanzados

##### 🔧 Ignorar espacios en blanco
```bash
git diff -w                  # Ignora cambios de whitespace
git diff -b                  # Ignora cambios de espacios
```
##### 📏 Límite de contexto
```bash
git diff -U5                # Muestra 5 líneas de contexto
git diff -U0                # Sin líneas de contexto
```
##### 🔄 Comparar con branch remoto
```bash
git diff origin/main        # Compara con main remoto
```
---
**¡Recuerda:** `git diff` es tu mejor amigo para entender qué cambió antes de commitear! 