# Requisitos
- Tener docker instalado

# Eliminar todas las imagenes
docker rmi -f $(docker images -a -q)

# Eliminar todos los contenedores
docker rm $(docker ps -a -q)

# Iniciar el proyecto
    - docker-compose build
    - docker-compose up

Puertos habilitados para los contenedores:

    - 5000 -> Este contenedor tiene la interfaz web

    - 5001 -> El unico objetivo del contenedor que se encuentra en este puerto es responder las solicitudes que le envia la app de la web.


# Correr test

- Para correr los test el proyecto debe de estar corriendo el proyecto

docker-compose -f docker-compose.yml exec -T api pytest test/test_api.py -s
![](images/test_api.PNG)

# El gestor de depedencias que se usa es pip el cual es el encargado de instalar todos los paquetes necesarios para cada proyecto

# Verificador de codigo se encuentra en la carpeta .vscode en settings.json , se usa flake8.