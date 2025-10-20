# 🧩 Kaiburr Task 1 — Java Backend and REST API

## 📘 Overview
This project implements a **Java Spring Boot REST API** that manages **Task** objects stored in a **MongoDB** database.  
Each Task represents a shell command that can be executed and tracked through its **TaskExecution** history.

This submission is for **Task 1** of the **Kaiburr Assessment 2025**.

---

## ⚙️ Features

✅ Create, read, delete, and search Task objects  
✅ Execute shell commands and store execution logs  
✅ MongoDB integration for persistent storage  
✅ Input validation to prevent unsafe commands  
✅ REST endpoints testable via Postman or Curl

---

## 🧱 Technology Stack

| Component | Technology |
|------------|-------------|
| Language | Java 17 |
| Framework | Spring Boot 3.x |
| Database | MongoDB |
| Build Tool | Maven |
| API Testing | Postman / Curl |

---

## 📂 Project Structure

kaiburr_1/
├── src/
│ ├── main/
│ │ ├── java/com/example/kaiburr/
│ │ │ ├── controller/TaskController.java
│ │ │ ├── model/Task.java
│ │ │ ├── model/TaskExecution.java
│ │ │ ├── repository/TaskRepository.java
│ │ │ ├── service/TaskService.java
│ │ │ └── KaiburrApplication.java
│ │ └── resources/application.properties
│ └── test/
└── pom.xml


---

## 🔧 Installation and Setup

### 1️⃣ Clone the repository
```bash
git clone https://github.com/honeygyani/Kaiburr_Task1.git
cd Kaiburr_Task1

2️⃣ Configure MongoDB

Edit your src/main/resources/application.properties:

spring.application.name=Task1
spring.data.mongodb.uri=mongodb://localhost:27017/kaiburrdb
server.port=8081

3️⃣ Build the project
mvn clean install

4️⃣ Run the application
mvn spring-boot:run

The API will start at:

http://localhost:8081


Testing with Curl
➤ Get all tasks
curl -X GET http://localhost:8080/tasks

➤ Create a task
curl -X PUT http://localhost:8080/tasks \
-H "Content-Type: application/json" \
-d "{\"id\":\"123\", \"name\":\"Print Hello\", \"owner\":\"Honey Gyani\", \"command\":\"echo Hello World!\"}"

➤ Execute a task
curl -X PUT http://localhost:8080/tasks/123/execute
