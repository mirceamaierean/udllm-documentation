# LLMService Documentation

## Class: LLMService

Handles LLM queries, vector store, embeddings, and detoxification.

### `__init__(self)`

Initializes the LLMService with:

- Qdrant client and vector store for articles
- HuggingFace embedding model
- VectorStoreIndex
- Ollama LLM
- Query engine
- Detoxify model

### `query(self, query: str, system_prompt: str) -> Tuple[str, List[ArticleMetadata]]`

Executes a query using the LLM and retrieves relevant articles.

- **query**: The user query string
- **system_prompt**: The system prompt to prepend
- **Returns**: Tuple of (response string, list of ArticleMetadata)
- Retrieves relevant nodes, extracts article metadata, synthesizes a response, and detoxifies the output.

### `_detoxify(self, text: str) -> str`

Detoxifies the input text using the Detoxify library.

- **text**: The input text to detoxify
- **Returns**: Detoxified text (or rewritten by LLM if toxicity detected)
