# Docker-roboshop

# As we are not filling any data into the Redis we can directly run the redis container on our Docker host

# Command >>>> docker run -d --name redis --network roboshop redis:7
    indicates that redis is running on roboshop network with the name redis

# As we are creating the Rabbitmq directly via docker compose and we are mentioning the env variables as well in the docker compose file

