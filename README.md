# 🚀 Insured Assurance – CI/CD Pipeline

> **DevOps Foundations Project**  
> Automated build, test, and deployment of a Java web application using **GitHub Actions** for Continuous Integration (CI) and **Jenkins** for Continuous Deployment (CD) to **Apache Tomcat 9** hosted on **AWS EC2**.

![Java](https://img.shields.io/badge/Java-17-orange)
![Maven](https://img.shields.io/badge/Maven-3.9-blue)
![Tomcat](https://img.shields.io/badge/Tomcat-9.0.85-yellow)
![AWS](https://img.shields.io/badge/AWS-EC2-green)
![CI](https://img.shields.io/badge/GitHub_Actions-CI-success)
![CD](https://img.shields.io/badge/Jenkins-CD-informational)

---

# 📖 Project Overview

**Insured Assurance**, a US-based insurance platform, is designed to demonstrate a real-world DevOps CI/CD pipeline.

This project automates software delivery using:

- GitHub Actions for Continuous Integration
- Jenkins for Continuous Deployment
- Apache Tomcat for application hosting
- AWS EC2 for infrastructure

Every push to the `main` branch automatically triggers build, test, and deployment pipelines.

---

# 🌐 Live Application

**Application URL**

```
http://34.234.67.210:8888/insured-assurance-1.0/hello
```

### Sample Output

```
Insured Assurance - Hello from Jenkins!
```

---

# 🏗️ CI/CD Architecture

```text
Developer
   │
   ▼
GitHub Repository
   │
   ▼
GitHub Actions (CI)
 ├── Checkout Code
 ├── Setup Java 17
 ├── Maven Build & Test
 ├── Package WAR File
 └── Trigger Jenkins Job
   │
   ▼
Jenkins (CD)
 ├── Receive Trigger
 ├── SCP WAR to EC2
 ├── SSH into EC2
 └── Restart Tomcat
   │
   ▼
AWS EC2 Instance
   │
   ▼
Apache Tomcat 9
   │
   ▼
Live Application
```

---

# 🛠️ Tech Stack

| Layer | Technology |
|------|------------|
| Source Control | GitHub |
| CI Tool | GitHub Actions |
| CD Tool | Jenkins |
| Build Tool | Maven 3.9 |
| Language | Java 17 |
| App Server | Apache Tomcat 9 |
| Infra | AWS EC2 |

---

# 📂 Repository Structure

```text
insured-assurance/
│
├── .github/workflows/
│   └── ci.yml
│
├── screenshots/
│   ├── Screenshot 2026-05-24 024618.png
│   ├── Screenshot 2026-05-24 024632.png
│   ├── Screenshot 2026-05-24 024702.png
│   ├── Screenshot 2026-05-24 024715.png
│   ├── Screenshot 2026-05-24 024739.png
│   ├── Screenshot 2026-05-24 024800.png
│   └── Screenshot 2026-05-24 024819.png
│
├── src/
├── pom.xml
└── README.md
```

---

# ⚙️ AWS EC2 Setup

```bash
sudo yum update -y
sudo yum install -y java-17-amazon-corretto-devel

sudo alternatives --set java \
/usr/lib/jvm/java-17-amazon-corretto.x86_64/bin/java

java -version
```

### Tomcat Permissions Fix

```bash
sudo chown -R ec2-user:ec2-user /opt/tomcat9
sudo chmod +x /opt/tomcat9/bin/*.sh
sudo systemctl restart tomcat
```

---

# 🔧 Key Issues Resolved

- Java not found → Installed Corretto 17
- Tomcat 203/EXEC error → Fixed permissions
- WAR deployment failure → Restarted Tomcat
- Port mismatch (8080/8888) → Configured correctly
- SSH deployment issues → Fixed key-based auth

---

# 📸 Project Screenshots

All screenshots are stored in the `screenshots/` folder and demonstrate the full CI/CD workflow.




---

# 🎯 CI/CD Flow Summary

1. Code pushed to GitHub  
2. GitHub Actions runs CI pipeline  
3. Maven builds WAR file  
4. Jenkins triggered automatically  
5. WAR copied to EC2 via SCP  
6. Tomcat restarted  
7. Application goes live  

---

# 👨‍💻 Author

**Arshit Choubey**  
DevOps Engineer   

GitHub: https://github.com/arshitchobey18

---

# 📅 Project Timeline

Completed: May 2026

---

⭐ If you like this project, please consider giving it a star.
