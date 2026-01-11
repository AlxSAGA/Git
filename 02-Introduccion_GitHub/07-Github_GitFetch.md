- Tags: #gitfetch

# `git fetch`
**Descarga cambios** del remoto pero **NO fusiona** con tu código local. Solo actualiza las referencias.

---
#### Comandos Esenciales

##### Traer todo del remoto:
```bash
git fetch
```
Una ves que se traigan los cambios, Cambiamos a la rama para poder verlos
```Shell
git switch --detach origin/main # Se crea rama temporal para visualizar los cambios.
```

Volvemos a la rama principal para integra los cambios de la rama temporal a la principal
```Shell
git pull
```
Si existen conflictos, revisamos con que cambios nos queremos quedar

---
---
#### Ver información
##### Ver ramas remotas:
```bash
git branch -r
```
##### Ver diferencias:
```bash
git diff main origin/main
```
##### Ver commits nuevos:
```bash
git log main..origin/main
```
---