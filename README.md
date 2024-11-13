To-Do Application

This project demonstrates how to containerize a simple To-Do application using Docker deploy it using Docker Compose. The application consists of two containers:
1. A node.js based To-Do app.
2. A MySQL databaseto store the to-do items.

#Features
- Multi-Container Architecture: The app and MySQL are deployed in separate containers.
- Docker Networking: Containers are connected through a custom Docker network for secure communication.
- Persistent Storage: MySQL data is stored persistently using Docker Volumes.
- Environment Variables: Configuration of MySQL settings using environment variables in the Docker container.

# Requirements
- Docker: To build and run the containers.
- Docker Compose: To define and run multi-container applications.

# Setup & Installation

 Step 1: Clone the Repository
 ```
 git clone <github url>
 ```

 Step 2: Build and Run the Application

1. **Build and start the containers** with Docker Compose:

```
docker-compose up --build
```

2. This command will:
   - Build the Docker images for the To-Do app and MySQL.
   - Start both containers, linking them together via a custom Docker network.

### Step 3: Access the Application

Once the containers are up and running, you can access the To-Do app at:

```
http://127.0.0.1:3000
```

### Step 4: Stop the Containers

To stop the containers, run:

```bash
docker-compose down
```

This will stop the running containers and remove them.

## Project Structure

```
├── docker-compose.yml   # Defines services (To-Do app, MySQL) and networking
├── Dockerfile           # Dockerfile for the To-Do app (Node.js)
├── app/                 # Source code for the To-Do application
├── mysql-data/          # Docker volume for persistent MySQL data
├── README.md            # Project documentation
└── package.json         # Node.js dependencies
```

## Environment Variables
The following environment variables are used to configure the MySQL container:

- `MYSQL_ROOT_PASSWORD`: Password for the MySQL root user.
- `MYSQL_DATABASE`: Name of the database to create (default: `todos`).
- `MYSQL_USER`: MySQL user (root by default).
- `MYSQL_PASSWORD`: Password for the MySQL user (default: `secret`).

These environment variables are set in the `docker-compose.yml` file for the MySQL service.

## Learning Outcomes

- **MySQL Containerization**: Configured a MySQL database container with secure password management and persistent data storage.
- **Docker Networking**: Set up a custom Docker network to enable secure communication between the app and the database containers.
- **Multi-Container Setup**: Leveraged Docker Compose to efficiently define and deploy a multi-container application.

## License
This project is open-source and available under the [MIT License](LICENSE).

