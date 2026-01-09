# 🌐 How Websites Work

## Simple Overview
When you type a URL in your browser and press enter, a lot of things happen behind the scenes. This document explains what happens step-by-step.

## Step-by-Step Process

### 1. You Type a URL
```
Example: https://www.example.com
```

### 2. Browser Sends a Request
Your browser sends a message to the server asking for the website.

### 3. Server Processes the Request
The server receives the request and:
- Checks if the user has permission
- Fetches the required files (HTML, CSS, JavaScript)
- Processes any data needed

### 4. Server Sends a Response
The server sends back:
- HTML (structure)
- CSS (styling)
- JavaScript (interactivity)
- Images and other files

### 5. Browser Renders the Website
Your browser:
- Reads the HTML
- Applies CSS styles
- Runs JavaScript
- Displays the final website

## Key Components

### Frontend (What You See)
- HTML: Structure
- CSS: Design/Styling
- JavaScript: Interactions
- Images, Videos, etc.

### Backend (What Happens Behind)
- Databases: Store user data, content
- Servers: Process requests
- APIs: Communication between frontend and backend
- Authentication: Login systems

## Example Flow

```
User (Browser) → Internet → Web Server → Database
     ↓                                         ↓
   Clicks                              Stores/Retrieves
   "Login"                               Information
     ↑                                         ↓
     └─────── Server sends HTML back ←────────┘
```

## Why This Matters
As a backend developer, you're responsible for:
- Making sure servers respond correctly
- Processing user data safely
- Storing data in databases
- Handling errors gracefully

## Key Takeaways

✅ Websites are two-part: Frontend (visible) + Backend (hidden)
✅ HTTP is the protocol that carries messages
✅ Servers must be fast and reliable
✅ Data security is critical
✅ Backend developers enable frontend to work
