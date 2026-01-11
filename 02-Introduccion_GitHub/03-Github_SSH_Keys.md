- Tags: #SSHKeys

# Creación de Llaves SSH para GitHub
- **Conexión segura** sin escribir credenciales cada vez
- **Mayor seguridad** que HTTPS con contraseñas
- **Automático** una vez configurado
---
#### Pasos para Crear Llaves SSH

##### 1. Verificar llaves existentes
```bash
ls -al ~/.ssh
# Buscar: id_rsa, id_ed25519, id_ecdsa
```
##### 2. Generar nueva llave SSH (Elige una opción)
**Nota** Si ya tenemos llaves ssh, No es necesario crear nuevas
###### Opción 1: Ed25519 (Recomendada)
```bash
ssh-keygen -t ed25519 -C "tu_email@ejemplo.com"
```
###### Opción 2: RSA (Compatibilidad)
```bash
ssh-keygen -t rsa -b 4096 -C "tu_email@ejemplo.com"
```
##### 3. Especificar ubicación (Presiona Enter para default)
```
Enter file in which to save the key (/home/usuario/.ssh/id_ed25519):
```
##### 4. Crear passphrase (Opcional pero recomendado)
**Nota** Si no queremos **passphrase**, damos enter para que quede vacio
```
Enter passphrase (empty for no passphrase):
[Tu passphrase segura]
```
---
---
#### Configurar SSH Agent

##### 1. Iniciar el agent
```bash
eval "$(ssh-agent -s)"
# Debe mostrar: Agent pid 12345
```
##### 2. Agregar llave al agent
```bash
ssh-add ~/.ssh/id_ed25519
```
##### 3. Configurar automáticamente (opcional)
Agregar esto a `~/.ssh/config`:
```
Host github.com
  AddKeysToAgent yes
  IdentityFile ~/.ssh/id_ed25519
```
---
#### Copiar Llave Pública al Portapapeles

##### Linux:
```bash
sudo apt-get install xclip  # Instalar si es necesario
xclip -selection clipboard < ~/.ssh/id_ed25519.pub
```
##### macOS:
```bash
pbcopy < ~/.ssh/id_ed25519.pub
```
##### Windows (Git Bash):
```bash
cat ~/.ssh/id_ed25519.pub | clip
```
---
#### 🌐 Agregar Llave a GitHub

##### 1. Ir a configuración de GitHub
   **settings/ssh** -> Buscar esta opcion
##### 2. Hacer clic en "New SSH key"
   - **Title**: Identificador (ej: "Laptop Personal")
   - **Key**: Pegar llave pública completa
##### 3. Verificar conexión
```bash
ssh -T git@github.com
```
**Debería mostrar:**
```
Hi usuario! You've successfully authenticated, but GitHub does not provide shell access.
```
---
#### 🔧 Configurar Repositorio para SSH

##### 🔄 Cambiar remote de HTTPS a SSH
```bash
# Elegir ssh o https
git remote add origin https://github.com/usuario/repo.git # para https
git remote add origin git@github.com:usuario/repo.git # para ssh

# Resultado final:
git remote -v
# origin  git@github.com:usuario/repo.git (fetch)
# origin  git@github.com:usuario/repo.git (push)
```

Si ya existe un remote se puede eliminar:
```
# Primero eliminar el origin existente
git remote remove origin
```

Si ya existe un remote con otro nombre, se puede renombrar
```bash
# Luego renombrar (ejemplo: si se llama 'upstream')
git remote rename upstream origin

# Ahora cambia la URL
git remote set-url origin git@github.com:AlxSAGA/SQL.git
```

---
---
#### Tips de Seguridad

##### Nunca compartas tu llave privada
- `id_ed25519` → **PRIVADA** (guardar segura)
- `id_ed25519.pub` → **PÚBLICA** (compartir)
##### Usa passphrase fuerte
- Mínimo 12 caracteres
- Mix de mayúsculas, números, símbolos
##### Rotar llaves periódicamente
- Cada 6-12 meses
- Eliminar llaves viejas de GitHub
##### 📱 Múltiples dispositivos
- Crear llave única por dispositivo
- Títulos descriptivos en GitHub
---
---
## Comandos Rápidos de Verificación

### 🔍 Ver estado de conexión
```bash
ssh -T git@github.com
```

### Listar llaves cargadas
```bash
ssh-add -l
```

### Eliminar llave del agent
```bash
ssh-add -d ~/.ssh/id_ed25519
```
