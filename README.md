# Docker_container
Lo primero sera crear una EC2 en AWS con los puertos 80, 8080 y 3036 abiertos y con conexión a SSH.

Pasos para ejecutar Docker:

1- Instalar Docker
2- Instalar docker-compose
3- Crear topico en AWS "simple notification service" (SNS)
4- Ir a la carpeta html y editar el archivo submit.php y cambiar la linea $snsTopicArn = 'arn:aws:sns:us-east-1:XXXXX:test'; y sustituir esa linea con el arn que se ha creado al realizar el topico.
5- Crear una suscripción de ese Topico
6- Añadir un Rol a la EC2 en AWS
7- Vamos a la consola de la EC2, vamos a acciones -> seguridad -> Añadir Rol
8- Elegimos el Rol “LabInstanceProfile”
9- Luego vamos al servicio IAM y buscamos este Rol, y añadimos la politica “SNSFullAccess”
10- Finalmente ejecutamos: sudo docker-compose up

11- Pega la url de la EC2 en el navegador, y accederemos al formulario que envia mensajes a al email suscrito del topico.

12- Pega la url de la EC2 de nuevo asi -> url:8080
Asi nos saldra la pagina de login de phpMyAdmin y tendremos que ingresar el user: root y el password: example_password


