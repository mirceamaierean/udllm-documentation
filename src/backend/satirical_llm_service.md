# SatiricalLLMService Documentation

## Class: SatiricalLLMService

Handles satirical/creative LLM queries, separate vector store, and detoxification.

### `__init__(self)`

Initializes the SatiricalLLMService with:

- Qdrant client and vector store for satirical articles
- HuggingFace embedding model
- VectorStoreIndex
- Ollama LLM (higher temperature for creativity)
- Query engine

### `generate_satirical_response(self, query: str, system_prompt: str = None) -> Tuple[str, List[ArticleMetadata]]`

Generates a satirical response based on the user's query and relevant satirical articles.

- **query**: The user query string
- **system_prompt**: Optional system prompt for additional context
- **Returns**: Tuple of (satirical response string, list of ArticleMetadata)
- Constructs a satirical prompt, retrieves relevant nodes, extracts article metadata, synthesizes a response, and detoxifies the output.

### `_detoxify(self, text: str) -> str`

Detoxifies the input text using the Detoxify library.

- **text**: The input text to detoxify
- **Returns**: Detoxified text (or rewritten by LLM if toxicity detected, keeping satirical tone and emojis)
