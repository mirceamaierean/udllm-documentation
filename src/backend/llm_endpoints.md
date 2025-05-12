# LLM API Endpoints Documentation

## POST /api/llm/prompt

- **Description:** Handles LLM and satirical LLM queries.
- **Request Model:** PromptRequest
- **Response Model:** LLMResponse
- **Logic:**
  - If `mode` is "satirical", uses SatiricalLLMService to generate a satirical response.
  - Otherwise, uses LLMService to generate a normal response, using the favorite system prompt.
  - With a certain probability, also returns a second response using a different random system prompt.
- **Errors:** Returns 500 on exception.
