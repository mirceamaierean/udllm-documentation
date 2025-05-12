# Health API Endpoints Documentation

## GET /api/health

- **Description:** Health check for the API and its dependencies.
- **Response:** JSON with status, model, vector store, and embedding model info.
- **Logic:**
  - Checks connection to the vector store (Qdrant).
  - Returns model and embedding model info if healthy.
  - Returns 503 if any dependency is unhealthy.
