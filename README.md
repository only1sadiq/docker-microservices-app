# Docker Microservices Deployment

This project demonstrates the infrastructure setup for a containerized **Node.js** application with a persistent **MongoDB** database layer. 

The goal was to move away from fragile local setups and create a **reproducible environment** where the application, database, and administration tools communicate seamlessly using a custom Docker Bridge Network.

## Architecture

The setup consists of three containers running on a user-defined isolated network:

1.  **MongoDB:** Handles persistent data storage (stateful).
2.  **Mongo-Express:** A lightweight web-based interface for database administration.
3.  **Node.js App:** The backend service that interfaces with the database via internal DNS.

##  How to Run

I have included a bash script to automate the provisioning of the network and containers so you don't have to type the commands manually.

### Prerequisites
* Docker Desktop installed and running.

### Quick Start
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/only1sadiq/docker-microservices-app.git](https://github.com/only1sadiq/docker-microservices-app.git)
    cd docker-microservices-app
    ```

2.  **Run the automation script:**
    ```bash
    sh start_app.sh
    ```
    *This script checks for the network, creates it if missing, and spins up the database and UI containers with the correct environment variables.*

3.  **Access the services:**
    * **Mongo Express UI:** [http://localhost:8081](http://localhost:8081)
    * **Node Application:** [http://localhost:3000](http://localhost:3000)

## Tech Stack
* **Docker & Docker Network**
* **Bash Scripting** (Infrastructure Automation)
* **MongoDB** (Database)
* **Node.js** (Backend)


