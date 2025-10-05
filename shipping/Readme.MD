Ikkada maven base image, which means shipping is based on Java application

line no 3 and 4 are for coping the source code and pom.xlm into our work directory (/opt/server)

line no-5 creates a folder called target which will contain our jar file with a version(shipping.1.0)

And lline no-6 is for moving that .jar file with version no into /opt/server folder by renaming it to shipping.jar

# Commands

docker build -t shipping:v1 .

docker run -d --name shipping --network roboshop shipping:v1

docker exec -it <container-id> bash

exit