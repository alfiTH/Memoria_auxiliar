# Sistema Operativo
```
lsb_release -a
```

# SSH
## Crear clave SSH
Para crear una clave SSH en Ubuntu en una terminal ejecutaremos el siguiente comando 
```bash
ssh-keygen
```
Preguntará por:
- Ubicación del archivo: pulsamos entre si lo queremos en la capeta por defecto ``~/.ssh/id_rsa``
- Contraseña para la clave privada
- Confirmación de contraseña
Ya habrá generado una clave publica(.pub) la cual es la que se comparte y la privada que debe ser solo para ti y esta protegida por la contraseña antes mencionada.
## Compartir clave SSH con dispositivo externo
Para compartir tu clave publica a otros dispositivos podrás:
- copiar la clave publica (.pub) en el otro dispositivo de forma manual a su carpeta ``~/.ssh/authorized_keys``
- Mediante el comando ``ssh-copy-id [usuario@ip]`` que hara lo anteriormente nombrado de forma automática, podrás seleccionar cual clave publica subir con el parámetro ``-i [fichero]``
## Tunelización con ssh

## Realizar ssh

## Restricción de ssh por claves Publicas/privadas
#TODO