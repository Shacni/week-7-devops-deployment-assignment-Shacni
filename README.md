[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=19823244&assignment_repo_type=AssignmentRepo)
# 🔄 Real-Time Chat Application with Socket.io

A fully functional real-time chat application built with Socket.io, React, and Express.js that demonstrates bidirectional communication between clients and server.

## 🚀 Features Implemented

### ✅ Task 1: Project Setup
- [x] Node.js server with Express
- [x] Socket.io server configuration
- [x] React front-end application
- [x] Socket.io client setup
- [x] Basic client-server connection

### ✅ Task 2: Core Chat Functionality
- [x] **User Authentication**: Simple username-based authentication
- [x] **Global Chat Room**: All users can send and receive messages
- [x] **Message Display**: Messages show sender name and timestamp
- [x] **Typing Indicators**: Shows when users are composing messages
- [x] **Online/Offline Status**: Real-time user presence tracking

### ✅ Task 3: Advanced Chat Features (3+ implemented)
- [x] **Private Messaging**: Direct messages between users
- [x] **Typing Indicators**: Real-time typing status
- [x] **User Join/Leave Notifications**: System messages for user events
- [x] **Message Delivery Acknowledgment**: Confirms message delivery

### ✅ Task 4: Real-Time Notifications
- [x] **Browser Notifications**: Web Notifications API integration
- [x] **Sound Notifications**: Audio alerts for new messages
- [x] **Unread Message Count**: Tracks unread messages
- [x] **User Join/Leave Alerts**: Notifies when users enter/exit

### ✅ Task 5: Performance and UX Optimization
- [x] **Message Pagination**: Limits stored messages to prevent memory issues
- [x] **Reconnection Logic**: Automatic reconnection with exponential backoff
- [x] **Message Search**: Search functionality for finding messages
- [x] **Connection Status**: Visual connection state indicators
- [x] **Responsive Design**: Works on desktop and mobile devices

## 🛠️ Technology Stack

- **Backend**: Node.js, Express.js, Socket.io
- **Frontend**: React, Vite
- **Package Manager**: pnpm
- **Real-time Communication**: Socket.io
- **Notifications**: Web Notifications API

## 📦 Installation & Setup

