- Tags: #SubirRepositorio
---
#### ¿Qué es un Fork?
Un **fork** es una **copia personal** de un repositorio de otro usuario. Te permite experimentar, modificar y contribuir sin afectar el proyecto original.
#### ¿Para qué sirve?
##### 1. Contribuir a proyectos open source
- Hacer cambios sin permisos especiales
- Proponer mejoras via Pull Requests
##### 2. Experimentar libremente
- Probar ideas sin miedo a romper nada
- Modificar para necesidades personales
##### 3. Usar como base para nuevo proyecto
- Partir de código existente
- Personalizar completamente
#### Fork vs Clone

| **Fork**                   | **Clone**                    |
| -------------------------- | ---------------------------- |
| **Copia en GitHub** (nube) | **Copia local** (tu máquina) |
| Necesitas cuenta GitHub    | No necesitas cuenta          |
| Para contribuir/publicar   | Para trabajar localmente     |

##### Buenas prácticas para contribuir
1. Hacer fork del repo original
2. Clonar TU fork (no el original)
3. Crear branch para tu feature
4. Hacer commits descriptivos
5. Push a TU fork
6. Crear Pull Request al original
##### Para proyectos personales
- Puedes modificar libremente tu fork
- No necesitas hacer Pull Request
- Es tu repositorio independiente

**Nota Importante**, Para realizar un **fork** tenemos que ir a la url o al proyecto que quremos realizar un **fork**,
Damos clik en: **( Fork )** desde **github**, Para que se cree
Otra forma es ingresando a un archivo y le damos click en el boton de editar, y tambien nos permitiria realizar un **fork** de ese archivo:
Una ves que realizemos el **fork** ya deberias tenerlo en nuestro **github** personal y entonces si ya podemos clonar el proyecto
**Clonar Fork** de nuestro repositorio
```bash
git clone https://github.com/TU-USUARIO/repo-forkeado.git
```

Una ves terminados los cambios, podemos **sincronizar** con el original, Primero tenemos que agregar los cambios al area de preparacion, y despues **commitear**
Ahora los cambios que subamos solo estarian subidos a nuestro **fork** de nuestro repositorio de **github**, no en el original
**Subir** nuestros cambios a nuestro **Fork**
```bash
git push origin main
```

Agrega el repositorio **ORIGINAL** como referencia.
Cuando haces un **fork** de un proyecto y quieres mantenerte actualizado con los cambios del original.
```bash
git remote add upstream https://github.com/USUARIO-ORIGINAL/repo.git
```

Descarga los cambios del repositorio original **SIN mezclarlos** en tu código.
Ver qué ha cambiado en el proyecto original antes de actualizar tu fork.
```
git fetch upstream
```

**Mezcla** los cambios descargados en tu rama actual.
Actualizar tu fork con las últimas mejoras del proyecto original.
```
git merge upstream/main
```

Tomas un fork de un proyecto open-source → Trabajas en tu versión → Quieres actualizarte con los cambios del proyecto principal.