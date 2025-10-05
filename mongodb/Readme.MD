Ikkada mongdb lo load chelasina data catalogue msvc lo master-data.js ane filename tho undi
basic ga data loading task ni DB team vallu handle chestharu and they dont give any root user to application team or DevOps team

But, here we are only loading the data directly in mongodb ratherthan running from catalogue msvc, that is the reason why we are keeping master-data.js file in mongodb folder and it loads befor the container starts as we have copied it in the path /docker-entrypoint-initdb.d in Docker

 line no 3 in dockerfile indicates that all the .js files in mongodb folder are being copied to /docker-entrypoint-initdb.d and Docker executes them first as the init script before starting the container.

actually, its master-data.js which is part of catalogue msvc, but we are running it via it directly via mongodb as it will be present in mongodb only when we are using application.

#master-data.js has catagories related data

# Commands to execute after finishing the dockerfile creation

 docker build -t mongodb:v1 .

 docker run -d --name mongodb mongodb:v1

 As we are not exposing the mongodb, we are not using -p command 

docker exec -t mongodb <container-id> bash  >>>  to loginto the container in execute mode and see the catagories related data

exit

