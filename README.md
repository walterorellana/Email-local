# Walter Antonio Orellana Beltetón   1890-20-4566
# Email-local
Configurar correo local y enviar un mensaje de prueba. (webmail, procesos, redes --> subdominio = ct-procesos.digicom.com.gt, prueba@ct-procesos.digicom.com.gt)

# CONFIGUARCION DE GMAIL LOCAL POR MEDIO DE POSTFIX  

## Paso 1: Instalación de Postfix 
Para comenzar con la configuración de un servidor de correo, es necesario instalar Postfix, que es un agente de transferencia de correo (MTA). Postfix permite el envío y la recepción de correos electrónicos entre usuarios locales o externos, funcionando como la base del sistema de correo electrónico en servidores Linux.
### Comando para instalar Postfix en Debian/Ubuntu:
  - sudo apt update
  + sudo apt install postfix
### Verificar que Postfix esté funcionando
- sudo systemctl status postfix

NOTA: en este caso ya se encuentra instalado el postfix.
## Paso 2: Configuracion de basica de postfix 
Una vez instalado Postfix, se debe realizar una configuración básica para que el servidor funcione correctamente dentro de la red o dominio deseado.

### General options 
En este paso se modificarán las opciones **"What domain to use in outbound mail"**, en la cual se colocará **"Use hostname"**, y **"What domains to receive mail for"**, en la cual se colocará **"Local machine"**.
![image](https://github.com/user-attachments/assets/130d3c25-1b5f-443a-9c1a-fec8175e49e5)

### Virtual Domains 
En este paso se configurará el dominio, el cual se colocará de la siguiente manera:

![image](https://github.com/user-attachments/assets/6e1496fb-e76e-4daf-9f75-2dd20fbf3904)

Y se creará el **"Map"**.

![image](https://github.com/user-attachments/assets/461c9f7b-7c42-4887-95fc-8d2468ddf52f)

Nota: Esta configuración aplica para el usuario, pero se puede modificar según se desee. En el archivo Map, se ha cambiado estudiante17 por el nombre de usuario de su preferencia.

## Paso 3: Pruebas de envío de correo
Una vez que la configuración esté correctamente realizada, se puede proceder a hacer una prueba de envío de correo.
Primero, es necesario validar que el comando mail esté disponible en el sistema. En caso de que no lo esté, se puede utilizar como alternativa el comando sendmail para realizar el envío.
El correo se puede enviar desde la "Command Shell" o la "Terminal", utilizando uno de los siguientes métodos:

![image](https://github.com/user-attachments/assets/f46f7507-ec6e-4c0b-ab50-ab335476f169)

Nota: Para fines de prueba, se utilizó Command Shell con el siguiente comando: **"echo -e "Subject: Aviso Importante\n\nHola,\n\nEste es un mensaje de prueba enviado desde sendmail.\nPor favor, no responder.\n\nSaludos,\nEquipo de Soporte" | sendmail prueba@ct-procesos.digicom.com.gt"**

## Paso 4: Validar el envío del correo
Para validar el envío, se debe ingresar a la opción **"Read User Mail"** . Este servicio debería venir activado por defecto en Webmin. Después de entrar al apartado, se debe seleccionar el usuario vinculado al correo, y se debería visualizar una interfaz similar a la siguiente: 
![image](https://github.com/user-attachments/assets/b9e2ad05-02db-4b35-a9b3-19e0bcea9652)}

 Al ingresar al usuario, se visualizará la bandeja de entrada con los mensajes recibidos.

![image](https://github.com/user-attachments/assets/874e9992-46cd-4b90-b360-8e41d5ea67cd)

Luego, se puede visualizar el contenido del correo dando clic sobre algún mensaje, donde se mostrará el cuerpo completo del correo.

![image](https://github.com/user-attachments/assets/8241b9da-cd8b-4115-8c2f-38e1bd4aaea1)


