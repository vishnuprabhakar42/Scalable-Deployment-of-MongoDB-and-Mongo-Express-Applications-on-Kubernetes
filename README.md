# Scalable-Deployment-of-MongoDB-and-Mongo-Express-Applications-on-Kubernetes

This project focuses on the scalable deployment of MongoDB and Mongo Express applications using Kubernetes. By utilizing Kubernetes, a powerful container orchestration platform, we can easily manage and deploy these essential components for database management and administration.

## Contents

- [Introduction](#introduction)
- [Deployment Files](#deployment-files)
- [Instructions](#instructions)
- [Prerequisites](#prerequisites)
- [Deployment](#deployment)
- [Accessing MongoDB and Mongo Express](#accessing-mongodb-and-mongo-express)
- [Video Demo](#video-demo)
- [Contributing](#contributing)
- [License](#license)

## Introduction

In this project, we aim to provide a scalable and efficient solution for deploying MongoDB, a popular NoSQL database, and Mongo Express, a web-based administration tool for MongoDB, using Kubernetes. By leveraging the power of Kubernetes, we ensure seamless management, scalability, and high availability of these applications.

## Deployment Files

This repository contains the following deployment files:

- `mongo.yaml`: This file defines the Kubernetes Deployment for MongoDB. It specifies the image, ports, and environment variables required for initialization, including the secret for the root username and password.

- `mongodb-service.yaml`: This file creates a Kubernetes Service for MongoDB, enabling connectivity and load balancing to the MongoDB pods.

- `mongo-configmap.yaml`: This file creates a Kubernetes ConfigMap that stores the MongoDB database URL to be used by Mongo Express.

- `mongodb-secret.yaml`: This file creates a Kubernetes Secret to securely store the MongoDB root username and password.

- `mongo-express.yaml`: This file defines the Kubernetes Deployment for Mongo Express. It specifies the image, ports, and environment variables required for configuration, including the secret for the MongoDB root credentials and the ConfigMap for the database URL.

- `mongo-express-service.yaml`: This file creates a Kubernetes Service for Mongo Express, allowing external access to the Mongo Express web interface.

## Instructions

Follow the instructions below to deploy MongoDB and Mongo Express on Kubernetes:

### Prerequisites

Before proceeding with the deployment, ensure that you have the following prerequisites:

1. Kubernetes cluster is set up and running.

2. `kubectl` command-line tool is installed and configured to access your Kubernetes cluster.

### Deployment

1. Clone this repository to your local machine:

   ```shell
   git clone <repository-url>
   ```

2. Navigate to the cloned repository:

   ```shell
   cd <repository-directory>
   ```

3. Deploy MongoDB using the following command:

   ```shell
   kubectl apply -f mongo.yaml
   ```

4. Create the MongoDB Service:

   ```shell
   kubectl apply -f mongodb-service.yaml
   ```

5. Create the MongoDB ConfigMap:

   ```shell
   kubectl apply -f mongo-configmap.yaml
   ```

6. Create the MongoDB Secret:

   ```shell
   kubectl apply -f mongodb-secret.yaml
   ```

7. Deploy Mongo Express:

   ```shell
   kubectl apply -f mongo-express.yaml
   ```

8. Create the Mongo Express Service:

   ```shell
   kubectl apply -f mongo-express-service.yaml
   ```

## Accessing MongoDB and Mongo Express

Once the deployment is completed, you can access MongoDB and Mongo Express using the following information:

- MongoDB:

  - Service Name: `mongodb-service`
  - Port: `27017`

- Mongo Express:

  - Service Name: `mongo-express-service`
  - Port: `8081`

Ensure that you have the necessary network access to reach the Kubernetes cluster and access the services.

## Video Demo

For a visual demonstration of the deployment process, you can watch the [video demo](https://drive.google.com/file/d/1IhZAp7Lm3HvOdeISzeCAGRtPzuOvSBBK/view?usp=sharing) of this project.

## Contributing

Contributions are welcome! If you have any improvements or suggestions for this project, please feel free to submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
