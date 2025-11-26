Docker Microservices Deployment
This project demonstrates the containerization of a Node.js application with a persistent database layer. It utilizes a custom Docker Bridge Network to ensure secure, isolated communication between the application, the database, and the administration UI.

Attribution: The application logic is based on a demo by Nana Janashia, adapted here to demonstrate infrastructure automation and network configuration.

Architecture
The setup consists of three containers running on a user-defined bridge network:

MongoDB: Persistent data storage.

Mongo-Express: Web-based database administration interface.

Node.js App: The backend service communicating with the database.

How to Run
I have included a bash script to automate the provisioning of the network and containers.

Prerequisites:

Docker Desktop installed and running.

Steps:

Clone the repository:

Bash

git clone https://github.com/your-username/docker-microservices-app.git
Navigate to the directory:

Bash

cd docker-microservices-app
Run the automation script:

Bash

sh start_app.sh
Access the interfaces:

Mongo Express UI: http://localhost:8081

Application: http://localhost:3000 (or whatever port the app uses)

Tech Stack
Docker & Docker Network

Bash Scripting (Automation)

MongoDB

Node.js

