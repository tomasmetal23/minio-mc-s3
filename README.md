# Minio-Mc-S3


Este archivo YAML crea dos servicios: minio y mc. El servicio minio es el servidor de almacenamiento Minio S3, que se ejecuta en el puerto 9000 y utiliza las credenciales de acceso predefinidas minioadmin:minioadmin. Los datos y la configuración de Minio S3 se almacenan en los volúmenes locales ./data y ./config, respectivamente.

El servicio mc es el cliente de línea de comandos MC, que se utiliza para interactuar con el servidor de almacenamiento Minio S3. Este servicio depende del servicio minio y utiliza el comando mc config host add para agregar un host llamado myminio con la dirección http://minio:9000 y las credenciales minioadmin:minioadmin. Luego, utiliza los comandos mc mb y mc cp para crear un nuevo bucket llamado mybucket y copiar un archivo local a ese bucket.

Para utilizar este docker-compose, simplemente guarda el archivo YAML en un directorio y ejecuta el comando docker-compose up. Esto iniciará ambos servicios y creará el bucket y el archivo especificados.

## MC
El segundo servicio es minio/mc en tu archivo docker-compose.yml. Puedes crear buckets y cargar datos en ellos utilizando el comando mc dentro del contenedor de minio/mc. 

Recuerda que debes adaptar los valores de las variables de entorno MC_HOST, MC_PORT, MC_ACCESS_KEY y MC_SECRET_KEY a los valores que has establecido para el servicio de minio.
