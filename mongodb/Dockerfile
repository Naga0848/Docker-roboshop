FROM mongo:7.0

COPY *.js /docker-entrypoint-initdb.d

# line no 3 indicates that all the .js files in mongodb folder are being copied to /docker-entrypoint-initdb.d and Docker executes them first as the init script before starting the container.

#actually, its master-data.js which is part of catalogue msvc, but we are running it via it directly via mongodb as it will be present in mongodb only when we are using application.

#master-data.js has catagories related data

# Commands to execute after finishing the dockerfile creation

# docker build -t mongodb:v1 .

# docker run -d --name mongodb mongodb:v1

# As we are not exposing the mongodb, we are not using -p command 

# docker exec -t mongodb <container-id>    ---- to loginto the container in execute mode and see the catagories related data

