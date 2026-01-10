- Tags: #GitIgnore #Designore

# `.gitignore` - Ignorar Archivos en Git
Es un **archivo de texto** que le dice a Git qué archivos y directorios debe ignorar y no rastrear en el repositorio.
📁 **Múltiples archivos .gitignore** Puedes tener varios archivos en diferentes directorios:
[Plantilas predefinidas](https://github.com/github/gitignore) GitHub ofrece plantillas para diferentes lenguajes:
**Nota** Los archivos que ya fueron rastreados, es decir subidos se tienen que eliminar. agregar la eliminacion, y realizar su commit para que asi, para que git elimine el archivo del **commit**, y ya no sea mostrado
**gitignore** es para archvios que no han sido subidos al are de preparacion
##### Mantener el repositorio limpio
- Evitar subir archivos innecesarios
- Prevenir commits accidentales de archivos sensibles
##### Seguridad
- Proteger información confidencial (contraseñas, API keys)
- Evitar exponer datos privados    
##### Optimización
- Reducir tamaño del repositorio
- Mejorar performance de Git

**Crear** archivo:
```bash
touch .gitignore
```

**Ejemplo** basico, de agregar archivos
```bash
echo "node_modules/" >> .gitignore
echo ".env" >> .gitignore
```

**ls-tree** Muestra todos los archivos que tienen un **commit**
**-r** Muestra todos los archivos y directorios
**--name-only** Solo muestra los nombres de los archivos
**hast** Aqui se pone el hash del **commit**.
```bash
# Tambien podemos poner HEAD, ya que nos lleva siempre al ultimo commit
git ls-tree -r --name-only hash
```

**Designorar** un archivo, En caso de que agregamos todos los archivos **txt** o cual sea la extension, si queremos que uno sea **designorado**, para que si se suba al repositorio remoto,
```bash
# ! designora, para que pueda ser agregado
!nombre_archivo.txt
```

**Verificar** archivos ignorados
```bash
git status --ignored
git check-ignore -v archivo.txt
```

**Forzar** el **add** de archivos ignorados
```bash
git add -f archivo.env
```

**Limpiar** archivos ignorados
```bash
git clean -X -n  # Ver qué se eliminaría
git clean -X -f  # Eliminar archivos ignorados
```

**Archivos ya rastreados** Si un archivo ya fue commitado,
```bash
git rm --cached archivo.txt  # Dejar de trackear
git commit -m "Stop tracking archivo.txt"
```

#### 🌐 Gitignore global
Para ignorar archivos en todos tus proyectos: Creamos un archivo que todos los repositorios lean, para saber que archivos ignorar de manera global, evitando tener que crear uno nuevo cada que se crea un proyecto
```bash
# Tenemos que poner la ruta donde este el gitignore_global
git config --global core.excludesfile ~/.gitignore_global
```
**Nota** El **gitigonore** local de cada repositorio, tiene prioridad sobre nuestro **gitignore_global**.