- Tags: #Alias

# Alias en Git
#### Crear Alias
```bash
# Crear alias permanente
git config --global alias.<atajo> "<comando>"

# Ejemplo:
git config --global alias.co "checkout"
```
---
#### Alias Útiles

##### Estado y Log
```bash
git config --global alias.s "status -s"          # Estado corto
git config --global alias.lg "log --oneline --graph --all"  # Log bonito
git config --global alias.ll "log --pretty=format:'%C(yellow)%h %C(cyan)%ad %Cblue%an%C(auto)%d %Creset%s' --date=short"
```
Se pueden crear alias para: Commits, Ramas, Staging, Diferencias

---
---
#### Ver y Editar Alias

##### Ver alias existentes
```bash
git config --global --get-regexp alias   # Listar todos los alias
git config --global alias.*              # Ver configuración
```
##### Editar manualmente
```bash
code ~/.gitconfig  # VS Code
nvim ~/.gitconfig  # Neovim
```
##### Eliminar alias
```bash
git config --global --unset alias.<atajo>
```
---
---
#### ⚠️ Tips Importantes
- Usa `--global` para alias en todos tus proyectos
- Los alias con `!` ejecutan comandos de shell
- Puedes usar funciones complejas en alias
- Los alias se guardan en `~/.gitconfig`