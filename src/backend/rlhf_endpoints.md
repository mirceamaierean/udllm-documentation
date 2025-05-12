# RLHF API Endpoints Documentation

## POST /api/rlhf/reward

- **Description:** Send a reward/feedback message for RLHF (Reinforcement Learning from Human Feedback).
- **Request Model:** RLHFMessage
- **Response Model:** {"message": "Reward sent"}
- **Logic:** Sends the message to the Kafka topic using KafkaService.
- **Errors:** 500 on failure.
