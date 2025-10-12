# The payment micro service is developed in Python language

# Understanding the CMD Command

CMD ["usgi", "--ini", "payments.ini"]

This line sets the default command that will be executed when a container built from this Docker image is run.

🔍 Components explained:
CMD: Dockerfile instruction that specifies what to run when the container starts.

["usgi", "--ini", "payments.ini"]: This is the JSON array syntax for the command. It avoids shell parsing issues and is preferred for clarity and reliability.

🧠 What the command does:
usgi: This is likely a command-line tool or executable included in the image. It could be a custom binary or script.

--ini payments.ini: This tells usgi to use the configuration file named payments.ini. The .ini format is commonly used for configuration settings.

==================================================

# Commands to run the image


docker build -t nagashankar1992332/payment:v1 .

===============================================================

Env variables for this payment service is writeen in the docker-compose.yaml rather that writing in the dockerfile
