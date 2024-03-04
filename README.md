# Microservice-based Message Queue with RabbitMQ

This project demonstrates a basic implementation of a microservice architecture using RabbitMQ as the message broker. It consists of two services: Product Service and Order Service, each communicating with each other via RabbitMQ.

## Overview

The application consists of the following components:

- **Product Service**: Responsible for managing products and processing orders. Exposes endpoints for creating products and purchasing products.
- **Order Service**: Handles order processing and creation. Receives order requests from the Product Service via RabbitMQ and creates orders accordingly.

## Requirements

To run the application locally, you need the following:

- Node.js and npm installed on your machine
- MongoDB instance running
- RabbitMQ server running on localhost

## Setup

1. Clone the repository:

    ```bash
    git clone https://github.com/coder-adnan/microservice-message-queue-rabbitmq.git
    ```

2. Install dependencies for both services:

    ```bash
    cd products
    npm install

    cd ../orders
    npm install
    ```

     cd ../authentication-service
    npm install
    ```

3. Set up environment variables:

    - Create a `.env` file in these `authentication` `product-service` and `order-service` directories.
    - Specify the MongoDB URI and RabbitMQ connection details in the `.env` files.

4. Start both services:

    ```bash
    # In product-service directory
    npm start

    # In order-service directory
    npm start
    ```

## Usage

Once both services are up and running, you can interact with them using their respective endpoints:

- **Product Service Endpoints**:
    - `POST /product/create`: Create a new product.
    - `POST /product/buy`: Purchase products by providing their IDs.

- **Order Service Endpoints**: (No direct endpoints, it listens for messages from Product Service)

## Architecture

The architecture follows a typical microservices pattern, with each service handling specific responsibilities and communicating via RabbitMQ message queues. RabbitMQ facilitates asynchronous communication and decouples the services, making the system more scalable and resilient.
