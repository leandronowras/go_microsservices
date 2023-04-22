# go_microsservices

## Introduction
This project is a microservices architecture based project consisting of several services that provide different functionalities. Each service has its own Dockerfile, Go modules and application code. In addition, there are configuration files for the project and the Kubernetes deployment.
## Diagram
![Leandro's landscape - Diagram 1 (Latest)](https://user-images.githubusercontent.com/56269786/233810506-b48ad54a-768f-4a9f-b310-7a2545e5b5b5.png)

The full C4 diagram can be accessed here: https://s.icepanel.io/Rh89uQWRKrWsrC/xlDY 

---

## Microservices
- Authentication Service:
  - Contains a microservice responsible for handling user authentication. It has a go.mod file for managing dependencies, a cmd/api folder for running the service, a data folder for storing data models and a Dockerfile for building a Docker image.

- Broker Service:
  - Responsible for managing a message broker, such as RabbitMQ. It has a go.mod file for managing dependencies, a cmd/api folder for running the service, an event folder for handling events, and a Dockerfile for building a Docker image.

- Listener Service:
  - Responsible for listening to events emitted by the broker service. It has a go.mod file for managing dependencies, a event folder for handling events, a listener-service.dockerfile for building a Docker image, and a listenerApp folder for storing application code
  
- Logger Service:
  - Responsible for handling logging for the entire application. It has a go.mod file for managing dependencies, a cmd/api folder for running the service, a data folder for storing data models, a logger-service.dockerfile for building a Docker image, and a loggerServiceApp folder for storing application code.

- Mailer Service:
  - Responsible for handling email notifications for the application. It has a go.mod file for managing dependencies, a cmd/api folder for running the service, a templates folder for storing email templates, a mail-service.dockerfile for building a Docker image, and a mailerApp folder for storing application code.

---

## Configuration Files
- Makefile:
  - Contains a list of tasks for automating the build and deployment process. These tasks include building Docker images, starting and stopping the development environment, and deploying to Kubernetes.

- docker-compose-yml
  - Defines a set of Docker containers that make up the development environment. It includes containers for the database, message broker, and all microservices.

- k8s
  - Contains configuration files for deploying the microservices to Kubernetes. There are separate files for each microservice, as well as additional files for configuring the database and message broker.

- ingress.yml
  - Defines an ingress controller for the Kubernetes deployment, allowing external access to the web application.

- postgres.yml
  - Defines a Docker container for running a PostgreSQL database instance.

- db-data
  - Contains data files for setting up the database, including files for configuring the PostgreSQL and RabbitMQ databases.

