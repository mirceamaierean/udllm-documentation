# PromptService Documentation

## Class: PromptService

Handles CRUD operations and statistics for system prompts.

### `get_random_prompt(db: Session, other_prompt_ids: list[int] = []) -> SystemPrompt`

Fetches a random system prompt not in the provided list, updates its usage stats.

- **db**: SQLAlchemy session
- **other_prompt_ids**: List of prompt IDs to exclude
- **Returns**: A random SystemPrompt object

### `get_favorite_prompt(db: Session) -> SystemPrompt`

Fetches the most liked system prompt.

- **db**: SQLAlchemy session
- **Returns**: The SystemPrompt object with the most likes

### `add_prompt(db: Session, prompt_text: str) -> SystemPrompt`

Adds a new system prompt to the database.

- **db**: SQLAlchemy session
- **prompt_text**: The prompt text to add
- **Returns**: The newly created SystemPrompt object

### `like_prompt(db: Session, prompt_id: int) -> SystemPrompt`

Increments the like count for a prompt.

- **db**: SQLAlchemy session
- **prompt_id**: The ID of the prompt to like
- **Returns**: The updated SystemPrompt object

### `dislike_prompt(db: Session, prompt_id: int) -> SystemPrompt`

Increments the dislike count for a prompt.

- **db**: SQLAlchemy session
- **prompt_id**: The ID of the prompt to dislike
- **Returns**: The updated SystemPrompt object

### `get_prompt_stats(db: Session) -> list`

Fetches all system prompts for statistics.

- **db**: SQLAlchemy session
- **Returns**: List of all SystemPrompt objects
