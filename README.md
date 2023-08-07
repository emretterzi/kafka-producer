
# Kafka Producer with Spring Boot

This is a simple Java Spring Boot application that serves as a Kafka Producer. It demonstrates how to send messages to a Kafka topic using the KafkaTemplate and Spring Kafka integration.

## Prerequisites

- Java 8 or higher installed on your machine.
- Apache Kafka broker running on `localhost:9092`.
- PostgreSQL database installed and configured with the following credentials:
    - Username: `postgres`
    - Password: *Your_Password*
    - Database URL: `jdbc:postgresql://localhost:5432/`

## Getting Started

1. Clone the repository to your local machine.
2. Ensure that Kafka is up and running on `localhost:9092`.
3. Set up the PostgreSQL database and update the credentials in `application.properties`:
    ```properties
    spring.datasource.username=postgres
    spring.datasource.password=your_password
    spring.datasource.url=jdbc:postgresql://localhost:5432/your_database_name
    ```
4. Build the application using Maven:
    ```bash
    mvn clean package
    ```
5. Run the application:
    ```bash
    java -jar target/kafka-producer-app.jar
    ```

## API Endpoint

- **Health Check**: To send a message to the Kafka topic, make a GET request to `/producer` with the message in the request body. The message will be sent to the Kafka topic defined in the configuration.

## Configuration

The application's configuration can be found in `application.properties`. You can update the following properties as per your requirements:

- `spring.kafka.bootstrap-servers`: Comma-separated list of Kafka broker addresses.
- `spring.kafka.producer.value-serializer`: Serializer class for the message value.
- `spring.kafka.producer.key-serializer`: Serializer class for the message key.
- `kafka.topic`: The name of the Kafka topic to which messages will be sent.

## Notes

- The `ProducerService` class handles message sending to the Kafka topic using the `KafkaTemplate`.
- The `@PostConstruct` method in `ProducerService` automatically sends a test message to the Kafka topic on application startup.


## Author

- Emre Terzi
- GitHub: (https://github.com/emretterzi)

---

Please replace `your_password`, `your_database_name`, and `YourGitHubUsername` with the appropriate values in the README file. Also, add any additional details or instructions specific to your application if needed.