### Prerequisites
- Node.js (v18+ recommended)
- pnpm package manager

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/PLP-MERN-Stack-Development/week-5-web-sockets-assignment-DennisAmutsa.git
   cd week-5-web-sockets-assignment-DennisAmutsa
   ```

2. **Install server dependencies**
   ```bash
   cd server
   pnpm install
   ```

3. **Install client dependencies**
   ```bash
   cd ../client
   pnpm install
   ```

4. **Start the development servers**

   **Terminal 1 - Start the server:**
   ```bash
   cd server
   pnpm run dev
   ```
   Server will run on: http://localhost:5000

   **Terminal 2 - Start the client:**
   ```bash
   cd client
   pnpm run dev
   ```
   Client will run on: http://localhost:5173

## 🎯 How to Use

1. **Join the Chat**
   - Open the application in your browser
   - Enter a username and click "Join"
   - Enable notifications when prompted

2. **Send Messages**
   - Type your message in the input field
   - Press Enter or click "Send"
   - Messages appear in real-time for all users

3. **Private Messaging**
   - Click "Private" next to any user's name
   - Send private messages that only you and that user can see
   - Click "Cancel Private" to return to public chat

4. **Search Messages**
   - Use the search bar to find specific messages
   - Results show sender and message content
   - Click "Clear" to reset search

5. **Notifications**
   - Browser notifications appear when the tab is not active
   - Sound notifications play for new messages
   - Unread count shows in the title

## 🔧 API Endpoints

### Server Endpoints
- `GET /` - Server status
- `GET /api/messages` - Get all messages
- `GET /api/users` - Get online users
- `GET /api/messages/search?q=query` - Search messages

### Socket Events
- `user_join` - User joins chat
- `send_message` - Send public message
- `private_message` - Send private message
- `typing` - Typing indicator
- `disconnect` - User leaves

## 📱 Features in Detail

### Real-time Communication
- Instant message delivery
- Live typing indicators
- Real-time user presence
- Automatic reconnection

### User Experience
- Clean, responsive interface
- Connection status indicators
- Message delivery confirmation
- Smooth scrolling to new messages

### Notifications
- Browser notifications (when tab inactive)
- Sound alerts for new messages
- Unread message counter
- Visual indicators for connection status

### Performance
- Message pagination (100 message limit)
- Efficient reconnection handling
- Memory management
- Optimized Socket.io configuration

## 🚀 Deployment

### Server Deployment (Render/Railway/Heroku)
1. Set environment variables:
   - `PORT`: Server port
   - `CLIENT_URL`: Your client URL

2. Deploy using your preferred platform

### Client Deployment (Vercel/Netlify)
1. Build the project:
   ```bash
   cd client
   pnpm run build
   ```

2. Deploy the `dist` folder to your platform

## 📸 Screenshots

  ![Login Screen](./screenshots/login.png)
  ![Chat Interface](./screenshots/chat-ui.png)
  ![Private Messaging](./screenshots/private-message.gif)

## 🤝 Contributing

This is an assignment project, but feel free to fork and improve!

## 📄 License

MIT License - feel free to use this code for learning purposes.

## 👨‍💻 Author

**Dennis Amutsa**
- GitHub: [Shacni](https://github.com/Shacni)

---

**Note**: This project demonstrates advanced Socket.io implementation with real-time features, notifications, and performance optimizations as required by the Week 5 assignment. 

---

## 1. **How WebSocket Messaging Works in Your App**

- **Client (browser)** connects to the server using Socket.io.
- When you send a message in the chat UI, the client emits a socket event (e.g., `send_message`) to the server.
- The **server** receives this event, processes the message, saves it to the database, and broadcasts it to all connected clients (or just the intended recipient for private messages).
- All clients receive the new message in real time.

---

## 2. **You Can’t Use Postman for WebSocket Events**

- Postman is for HTTP requests (GET, POST, etc.), not for WebSocket events.
- To test WebSocket events, you need:
  - Your chat app’s UI (the easiest way)
  - Or a tool like [Socket.io Tester](https://amritb.github.io/socketio-client-tool/) or [websocat](https://github.com/vi/websocat) (for advanced users)

---

## 3. **How to Test WebSocket Messaging**

### **A. Using Your Chat App UI (Recommended)**
1. **Start your server and client** as before.
2. **Open your app in two browser windows/tabs** at [http://localhost:5173](http://localhost:5173).
3. **Log in as two different users.**
4. **Send messages**—you’ll see them appear in real time in both windows.

### **B. Using a Socket.io Client Tool (Optional/Advanced)**
- Go to [Socket.io Tester](https://amritb.github.io/socketio-client-tool/).
- Enter your server URL (e.g., `http://localhost:5000`).
- Connect and emit events like `send_message` with the required data.
- You’ll need to know the exact event names and payloads your server expects.

---

## 4. **Example: How Your Client Sends a Message (in code)**

```js
<code_block_to_apply_changes_from>
```

---

## 5. **Summary Table**

| Action                | How to Test                |
|-----------------------|---------------------------|
| Fetch messages        | Postman GET /api/messages |
| Send/receive messages | Chat app UI (WebSocket)   |
| Private messaging     | Chat app UI               |
| Typing indicators     | Chat app UI               |

---

**If you want to see or modify the code that handles WebSocket events, let me know which file you want to look at (e.g., `server/server.js` or `client/src/socket/socket.js`) and I can walk you through it!** 

## 🚀 Live Demo

- Frontend: [https://your-chat-client.vercel.app](https://your-chat-client.vercel.app)
- Backend: [https://your-chat-server.onrender.com](https://your-chat-server.onrender.com) 

---

## **Step-by-Step: Push Your Changes**

1. **Open a terminal** in your project root directory:
   ```
   C:\Users\HP\OneDrive\Desktop\PLP CODE\MERN STACK\week-5-web-sockets-assignment-Shacni
   ```

2. **Stage all changes** (including your updated `README.md`):
   ```bash
   git add .
   ```

3. **Commit your changes** with a message:
   ```bash
   git commit -m "Update README with live demo URLs"
   ```

   - If you see "nothing to commit," it means everything is already committed.

4. **Push to GitHub**:
   ```bash
   git push
   ```

---

## **Verify**

- Go to your repo:  
  [https://github.com/PLP-MERN-Stack-Development/week-5-web-sockets-assignment-Shacni](https://github.com/PLP-MERN-Stack-Development/week-5-web-sockets-assignment-Shacni)
- Refresh and check that your latest changes (including the new "Live Demo" section) are visible in `README.md`.

---

**If you get any errors during these steps, copy and paste the error message here and I’ll help you fix it!** 
