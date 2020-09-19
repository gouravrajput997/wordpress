# wordpress
Wordpress with MySQL

Project structure:

.
├── docker-compose.yaml
└── README.txt


docker-compose.yaml

services:
  db:
    image: mysql:5.7
    ...
  wordpress:
    image: wordpress
    ports:
      - 8000:80
    restart: always
    ...

When deploying this setup, docker-compose maps the wordpress container port 80 to port 8000 of the host 
as specified in the compose file.

Deploy with docker-compose

$ docker-compose up -d

Check containers are running and the port mapping:

$ docker ps

Navigate to http://localhost:8000 in your web browser to access Wordpress.

page

Stop and remove the containers

$ docker-compose down

To remove all Git data, delete the named volumes by passing the -v parameter:

$ docker-compose down -v
