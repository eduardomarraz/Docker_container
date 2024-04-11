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
