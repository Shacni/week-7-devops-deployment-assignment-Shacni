# 🔄 Week 5: Real-Time Communication with Socket.io

## 🚀 Objective
Build a real-time chat application using Socket.io that demonstrates bidirectional communication between clients and server, implementing features like live messaging, notifications, and online status updates.

## 📂 Tasks

### Task 1: Project Setup
- Set up a Node.js server with Express
- Configure Socket.io on the server side
- Create a React front-end application
- Set up Socket.io client in the React app
- Establish a basic connection between client and server

### Task 2: Core Chat Functionality
- Implement user authentication (simple username-based or JWT)
- Create a global chat room where all users can send and receive messages
- Display messages with sender's name and timestamp
- Show typing indicators when a user is composing a message
- Implement online/offline status for users

### Task 3: Advanced Chat Features
- Create private messaging between users
- Implement multiple chat rooms or channels
- Add "user is typing" indicator
- Enable file or image sharing
- Implement read receipts for messages
- Add message reactions (like, love, etc.)

### Task 4: Real-Time Notifications
- Send notifications when a user receives a new message
- Notify when a user joins or leaves a chat room
- Display unread message count
- Implement sound notifications for new messages
- Add browser notifications (using the Web Notifications API)

### Task 5: Performance and UX Optimization
- Implement message pagination for loading older messages
- Add reconnection logic for handling disconnections
- Optimize Socket.io for performance (using namespaces, rooms)
- Implement message delivery acknowledgment
- Add message search functionality
- Ensure the application works well on both desktop and mobile devices

## 🧪 Expected Outcome
- A fully functional real-time chat application
- Smooth bidirectional communication using Socket.io
- Good user experience with proper error handling and loading states
- Implementation of at least 3 advanced chat features
- Responsive design that works on different devices

## 🛠️ Setup
1. Make sure you have Node.js installed (v18+ recommended)
2. Clone the starter code repository
3. Install server dependencies:
   ```
   cd server
   npm install
   ```
4. Install client dependencies:
   ```
   cd client
   npm install
   ```
5. Start the development servers:
   ```
   # In the server directory
   npm run dev
   
   # In the client directory
   npm run dev
   ```

## ✅ Submission Instructions
1. Accept the GitHub Classroom assignment invitation
2. Clone your personal repository that was created by GitHub Classroom
3. Complete all the tasks in the assignment
4. Commit and push your code regularly to show progress
5. Include in your repository:
   - Complete client and server code
   - A comprehensive README.md with:
     - Project overview
     - Setup instructions
     - Features implemented
     - Screenshots or GIFs of the application
6. Optional: Deploy your application
   - Deploy the server to a service like Render, Railway, or Heroku
   - Deploy the client to Vercel, Netlify, or GitHub Pages
   - Add the deployed URLs to your README.md
7. Your submission will be automatically graded based on the criteria in the autograding configuration
8. The instructor will review your submission after the autograding is complete 

---

# 🚀 **1. Deploy the Server (Backend) on Render**

### **A. Prepare Your Server for Deployment**
1. **Check CORS:**  
   Make sure your server allows requests from your deployed client.  
   In `server.js`:
   ```js
   const cors = require('cors');
   app.use(cors({
     origin: ['http://localhost:5173', 'https://your-vercel-client-url.vercel.app'], // add your deployed client URL here
     credentials: true
   }));
   ```
2. **Check Environment Variables:**  
   - `PORT` (Render sets this automatically)
   - `MONGO_URI` (your MongoDB connection string)
   - `CLIENT_URL` (your deployed client URL)

### **B. Push All Code to GitHub**
Make sure your latest code is pushed.

### **C. Deploy on Render**
1. Go to [https://render.com/](https://render.com/) and sign up/log in.
2. Click **"New Web Service"**.
3. Connect your GitHub and select your repo.
4. Set the **root directory** to `server`.
5. Set the **build command** to:
   ```
   pnpm install
   ```
6. Set the **start command** to:
   ```
   pnpm start
   ```
7. Add environment variables (`MONGO_URI`, etc.) in the Render dashboard.
8. Click **Create Web Service**.
9. Wait for deployment to finish. Copy the Render URL (e.g., `https://your-chat-server.onrender.com`).

---

# 🌐 **2. Deploy the Client (Frontend) on Vercel**

### **A. Prepare Your Client**
1. In `client/.env` (create if it doesn’t exist), set:
   ```
   VITE_SERVER_URL=https://your-chat-server.onrender.com
   ```
   (Replace with your actual Render server URL.)

2. In your code, make sure you use `import.meta.env.VITE_SERVER_URL` for the server URL.

### **B. Push All Code to GitHub**
Make sure your latest code is pushed.

### **C. Deploy on Vercel**
1. Go to [https://vercel.com/](https://vercel.com/) and sign up/log in.
2. Click **"New Project"**.
3. Import your GitHub repo.
4. Set the **root directory** to `client`.
5. Set the **build command** to:
   ```
   pnpm run build
   ```
6. Set the **output directory** to:
   ```
   dist
   ```
7. Add environment variable `VITE_SERVER_URL` with your Render server URL.
8. Click **Deploy**.
9. Copy your Vercel URL (e.g., `https://your-chat-client.vercel.app`).

---

# 📝 **3. Update README with Deployed URLs**

Add your deployed server and client URLs to your README for easy access.

---

# ✅ **4. Test Everything**

- Open your Vercel client URL in your browser.
- Make sure chat, notifications, and all features work.
- If you see CORS or connection errors, double-check your CORS settings and environment variables.

---

## **Need Help with Any Step?**

- If you get stuck, tell me which step and what error you see (copy the error message).
- If you want to use another platform (Netlify, Railway, Heroku), let me know!

---

**Let me know when you’re ready for the next step, or if you need help with a specific part of deployment!** 