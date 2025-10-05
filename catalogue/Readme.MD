ikkada line no-7 lo unna mongodb:27017 is the host. manam separate ga route53 ni em use cheyatledu. name of the container is the name of the host i.e., mongdb
 we already know that mongodb is available on 27017 port no
 line 5 installs dependencies
line 3 and 4 makes sure that we are copying all the code into the /opt/server folder 
 And finally, line no-8, manam execute cheyalsina code server.js


# Download the https://roboshop-artifacts.s3.amazonaws.com/catalogue-v3.zip  into our laptop and extract it. And copy the make package.json and server.json so that they are with our dockerfile
======================================================================================
# Below are the steps in understanding the CMD instruction step-by-step

CMD ["node", "server.js"]
is the default command that gets executed when a container is started from the image you're building.

🧠 What CMD Does
It tells Docker: “When someone runs a container from this image, execute node server.js.”

This starts your Node.js application by running the server.js file.


=============

the word node refers to the Node.js runtime—a JavaScript engine that lets you run JavaScript code outside of a browser, typically on servers.

🧠 What node Does Here
It launches the Node.js interpreter.

It runs the file server.js, which is presumably your backend application or server logic.

So when the container starts, it’s essentially doing:

node server.js
inside the container, which kicks off your app

============

Your Dockerfile starts with:


FROM node:20
This means your image is based on the official Node.js version 20 image, which already includes the node command. So you don’t need to install Node.js manually—it’s baked into the image.

If you want, I can help you verify that server.js is set up correctly to start your app, or walk through how to expose ports and connect it to MongoDB. Just say the word.

============================================================


# Commands to execute the docker image

docker build -t catalogue:v1 .

docker run -d --name catalogue catalogue:v1

docker ps

docker exec -it catalogue bash

curl http://catalogue:8080/health   >>> to see whther catalogue is properly istalled or not

exit

docker have 2 types of network, bridge and host. host means directly host network. bridge means docker creates seperate network interface and assign the IP address to containers..

docker default bridge network can't communicate between containers, docker always suggest to create custom brige network



# Commands to create a new network and disconnect and connect to the new network

docker network create roboshop  >>>  command to create a new network

docker network disconnect bridge catalogue

docker network disconnect bridge mongodb

docker network ls >>> shows our networks


docker network connect roboshop catalogue

docker network connect roboshop catalogue

docker exec -it catalogue bash
curl localhost:8080/health
this shows app:OK and mongo:true   >>>> which confirms that catalogue is running fine





