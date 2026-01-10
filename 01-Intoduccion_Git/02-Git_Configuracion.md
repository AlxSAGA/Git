- Tags: #Configuracion
#### Configuración Básica: Correo Electrónico y Nombre
Git necesita saber quién eres para asociar tu nombre y correo a cada _commit_ que realizas. Esta información es crucial para el trabajo en equipo.

| Comando      | Descripción        |
| ------------ | ------------------ |
| `git config` | Configurar usuario |
| `git config` | Configurar correo  |
**Configuracion:**
- La opción `--global` significa que esta configuración se aplicará a **todos tus repositorios** en tu máquina. Si quieres una configuración diferente para un repositorio específico, quita el `--global` y ejecuta el comando dentro de la carpeta del proyecto.
```bash
# Configura tu nombre de usuario (usa comillas si tiene espacios)
git config --global user.name "Tu Nombre"

# Configura tu dirección de correo electrónico
git config --global user.email "tu.email@ejemplo.com"
```

**Verificar Configuraciones**
```bash
# Muestra todas las configuraciones guardadas
git config --list

# Muestra solo el correo configurado
git config user.email

# Muestra solo el nombre configurado
git config user.name
```

#### Jerarquías de configuración en Git: **system**, **global** y **local**
|Jerarquía|Alcance|Archivo de Configuración (Ejemplos de ubicación)|Comando para configurar|Orden de Precedencia (Mayor a Menor)|
|---|---|---|---|---|
|**`--system`**|**Todos los usuarios** en el sistema.|- **Linux/Mac:** `/etc/gitconfig`  <br>- **Windows:** `C:\Program Files\Git\etc\gitconfig`|`git config --system <key> <value>`|3️⃣ (La más débil)|
|**`--global`**|**Todos los repositorios** del usuario actual.|- **Linux/Mac:** `~/.gitconfig`  <br>- **Windows:** `C:\Users\<USER>\.gitconfig`|`git config --global <key> <value>`|2️⃣|
|**`--local`**|**Solo el repositorio actual.** (Valor por defecto)|Dentro de cada repositorio, en la carpeta `.git/config`|`git config --local <key> <value>` o solo `git config <key> <value>`|1️⃣ (La más fuerte)|
#### Explicación y Uso Práctico
- **Precedencia:** Si una misma clave (por ejemplo, `user.email`) está definida en los tres niveles, Git usará el valor definido en el nivel **local** (el que tiene la precedencia más alta), luego el global y por último el system.
- **Cuál usar:**
    - **`--local`:** Para configuraciones específicas de un proyecto. Ejemplo: credenciales de deploy, un hook específico, la URL de un remote particular.
    - **`--global`:** **Es el más común.** Para tu identidad (nombre y correo), tus alias preferidos, tu editor favorito, y otras preferencias personales que quieres aplicar en todos tus proyectos.
    - **`--system`:** Para políticas de empresa o configuración general en una máquina compartida. Rara vez lo usa un usuario individual.

Puedes usar el comando `git config --list --show-origin` para ver todas las configuraciones activas y **exactamente de qué archivo proviene cada una**, lo que es muy útil para resolver conflictos de configuración.
```bash
git config --list --show-origin

# Ver solo configuraciones a nivel sistema
git config --system --list

# Ver solo configuraciones globales
git config --global --list

# Ver solo configuraciones locales
git config --local --list
```