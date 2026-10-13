# 📚 QuestionBank

A full-stack web application built with Spring Boot and Thymeleaf for managing and organizing question banks — designed for educators, trainers, and students.

## 🚀 Tech Stack

| Layer | Technology |
|---|---|
| Backend | Java 25, Spring Boot 4.0.6 |
| ORM | Hibernate / Spring Data JPA |
| Database | MySQL 9.7 |
| Frontend | Thymeleaf Templates |
| Build Tool | Maven |
| Server | Apache Tomcat 11 (embedded) |
| Dev Tools | Spring Boot DevTools |

<!-- CHECK: Java and Spring Boot versions above must match <java.version> and the parent version in pom.xml -->

## ✨ Features

- 📝 Create, Read, Update, Delete (CRUD) questions
- 🗂️ Organize questions by subject/category
- 🔍 Search and filter question bank
- 📊 8 JPA Repository interfaces for data access
- 🔄 Auto DDL update with Hibernate
- 🌐 Web-based UI with Thymeleaf templates

<!-- CHECK: remove the "Search and filter" line if the app does not have it -->

## 🛠️ Prerequisites

Before running this project, make sure you have:

- ☕ Java 25 (same version as in pom.xml)
- 🐬 MySQL Server running on localhost:3306
- 📦 Maven 3.x
- 🌱 Spring Tools Suite (STS) or any IDE

## ⚙️ Setup & Configuration

### 1. Clone the Repository

```bash
git clone https://github.com/Himaja-23110/QuestionBank.git
cd QuestionBank
```

### 2. Database Configuration

The app auto-creates the database. Just make sure MySQL is running.

Update `src/main/resources/application.properties` if needed:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/question_bank?createDatabaseIfNotExist=true&useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=root
```

### 3. Run the Application

Using Maven:

```bash
mvn spring-boot:run
```

Using STS: Right-click project → Run As → Spring Boot App

### 4. Access the App

```
http://localhost:8085
```

## 📁 Project Structure

```
QuestionBank/
├── src/
│   ├── main/
│   │   ├── java/com/qbank/
│   │   │   ├── controller/        # MVC Controllers
│   │   │   ├── dto/               # Data Transfer Objects
│   │   │   ├── entity/            # JPA Entities
│   │   │   ├── repository/        # Spring Data JPA Repos (8 interfaces)
│   │   │   └── service/           # Business Logic
│   │   └── resources/
│   │       ├── templates/         # Thymeleaf HTML templates
│   │       └── application.properties
│   └── test/java/                 # Tests
├── pom.xml
└── README.md
```

## 🔧 Application Properties

```properties
# App
spring.application.name=QuestionBank
server.port=8085

# JPA
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true

# Logging
logging.level.org.springframework.web=DEBUG
logging.level.org.hibernate.SQL=DEBUG

# Thymeleaf
spring.thymeleaf.cache=false
```

## 🐛 Common Issues

### Port Already in Use

```
Web server failed to start. Port 8085 was already in use.
```

**Fix:** Change the port in `application.properties`:

```properties
server.port=8086
```

Or kill the process using the port:

```bash
# Windows
netstat -ano | findstr :8085
taskkill /PID <PID> /F
```

### MySQL Connection Error

- Make sure the MySQL service is running
- Check the username/password in `application.properties`
- The database `question_bank` will be auto-created on first run

## 👤 Author

**Pogiri Himaja**
📧 pogirihimaja86@gmail.com
🔗 [GitHub](https://github.com/Himaja-23110)
