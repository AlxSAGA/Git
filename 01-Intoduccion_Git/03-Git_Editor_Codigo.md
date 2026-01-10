- Tags: #EditorCodigo #Colores
# Configurar `core.editor` en Git

#### 1. Para Salir de Vim
*   **La razón más común:** Por defecto, en muchos sistemas (como Linux y Mac), Git usa **Vim** como editor por defecto para escribir mensajes de commit.
*   **El problema:** Si no sabes usar Vim, es **fácil quedar atrapado** sin saber cómo salir. Esto causa frustración y pérdida de tiempo.
*   **La solución:** Configurar un editor que te sea familiar (como VS Code, Nano o Notepad++) te permite escribir y editar mensajes de commit de forma cómoda y sin estrés.
#### 2. Para Escribir Mensajes de Commit Mejores y Más Explicativos
*   Un editor de código moderno te ofrece:
    *   **Sintaxis resaltada:** Puedes formatar el mensaje más claramente.
    *   **Múltiples líneas:** Es fácil escribir mensajes detallados con un título corto y un cuerpo explicativo.
    *   **Corrección ortográfica:** Plugins que ayudan a evitar errores.
*   Esto fomenta la buena práctica de escribir commits significativos, que son cruciales para un historial de proyecto comprensible.
#### 3. Para Resolver Conflictos de Merge de Forma Más Eficiente
*   Cuando Git no puede fusionar cambios automáticamente, entra en un estado de **conflicto**.
*   Git abre tu editor configurado (`core.editor`) con un archivo especial que muestra los cambios en conflicto marcados con `<<<<<<<`, `=======` y `>>>>>>>`.
*   Tener un editor potente como **VS Code** con extensiones para Git hace que la **resolución de conflictos sea visual e intuitiva**, en lugar de tener que editar manualmente esos marcadores en un editor de texto plano.---
#### 4. Para Flujos de Trabajo Interactivos
*   Comandos como `git rebase -i` (rebase interactivo) o `git commit --amend` abren tu editor configurado para que puedas:
    *   Reordenar, editar, combinar o eliminar commits.
    *   Modificar el mensaje del último commit.
*   Tener un editor que manejes bien es esencial para usar estas potentes características con confianza.
#### ¿Cómo Configurarlo?
Usa `git config --global` para aplicar el cambio a todos tus repositorios.

**Ejemplos para editores populares:**
```bash
# Para VS Code
git config --global core.editor "code --wait"

# Para NeoVim
git config --global core.editor "nvim" # Recomendado
git config --global core.editor "nvim --wait"

# Para Nano (simple y fácil de usar)
git config --global core.editor "nano"

# Para Notepad++ (Windows)
git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"

# Para Sublime Text
git config --global core.editor "subl -n -w"
```
**Nota importante:** La opción `--wait` (en VS Code y Sublime) es crucial. Le indica al editor que mantenga la terminal abierta *esperando* a que cierres la ventana del editor. Sin esto, Git procedería inmediatamente sin tu mensaje de commit.
Configurar `core.editor` es **personalizar una herramienta fundamental de tu flujo de trabajo**. Mejora tu experiencia, aumenta tu productividad y te ayuda a escribir un mejor historial de código. Es una de las primeras configuraciones que deberías hacer después de instalar Git.

#### Configuracion Colores Git
```bash
git config --global color.iu true
```