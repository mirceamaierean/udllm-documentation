# KafkaService Documentation

## Class: KafkaService

Handles sending messages to a Kafka broker.

### `__init__(self)`

Initializes the KafkaService with a KafkaProducer using the broker from settings.

### `send_message(self, topic: str, message: RLHFMessage)`

Sends a message to the specified Kafka topic.

- **topic**: The Kafka topic to send the message to
- **message**: The RLHFMessage object to send (serialized as JSON)
- Prints status and handles exceptions
