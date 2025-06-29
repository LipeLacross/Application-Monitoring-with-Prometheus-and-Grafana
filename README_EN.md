Here is your README fully translated and adapted to English, including the visual example block with improved image layout (note: the images are shown stacked at 60% width, which may not be ideal for side-by-side display—adjust width if you want them in a row):

## 🌐 [English Version of README](README_EN.md)

# Application Monitoring with Prometheus and Grafana

This repository contains practical examples and configurations for monitoring applications and servers using Prometheus and Grafana. It includes guides for installation, metrics collection, dashboard creation, and alert setup, based on the course by instructor Rodrigo Roma[1].

## 🔨 Project Features

- **Real-time monitoring** of web applications and servers.
- **Automatic metrics collection** (requests, logged-in users, response time).
- **Data visualization** using intuitive Grafana dashboards.
- **Alert configuration** in Prometheus.
- **Simple integration** between Node.js application, Prometheus, and Grafana using Docker Compose.

### 📸 Visual Example

<div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: space-around;">
  <img src="https://github.com/user-attachments/assets/9de4d1e1-ad0e-4802-8592-58b275dc1a1d" style="width: 60%; border-radius: 8px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);">
  <img src="https://github.com/user-attachments/assets/c7f2b411-2b74-444f-9405-b43bff7526ea" style="width: 60%; border-radius: 8px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);">
  <img src="https://github.com/user-attachments/assets/9dbccaef-ebab-4379-970c-b7140bd38f02" style="width: 60%; border-radius: 8px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);">
</div>

## ✔️ Technologies and Tools Used

- **Node.js:** JavaScript runtime platform.
- **Prometheus:** Monitoring and alerting system.
- **Grafana:** Metrics visualization and analytics platform.
- **Express:** Web framework for Node.js.
- **prom-client:** Library to expose Prometheus-compatible metrics.
- **Docker Compose:** Container orchestration for development and production environments.

## 📁 Project Structure

```
Application-Monitoring-with-Prometheus-and-Grafana/
|-- LICENSE
|-- README.md
|-- docker-compose.yml
|-- index.js
|-- package-lock.json
|-- package.json
|-- prometheus-data/
    |-- prometheus.yml
```

- **LICENSE:** Project license.
- **README.md:** Main documentation.
- **docker-compose.yml:** Configuration to run Prometheus and Grafana in Docker containers.
- **index.js:** Node.js application exposing custom metrics.
- **package-lock.json** and **package.json:** Project dependencies.
- **prometheus-data/prometheus.yml:** Prometheus configuration for metrics collection from the application and server[1].

## 🛠️ Getting Started

To run the project locally, follow these steps:

1. **Ensure Node.js is installed:**
   - [Node.js](https://nodejs.org/) is required. Check if you already have it installed with:

     ```bash
     node -v
     ```

   - If not, download and install the recommended version.

2. **Clone the repository:**
   - Copy the repository URL and run the following command in your terminal:

     ```bash
     git clone 
     ```

3. **Install Node.js dependencies:**
   - Navigate to the project folder and run:

     ```bash
     npm install
     ```

4. **Start the Node.js application (optional, for local testing):**
   - Run:

     ```bash
     node index.js
     ```
   - The application will be available at `http://localhost:3030` and metrics at `http://localhost:3030/metrics`.

5. **Start services with Docker Compose:**
   - Run the following command to start Prometheus and Grafana:

     ```bash
     docker-compose up -d
     ```
   - **Prometheus:** `http://localhost:9090`
   - **Grafana:** `http://localhost:3000`

## 🌐 Deployment

To deploy the project in a production environment:

1. **Ensure Docker and Docker Compose are installed** on the target server.
2. **Copy all project files** to the server.
3. **Start the services** with the command:

   ```bash
   docker-compose up -d
   ```
4. **Configure domains and/or firewalls** as needed for external access.
5. **Secure Grafana access** by changing the default password and restricting access if necessary.

## 📝 Code Documentation

### **index.js**

Node.js application that exposes custom metrics for Prometheus:

- **express:** Creates the web server.
- **prom-client:** Generates Prometheus-compatible metrics.
- **Exposed metrics:**
  - `aula_requests_total`: Request counter, with status code as a label.
  - `aula_usuarios_logados_total`: Gauge for the number of logged-in users.
  - `aula_request_duration_seconds`: Histogram for API response time.
- **Endpoints:**
  - `/`: Returns "Hello World!".
  - `/zera-usuarios-logados`: Resets the logged-in users counter.
  - `/retorna-usuarios-logados`: Restores the logged-in users counter to its normal value.
  - `/metrics`: Exposes metrics for Prometheus to collect.

**Note:** Replace `` with the actual repository URL when using this README.  
To add the English README, create the file `README_EN.md` with the above content.

This is your complete README in English, ready to use.

[1] https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/55317053/4caabe98-50e8-4975-b797-300f80153c4b/directory_listing.txt
