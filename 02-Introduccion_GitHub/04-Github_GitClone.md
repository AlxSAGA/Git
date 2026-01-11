- Tags: #gitclone #https #ssh #githubcli

# Diferencias al Clonar Repositorios: HTTPS vs SSH vs GitHub CLI

| Método         | URL Ejemplo                           | Autenticación              | Seguridad | Facilidad |
| :------------- | :------------------------------------ | :------------------------- | :-------- | :-------- |
| **HTTPS**      | `https://github.com/usuario/repo.git` | Usuario/Contraseña o Token | 🔓 Buena  | ⭐⭐⭐⭐⭐     |
| **SSH**        | `git@github.com:usuario/repo.git`     | Llaves SSH                 | 🔐 Máxima | ⭐⭐⭐       |
| **GitHub CLI** | `gh repo clone usuario/repo`          | Token OAuth                | 🔐 Máxima | ⭐⭐⭐⭐⭐     |

---
#### HTTPS (Recomendado para principiantes)
##### 🔧 Cómo clonar:
```bash
git clone https://github.com/usuario/repo.git
```
###### Ventajas:
- Funciona en cualquier red (firewalls amigable)
- No configuración adicional necesaria
- Fácil para empezar
###### Desventajas:
- Necesitas escribir credenciales cada vez
- Menos seguro que SSH
- Tokens expiran y necesitan renovación
###### Autenticación:
- Usuario y contraseña (deprecado)
- **Personal Access Token** (recomendado)
---
#### SSH (Recomendado para avanzados)
##### 🔧 Cómo clonar:
```bash
git clone git@github.com:usuario/repo.git
```
###### Ventajas:
- Máxima seguridad (criptografía asimétrica)
- No escribir credenciales nunca más
- Más rápido para operaciones frecuentes
###### Desventajas:
- Configuración inicial compleja
- Problemas en redes restrictivas
- Puertos SSH pueden estar bloqueados
###### Requisitos:
1. Generar llaves SSH (`ssh-keygen`)
2. Agregar llave pública a GitHub
3. Configurar SSH agent
---
#### GitHub CLI (La forma moderna)
##### 🔧 Cómo clonar:
```bash
gh repo clone usuario/repo
```
###### Ventajas:
- Autenticación automática (via `gh auth login`)
- Integración con features de GitHub
- Comandos más simples y intuitivos
- Mejor experiencia de desarrollador
###### Desventajas:
- Necesitas instalar herramienta adicional
- Curva de aprendizaje de nuevos comandos
###### Características únicas:
- Autocompletado en terminal
- Gestión de issues y PRs desde CLI
- Interfaz unificada para toda la plataforma
---
---
### **Para entornos empresariales:**
```bash
# SSH para servidores
# HTTPS para CI/CD
# GitHub CLI para desarrolladores
```
---
---