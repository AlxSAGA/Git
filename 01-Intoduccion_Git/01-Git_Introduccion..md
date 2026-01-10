- Tags: #Git
---
# Áreas de Desarrollo en Git
[Git](https://git-scm.com/) Documentacion.

#### 1. Directorio de Trabajo (Working Directory)
- Es tu carpeta local donde editas los archivos
- Aquí haces cambios directamente en los archivos
- Los cambios aún no están siendo rastreados por Git
#### 2. Área de Stage (Staging Area)
- Zona de preparación donde agregas los cambios que quieres commitear
- Usas `git add` para mover cambios del directorio al stage
- Te permite seleccionar qué cambios específicos incluir en el próximo commit
#### 3. Repositorio (Repository)
- Donde se guardan permanentemente los cambios confirmados
- Usas `git commit` para mover cambios del stage al repositorio
- Contiene el historial completo de todos los commits
**Flujo típico:**  
Directorio → `git add` → Stage → `git commit` → Repositorio
El **árbol de Git** es la representación de este flujo de tres niveles que te permite tener un control preciso sobre tu historial de versiones. Te obliga a pasar por un **área de preparación (stage)** donde decides qué cambios son lo suficientemente importantes como para ser guardados en la historia definitiva de tu proyecto (el repositorio).
#### Instalación y Configuración
[Git](https://git-scm.com/downloads) Repositorio ofical para descargar **Git**

| Comando             | Descripción              |
| ------------------- | ------------------------ |
| `git --version`     | Verificar versión de Git |
| `git config --list` | Listar configuración     |

---
