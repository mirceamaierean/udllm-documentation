# Database Schema Documentation

This document describes the main tables and relations in the Newsito Informiro database, as defined in `prisma/schema.prisma`.

---

## User

- **id**: String (PK)
- **name**: String (optional)
- **email**: String (unique, optional)
- **emailVerified**: DateTime (optional)
- **image**: String (optional)
- **role**: String (default: "user")
- **accounts**: [Account] (relation)
- **Conversation**: [Conversation] (relation)
- **Message**: [Message] (relation)
- **sessions**: [Session] (relation)

---

## Account

- **id**: String (PK)
- **userId**: String (FK to User)
- **type**: String
- **provider**: String
- **providerAccountId**: String
- **refresh_token**: String (optional)
- **access_token**: String (optional)
- **expires_at**: Int (optional)
- **token_type**: String (optional)
- **scope**: String (optional)
- **id_token**: String (optional)
- **session_state**: String (optional)
- **user**: User (relation)

---

## Session

- **id**: String (PK)
- **sessionToken**: String (unique)
- **userId**: String (FK to User)
- **expires**: DateTime
- **user**: User (relation)

---

## VerificationToken

- **identifier**: String
- **token**: String (unique)
- **expires**: DateTime

---

## SystemPrompts

- **id**: Int (PK, autoincrement)
- **prompt**: String (unique, optional)
- **likes**: Int (default: 0)
- **created_at**: DateTime (default: now)
- **last_used**: DateTime (optional)
- **used**: Int (default: 0)
- **dislikes**: Int (default: 0)

---

## Source

- **url**: String (PK)
- **Report**: [Report] (relation)

---

## Message

- **id**: String (PK)
- **content**: String
- **senderId**: String (FK to User)
- **createdAt**: DateTime (default: now)
- **conversationId**: String (FK to Conversation)
- **conversation**: Conversation (relation)
- **sender**: User (relation)
- **Report**: [Report] (relation)

---

## Conversation

- **id**: String (PK)
- **createdAt**: DateTime (default: now)
- **updatedAt**: DateTime (auto-updated)
- **satirical**: Boolean (default: false)
- **userId**: String (FK to User)
- **title**: String
- **user**: User (relation)
- **messages**: [Message] (relation)

---

## Report

- **id**: String (PK)
- **messageId**: String (FK to Message)
- **sourceId**: String (FK to Source)
- **createdAt**: DateTime (default: now)
- **updatedAt**: DateTime (auto-updated)
- **message**: Message (relation)
- **source**: Source (relation)

---

**Notes:**

- All relations are enforced with foreign keys and cascading deletes where specified.
- The schema supports authentication (NextAuth), chat conversations, messages, prompt feedback, and source reporting.
