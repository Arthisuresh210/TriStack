## **TriStack**

### **Deployment of a Three-Tier Web Application on Kubernetes Cluster on EC2 with Jenkins, SonarQube, Helm, Prometheus, and Grafana**

**TriStack** is a cloud-native project that demonstrates the deployment of a **three-tier web application**—comprising a **frontend, backend, and database**—on a **Kubernetes cluster hosted on AWS EC2** instances. The project focuses on **modular architecture, automated CI/CD**, and **observability at the infrastructure level**.

### **Technology Stack and Deployment Workflow**

* The application was containerized using Docker and then deployed to a Kubernetes cluster.
* Each component—frontend, backend, and database—runs in its own pod with corresponding services for internal communication.
* The Kubernetes cluster was created manually on EC2, allowing flexibility in infrastructure management.

### **CI/CD Integration with Jenkins and SonarQube**

To automate development workflows, a Jenkins pipeline was integrated. The pipeline performs:

* Cloning source code from GitHub/GitLab
* Static code analysis using **SonarQube**
* Building and tagging Docker images
* Pushing images to a container registry (Docker Hub or ECR)
* Deploying to the Kubernetes cluster using `kubectl`

This ensures continuous integration and continuous delivery with quality checks included.

### **Monitoring with Prometheus and Grafana (via Helm)**

For observability, **Prometheus** and **Grafana** were deployed using **Helm charts**. These tools were configured for **Kubernetes cluster-level monitoring only**.

* Metrics collected include **node health**, **pod status**, **CPU/memory usage**, and **resource consumption trends**.
* No application-level scraping was configured.
* Load was generated using a **Kubernetes Job YAML** to simulate traffic and test system behavior under pressure.

Grafana dashboards were set up to visualize key cluster metrics, helping track resource usage and infrastructure health.

### **Final Outcome**

This setup delivers a **production-like environment** with the following features:

* **Scalability** through Kubernetes
* **Basic observability** using Helm-based Prometheus and Grafana for infrastructure metrics
* **Automated deployment** using Jenkins and SonarQube
* **Load testing capabilities** through Kubernetes Job resources
![Screenshot 2025-06-10 222512](https://github.com/user-attachments/assets/44a0a88f-5a7a-4e20-b4a2-66265fa82a89)


The project demonstrates how to combine core DevOps tools and practices for managing and observing a distributed application on cloud infrastructure.

