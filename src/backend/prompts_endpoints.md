# System Prompts API Endpoints Documentation

## POST /api/system-prompts

- **Description:** Create a new system prompt.
- **Request Model:** SystemPromptCreate
- **Response Model:** SystemPromptResponse
- **Logic:** Adds a new prompt to the database.
- **Errors:** 500 on failure.

## POST /api/system-prompts/{prompt_id}/like

- **Description:** Like a system prompt.
- **Response Model:** SystemPromptResponse
- **Logic:** Increments the like count for the specified prompt.
- **Errors:** 404 if not found, 500 on other errors.

## POST /api/system-prompts/{prompt_id}/dislike

- **Description:** Dislike a system prompt.
- **Response Model:** SystemPromptResponse
- **Logic:** Increments the dislike count for the specified prompt.
- **Errors:** 404 if not found, 500 on other errors.

## GET /api/system-prompts

- **Description:** Get all system prompts and their stats.
- **Response Model:** List[SystemPromptResponse]
- **Logic:** Returns all system prompts from the database.
