# Producer-Consumer Application

A simple **Spring Boot** application demonstrating the **Producer-Consumer pattern** using **RabbitMQ**.

## Technologies Used
- Java
- Spring Boot
- RabbitMQ
- Postman (for API testing)

---

## Setup Instructions

### 1. Prerequisites
- Java 17+
- Maven
- RabbitMQ Server running locally or remotely

### 2. Clone the Repository
```bash
git clone <your-repo-url>
cd producer-consumer-application
```

### 3. Start RabbitMQ Server
- Default Host: `localhost`
- Default Port: `5672`
- Default Credentials: `guest/guest`

> You can use Docker to run RabbitMQ:
```bash
docker run -d --hostname my-rabbit --name some-rabbit -p 5672:5672 -p 15672:15672 rabbitmq:3-management
```

### 4. Run the Application
```bash
./mvnw spring-boot:run
```

---

## API Endpoints

### 1. Produce Message (POST)
- **URL:** `http://localhost:8080/produce`
- **Method:** `POST`
- **Request Body (JSON):**
```json
{
  "message": "Your message here"
}
```
- **Description:** Sends a message to the RabbitMQ queue.

---

### 2. Consume Message (GET)
- **URL:** `http://localhost:8080/consume`
- **Method:** `GET`
- **Description:** Consumes the next message from the RabbitMQ queue.

---

## Example Usage with Postman

### Produce API
- POST `http://localhost:8080/produce`
- Body (JSON):
```json
{
  "message": "Test Message"
}
```

### Consume API
- GET `http://localhost:8080/consume`

---

## Project Structure
```
src/main/java/com/example/producerconsumer
 ├── config
 │    └── RabbitMQConfig.java
 ├── controller
 │    ├── ProducerController.java
 │    └── ConsumerController.java
 ├── service
 │    ├── ProducerService.java
 │    └── ConsumerService.java
 └── ProducerConsumerApplication.java
```

---

## Dependencies
- `spring-boot-starter-web`
- `spring-boot-starter-amqp`
- `spring-boot-starter`

---

## Author
**Adesh Dilip Gadekar**

---

## License
This project is for learning and demo purposes only.
