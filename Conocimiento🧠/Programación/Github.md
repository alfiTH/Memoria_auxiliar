## Configurar usuario en el repositorio
```shell scrip
git config user.name "[nombre]"
git config user.email "[correo]"
```
```[nombre]``` y ```[correo]``` serán el nombre de usuario y correo a configurar  respectivamente 
En caso de querer aplicarlo en todos los repos del ordenador añadir el parámetro ```--global```

## Braches/Ramas

### Crear una nueva branch
```shell 
git branch [nombre]
```
```[nombre]``` será el nombre de la rama que quieras crear
### Moverte en branch
```bash
git checkout [nombre]
```
```[nombre]``` será el nombre de la rama donde quieras moverte
### Combinar branch
```bash
git merge [nombre]
```
```[nombre]``` será el nombre de la rama que quieras combinar
### Borrar branch
```bash
git branch -d [nombre]
```
```[nombre]``` será el nombre de la rama que quieras borrar

## Clonar repositorio
```bash
git clone [url]
```
Donde ```[url]``` es el enlace al repo, este puede ser clonado de diferentes formas
- http, una descarga normal mediante este comando, necesitaras a futuro usuario y contraseña/token para subir las cosas.
- ssh, igual que el http pero este esta ligada a una clave ssh publica/privada, no solicitara usuario ni contraseña ya que se te identificara por esas claves, mire [[Ubuntu#Crear clave SSH]] y [[Github#Registrar clave ssh en Github]]
- Descargar como zip y descomprimirlo donde quieres

## Sincronizar repositorios
### Actualizar local
```bash
git pull
```
este actualizará los archivos locales con la nube de Github, si se han eliminado archivos estos no los traerá 
### Traer archivo de la nube de Github
```bash
git checkout [fichero]
```
```[fichero]``` es la ruta a descargar, puede ser carpetas o ficheros, se puede usar el "." para definir la carpeta actual entera
Este comando también descarga archivos que se hayan eliminado localmente
### Añadir fichero al repositorio
```bash
git add [fichero]
```
Donde ```[fichero]``` será la ruta de la capeta o fichero a añadir al repo
### Confirmación de cambios en el repositorio
```bash
git commit [fichero]
```
``[fichero]`` es la ruta a confirmar, puede ser carpetas o ficheros, se puede usar el "." para definir la carpeta actual entera, este desplegara un nano para escribir un mensaje corto y explicativo de la confirmación
<span style="color:red">***NUNCA USAR EL "-a" O REALIZAR EL COMIT EN LA RAIZ, MUEDE GENERAR COLISIONES Y PROBLEMAS***</span>
Se puede usar el parámetro ``-m`` para escribir un mensaje desde el propio comando delimitado mediante unas ``""``
Si en ese commit quieres cambiar el ususario del commit en vez el definido mediante [[Github#Configurar usuario en el repositorio]] se podrá el siguiente comando para commitear como otra persona:
````bash 
GIT_AUTHOR_NAME="usuario" GIT_AUTHOR_EMAIL="email@hotmail.com" GIT_COMMITTER_NAME="usuario" GIT_COMMITTER_EMAIL="email@hotmail.com" git commit -m "" .
````
En este ejemplo el usuario es "usuario", y su correo "email@hotmail.com"

### Revertir una confirmación
#### Si quieres manterentener los comabios locales
```bash 
git reset --soft HEAD~1
```

#### Si quieres borrar los cambios locales
```bash 
git reset --hard HEAD~1
```

### Subir archivos
```bash
git push
```
En el caso de tener commits ([[Github#Confirmación de cambios en el repositorio]])  pendientes

## Mostrar cambios del repositorio local y nube
### Estado del repositorio local
```bash
git status
```
Este muestra :
- Rama actual
- Los commit pendientes 
- Ficheros modificados
- Ficheros añadidos [[Github#Añadir fichero al repositorio]]
- Ficheros sin seguimiento
Puede usar el "." para definir la carpeta actual entera o una ruta que quieras
### Diferencia de archivos
```bash
git diff
```
Este muestra las diferencias de los archivos, líneas añadidas y eliminadas
Puede usar el "." para definir la carpeta actual entera o una ruta que quieras

### log and show
TODO

## Registrar clave ssh en Github
1. Entramos en los ajustes de usuario
2. Zona izquierda "**SSH and GPG keys**"
3. Pulsamos "**New SSH key**"
4. pegamos la clave publica (.pub)
5. Pulsamos Add SSH key
## Generar token en Github
