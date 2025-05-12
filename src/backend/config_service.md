# Config Service Documentation

## Class: Settings

Loads and stores application configuration from environment variables using Pydantic BaseSettings.

### Fields

- **QDRANT_URL**: URL for the Qdrant vector store
- **EMBEDDING_MODEL**: Name of the embedding model (default: BAAI/bge-large-en-v1.5)
- **OLLAMA_MODEL**: Name of the Ollama LLM model (default: mistral)
- **DATABASE_URL**: Database connection string (default: SQLite)
- **MULTIPLE_PROMPT_PROB**: Probability for multiple prompts (float)
- **KAFKA_BROKER**: Kafka broker address
- **KAFKA_TOPIC**: Kafka topic for RLHF

### Inner class: Config

- **env_file**: Specifies that configuration is loaded from `.env`

## Function: get_settings()

Returns a cached instance of the Settings class for use throughout the app.
