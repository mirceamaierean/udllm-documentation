# Message Service API Documentation

## addMessage

- **Purpose:** Adds a new message to a conversation.
- **Endpoint:** `POST /api/message`
- **Authentication:** Required
- **Parameters:**
  - `content` (string): The message content.
  - `conversationId` (string): The conversation's ID.
  - `userId` (string): The sender's user ID.
- **Example Request Body:**
  ```json
  {
    "content": "Hello!",
    "conversationId": "abc123",
    "userId": "user456"
  }
  ```
- **Response:**
  - Returns the created message object.

---

## updateLikeDislike

- **Purpose:** Updates the like/dislike status for a prompt (AI message candidate).
- **Endpoint:** `POST /api/prompts`
- **Authentication:** Required
- **Parameters:**
  - `promptId` (string): The prompt's unique ID.
  - `liked` (boolean): `true` for like, `false` for dislike.
- **Example Request Body:**
  ```json
  {
    "promptId": "prompt789",
    "liked": true
  }
  ```
- **Response:**
  - `{ "message": "Prompt updated" }` on success.

---

## rewardMessages

- **Purpose:** Rewards or penalizes an AI response based on user feedback.
- **Endpoint:** `POST /api/message/reward`
- **Authentication:** Not required (proxies to backend RLHF endpoint)
- **Parameters:**
  - `prompt` (string): The user's message (prompt).
  - `response` (string): The AI's response.
  - `reward` (number): 1 for like, -1 for dislike.
- **Example Request Body:**
  ```json
  {
    "prompt": "What is the news today?",
    "response": "Here is a satirical take...",
    "reward": 1
  }
  ```
- **Response:**
  - `{ "message": "Reward received for ..." }` on success.

---

## fetchAIResponse (POST /api/model)

- **Purpose:** Gets AI response(s) from the backend model.
- **Endpoint:** `POST /api/model`
- **Authentication:** Not required
- **Parameters:**
  - `userMessage` (string): The user's message.
  - `context` (string): Conversation context.
  - `mode` ("satirical" | "normal"): Satire mode toggle.
- **Example Request Body:**
  ```json
  {
    "userMessage": "What's the latest news?",
    "context": "user: ...\nai: ...",
    "mode": "satirical"
  }
  ```
- **Response:**
  ```json
  {
    "messages": [{ "content": "AI response", "promptId": 123 }],
    "sender": "ai",
    "articles": ["https://...", "https://..."]
  }
  ```

# Message Service

Description of the Message Service component.
