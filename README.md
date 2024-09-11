# Docker Node/Express Repository

This repository is intended for practicing Docker basics. It includes a simple Node.js application running with Docker.

The project contains a basic Express.js application that responds with "Hi there :D" when accessed. The application is Dockerized using a Dockerfile.

## Files

- `index.js`: A simple Node.js application using Express.js.
- `Dockerfile`: Contains the instructions to build the Docker image for the Node.js application.

## Getting Started

To get started with this project, follow these steps:

### Prerequisites

Ensure you have Docker installed on your machine. You can download Docker from the [official website](https://www.docker.com/products/docker-desktop).

### Build the Docker Image

Navigate to the project directory in your terminal and build the Docker image using the following command:

```bash
docker build -t node-app-image .
```

### Run the Docker Container

After building the image, you can run the Docker container with:

Bash (currently not working)

```bash
docker run -v $PWD:/app:ro -v /app/node_modules --env-file ./.env -d -p 3000:4000 --name node-app node-app-image
```

Powershell (works)

```shell
docker run -v ${pwd}:/app:ro -v /app/node_modules --env-file ./.env -d -p 3000:4000 --name node-app node-app-image
```

This command maps port 3000 of your local machine to port 3000 in the Docker container.

### Access the Application

Open your web browser and go to `http://localhost:3000`. You should see a message saying "Hi there :D".

### To delete the container and volume

Enter the following command in the Powershell

```shell
docker rm node-app -fv
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
