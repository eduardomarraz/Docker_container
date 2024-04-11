## English:

# Docker_container

To begin with, you need to create an EC2 instance on AWS with ports 80, 8080, and 3036 open, as well as SSH connectivity.

## Steps to run Docker:

1. Install Docker
2. Install docker-compose
3. Create a topic on AWS "Simple Notification Service" (SNS)
4. Go to the `html` folder and edit the `submit.php` file. Replace the line `$snsTopicArn = 'arn:aws:sns:us-east-1:XXXXX:test';` with the ARN generated when creating the topic.
5. Create a subscription for that topic
6. Assign a Role to the EC2 instance on AWS
   - Go to the EC2 console, select "Actions" -> "Security" -> "Add Role"
   - Choose the “LabInstanceProfile” Role
7. Then, go to the IAM service, search for this Role, and add the “SNSFullAccess” policy.
8. Finally, run: `sudo docker-compose up`

## Usage:

- Paste the URL of the EC2 instance in the browser to access the form that sends messages to the subscribed email of the topic.

- Paste the URL of the EC2 instance followed by `:8080` in the browser to access the phpMyAdmin login page. The credentials are:
  - Username: root
  - Password: example_password

---

## Español:

# Docker_container

Para comenzar, debes crear una EC2 en AWS con los puertos 80, 8080 y 3036 abiertos, así como conexión SSH.

## Pasos para ejecutar Docker:

1. Instalar Docker
2. Instalar docker-compose
3. Crear un tema en AWS "Simple Notification Service" (SNS)
4. Ir a la carpeta `html` y editar el archivo `submit.php`. Cambiar la línea `$snsTopicArn = 'arn:aws:sns:us-east-1:XXXXX:test';` por el ARN generado al crear el tema.
5. Crear una suscripción para ese tema
6. Asignar un Rol a la EC2 en AWS
   - Ir a la consola de EC2, seleccionar "Acciones" -> "Seguridad" -> "Añadir Rol"
   - Elegir el Rol “LabInstanceProfile”
7. Luego, dirigirse al servicio IAM, buscar este Rol y añadir la política “SNSFullAccess”
8. Finalmente, ejecutar: `sudo docker-compose up`

## Uso:

- Pegar la URL de la EC2 en el navegador para acceder al formulario que envía mensajes al correo electrónico suscrito del tema.

- Pegar la URL de la EC2 seguido de `:8080` en el navegador para acceder a la página de inicio de sesión de phpMyAdmin. Los credenciales son:
  - Usuario: root
  - Contraseña: example_password
