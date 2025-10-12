### As this is the nodejs application(microservice) the explanation is same like catalogue, so we are just mentioning the commands rather than explaining the complete dockefile 


# Commands to execute the docker image

docker build -t cart:v1 .

docker run -d --name cart --network roboshop cart:v1

docker ps 

docker exec -it cart:v1 bash

curl localhost:8080/health

this shows app:OK and mongo:true   >>>> which confirms that cart is running fine

exit



# docker build -t nagashankar1992332/cart:v1 .

