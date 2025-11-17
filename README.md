# Docker-roboshop

# All these images are optimized and these images have less size

# As we are not filling any data into the Redis we can directly run the redis container on our Docker host

# Command >>>> docker run -d --name redis --network roboshop redis:7
    indicates that redis is running on roboshop network with the name redis

# As we are creating the Rabbitmq directly via docker compose and we are mentioning the env variables as well in the docker compose file


 # My Docker Credentials
 username - nagashankar1992332

 login to the docker and run docker compose command

 ==========================================

# /var/lib/docker ----> Docker Home directory and all the images that we built are stored here and we need to increase the size of this location when we are creating docker using terrform

## Understanding Roboshop Application Service specific Dockerfiles 

#### MONGODB

    Ikkada mongdb lo load chelasina data catalogue msvc lo master-data.js ane filename tho undi basic ga data loading task ni DB team vallu handle chestharu and they dont give any root user to application team or DevOps team

    But, here we are only loading the data directly in mongodb ratherthan running from catalogue msvc, that is the reason why we are keeping master-data.js file in mongodb folder and it loads befor the container starts as we have copied it in the path /docker-entrypoint-initdb.d in Docker

    line no 3 in dockerfile indicates that all the .js files in mongodb folder are being copied to /docker-entrypoint-initdb.d and Docker executes them first as the init script before starting the container.

    actually, its master-data.js which is part of catalogue msvc, but we are running it directly via mongodb as it will be present in mongodb only when we are using application.

    #master-data.js has catagories related data

    ## Commands to execute after finishing the dockerfile creation

        docker build -t mongodb:v1 .

        docker run -d --name mongodb mongodb:v1

        As we are not exposing the mongodb, we are not using -p command

        docker exec -t mongodb bash >>> to loginto the container in execute mode and see the catagories related data

        exit

#### CATALOGUE

    Understanding the docker image step by step

    ikkada line no-27 lo unna mongodb:27017 is the host. manam separate ga route53 ni em use cheyatledu. name of the container is the name of the host i.e., mongdb
    we already know that mongodb is available on 27017 port no
    RUN npm install installs dependencies
    COPY command makes sure that we are copying all the code into the /opt/server folder 
    And finally, line no-8, manam execute cheyalsina code server.js


    Download the https://roboshop-artifacts.s3.amazonaws.com/catalogue-v3.zip  into our laptop and extract it. And copy the make package.json and server.json so that they are with our dockerfile

    Below are the steps in understanding the CMD instruction step-by-step

    