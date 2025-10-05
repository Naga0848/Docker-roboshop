Ikkada mysql lo load chelasina data shipping msvc lo .sql file names tho unnai
basic ga data loading task ni DB team vallu handle chestharu and they dont give any root user to application team or 
DevOps team

But, here we are only loading the data directly in mysql ratherthan running from catalogue msvc, that is the reason why 
we are keeping all the .sql files in mysql/db folder and it loads before the container starts as we have copied it in the 
path /docker-entrypoint-initdb.d in Docker

# Commands

docker build -t mysql:v1 .

docker run -d --name mysql --network roboshop mysql:v1

docker ps

docker exec -it <container-id> bash 

exit

