# TriStack
### **Deployment of a Three-Tier Web Application with Docker Compose, Kubernetes, Jenkins, SonarQube, Grafana, and Prometheus on EC2**  

This project focuses on deploying a **three-tier web application** on an **AWS EC2 instance** using **Docker Compose** and later migrating to **Kubernetes**. The architecture consists of a **frontend**, a **backend**, and a **database**, ensuring modularity, scalability, and observability.  

### **Technology Stack and Workflow**  
Initially, **Docker Compose** is used to containerize and manage the multi-container application. The **backend** processes user requests and interacts with the **database**, while the **frontend** provides the user interface. Once the application runs successfully in Docker, it is migrated to **Kubernetes**, where each component runs as a separate pod. **Kubernetes Services** manage communication.

### **CI/CD Integration with Jenkins and SonarQube**  
To automate application deployment, **Jenkins** is introduced for continuous integration and delivery (CI/CD). It pulls the latest code from the repository, builds Docker images, and deploys them to **Kubernetes**. **SonarQube** is integrated into the Jenkins pipeline for **static code analysis**, ensuring security, code quality, and maintainability.  

The Jenkins pipeline automates:  
1. **Code fetching from GitHub/GitLab**  
2. **Static code analysis using SonarQube**  
3. **Building and pushing Docker images to a container registry (ECR/Docker Hub)**  
4. **Deploying updated images to Kubernetes**  

### **Monitoring with Prometheus and Grafana**  
To enhance **observability**, **Prometheus** is deployed to collect and store application and infrastructure metrics. The backend API, database, and Kubernetes nodes expose metrics, which Prometheus scrapes periodically.  

**Grafana** is then used to visualize these metrics with custom dashboards, providing insights into:  
- **Application health and response times**  
- **Resource utilization (CPU, memory, disk I/O)**  
- **Database performance and queries**  
- **Kubernetes cluster metrics (pod status, node usage, network traffic)**  

### **Final Outcome**  
This setup results in a **scalable, automated, and observable** cloud-native deployment. **Docker and Kubernetes** ensure portability and orchestration, **Jenkins and SonarQube** automate CI/CD with quality checks, and **Prometheus and Grafana** provide real-time monitoring and alerting, making the system highly reliable and efficient.
