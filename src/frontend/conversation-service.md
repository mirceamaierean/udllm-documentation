# Conversation Service

Description of the Conversation Service component.

# Conversation Service API Documentation

## getAllConversations

- **Purpose:** Fetches all conversations for the current user.
- **Endpoint:** `GET /api/conversations`
- **Authentication:** Required
- **Parameters:** None
- **Example Request:**
  ```http
  GET /api/conversations
  ```
- **Response:**
  ```json
  {
    "conversations": [
      { "id": "abc123", "title": "...", ... }
    ]
  }
  ```

---

## getConversatioMessagesById

- **Purpose:** Fetches all messages for a specific conversation.
- **Endpoint:** `GET /api/conversation/?conversationId={id}`
- **Authentication:** Required
- **Parameters:**
  - `conversationId` (string): The conversation's ID (as a query parameter).
- **Example Request:**
  ```http
  GET /api/conversation/?conversationId=abc123
  ```
- **Response:**
  ```json
  {
    "messages": [ ... ]
  }
  ```

---

## createConversation

- **Purpose:** Creates a new conversation with a given title.
- **Endpoint:** `POST /api/conversation`
- **Authentication:** Required
- **Parameters:**
  - `title` (string): The title of the new conversation.
- **Example Request Body:**
  ```json
  {
    "title": "My new chat"
  }
  ```
- **Response:**
  - Returns the created conversation object.

---

## deleteConversation

- **Purpose:** Deletes a conversation by its ID.
- **Endpoint:** `DELETE /api/conversation?conversationId={id}`
- **Authentication:** Required
- **Parameters:**
  - `conversationId` (string): The conversation's ID (as a query parameter).
- **Example Request:**
  ```http
  DELETE /api/conversation?conversationId=abc123
  ```
- **Response:**
  ```json
  { "message": "Conversation deleted" }
  ```
