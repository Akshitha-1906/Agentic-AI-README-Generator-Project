# Flask Hostname Greeter 🚀

## ⭐ Problem Statement
In distributed and containerized environments, understanding which specific instance or container is serving a request can be crucial for debugging, load balancing, and general service introspection. This project provides a simple yet effective demonstration of how a basic web application can dynamically report its hostname within a containerized setup, illustrating the use of environment variables for service identification.

## 📘 Overview
This project is a lightweight Flask web application that serves a "Hello, World!" greeting. Its unique feature is that it dynamically includes the hostname of the container in its greeting message. The application is fully containerized using Docker and can be easily orchestrated with Docker Compose, showcasing a basic yet complete deployment pipeline for a simple web service.

## 🔁 Workflow / How it Works
1.  **Build Phase** 🏗️: A `Dockerfile` specifies how to build the application's Docker image. It installs Python dependencies (`Flask`) and copies the `app.py` script.
2.  **Environment Configuration** ⚙️: The `Dockerfile` sets a default `HOSTNAME` environment variable. This is then overridden by `docker-compose.yml` which explicitly sets `HOSTNAME` to `web-service` for the Docker Compose setup.
3.  **Service Definition** 🐳: `docker-compose.yml` defines a single service, `web`, which is built from the `Dockerfile` in the current directory. It maps the container's port 80 to the host's port 80.
4.  **Application Execution** ▶️: When the container starts, `app.py` is executed. The Flask application starts on port 80.
5.  **Dynamic Greeting** 👋: Upon receiving a request, the Flask app retrieves the `HOSTNAME` environment variable and uses it to construct the "Hello from {hostname}" message.
6.  **Access** 🌐: Users can access the web application via their browser at `http://localhost`, which will display the dynamic greeting.

## 🛠 Tools & Tech Stack
*   **Python** 🐍: The core programming language for the web application.
*   **Flask** 🌐: A micro web framework for Python, used to build the web service.
*   **Docker** 🐳: Platform for developing, shipping, and running applications in containers.
*   **Docker Compose** 📦: Tool for defining and running multi-container Docker applications.

## ✅ Outputs / Result
The final output of this project is a running web service accessible on port `80` of the host machine. When accessed, it displays a simple "Hello from web-service" message, demonstrating successful containerization, environment variable injection, and basic web server functionality. This provides a foundational example for more complex containerized applications.