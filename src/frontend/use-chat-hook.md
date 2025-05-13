# Use Chat Hook

Description of the Use Chat Hook component.

# useChat Hook Documentation

The `useChat` hook manages chat state and provides utility methods for interacting with the chat interface and AI backend.

## State & Returned Values

- `messages`: Array of chat messages.
- `setMessages`: Function to update the messages array.
- `showConversation`: Boolean for UI state.
- `setShowConversation`: Setter for showConversation.
- `chatContainerRef`: Ref to the chat container div (for scrolling, etc.).

## Methods

### fetchAIResponse

- **Purpose:** Fetches an AI response from the backend model API.
- **Parameters:**
  - `userMessage` (string): The user's message.
  - `conversationId` (string): The current conversation's ID.
  - `mode` ("satirical" | "normal"): Satire mode toggle.
- **Usage:**
  - Sends a POST request to `/api/model` with the user message, context, and mode.
  - Returns either a single message (if only one response) or an object with multiple messages.

### includeMessage

- **Purpose:** Adds a message to the local messages state.
- **Parameters:**
  - `message` (Message): The message object to add.
- **Usage:**
  - Appends the message to the messages array.

### findPreviousMessageSendByUser

- **Purpose:** Finds the previous user message before a given message ID.
- **Parameters:**
  - `messageId` (string): The ID of the message to search before.
- **Returns:**
  - The previous user message object, or null if not found.

### setMessages

- **Purpose:** Sets the messages array directly.
- **Parameters:**
  - `messages` (Message[]): The new array of messages.

### setShowConversation

- **Purpose:** Sets the showConversation boolean.
- **Parameters:**
  - `show` (boolean): The new value.

### chatContainerRef

- **Purpose:** Ref to the chat container div, useful for scrolling or focusing.

---

This hook is used throughout the chat interface to manage state, fetch AI responses, and handle user interactions.
