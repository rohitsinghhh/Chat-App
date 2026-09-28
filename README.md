# Real-Time Chat App

Full-stack real-time messaging with 1:1 and group chat, JWT auth, online presence, and typing indicators.

**Stack:** React.js · Node.js · Express.js · MongoDB · Socket.io · Tailwind CSS

---

## Quick Start

### Step 1 — Set up the backend

```bash
cd backend
npm install
cp .env.example .env
```

Open `backend/.env` and fill in:
```
MONGO_URI=mongodb://127.0.0.1:27017/realtime-chat-app
JWT_SECRET=any_long_random_string_here
```

Then run:
```bash
npm start
```

You should see:
```
MongoDB connected: 127.0.0.1
✓ Server running on http://localhost:5000
```

### Step 2 — Set up the frontend

Open a **new terminal**:
```bash
cd frontend
npm install
npm run dev
```

Open `http://localhost:5173` in your browser.

---

## MongoDB Options

**Option A — Install MongoDB locally (free)**
Download from https://www.mongodb.com/try/download/community and install. Then use:
```
MONGO_URI=mongodb://127.0.0.1:27017/realtime-chat-app
```

**Option B — MongoDB Atlas (free cloud, no install)**
1. Create a free account at https://www.mongodb.com/cloud/atlas
2. Create a free cluster → get the connection string
3. Paste it as your `MONGO_URI`

---

## Features
- Register / login with JWT authentication
- Start 1:1 conversations with any user
- Create group chats with multiple people
- Messages delivered in real time via Socket.io
- Online / offline presence indicator
- Typing indicators
- Conversation list sorted by latest activity
- Mobile-responsive layout

## Project Structure
```
realtime-chat-app/
├── backend/
│   ├── config/db.js              # MongoDB connection
│   ├── models/                   # User, Conversation, Message
│   ├── middleware/auth.js        # JWT protection
│   ├── routes/                   # auth, users, conversations, messages
│   ├── socket/socketHandler.js   # real-time events
│   └── server.js
└── frontend/
    └── src/
        ├── api/axios.js
        ├── context/              # Auth + Socket providers & hooks
        ├── components/           # Sidebar, ChatWindow, MessageBubble, etc.
        ├── pages/                # Login, Register, ChatPage
        └── utils/
