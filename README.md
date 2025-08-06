# Intern-Task-2---Real-Time-Applicaation
COMPANY NAME : CODTECH IT SOLUTIONS
NAME : ANANTHANARAYANAN R
INTERN ID : CT04DZ287
DOMAIN : FRONTEND DEVELOPMENT
DURATION : 4 WEEKS
MENTOR : NEELA SANTOSH

 Real-Time Chat Application
This is a simple real-time chat application built using HTML, CSS, and JavaScript. It leverages Socket.IO for real-time communication between users.

🚀 Features
Real-time message sending and receiving

Scrollable message history

Simple and clean user interface

🛠️ Technologies Used
HTML5

CSS3

JavaScript

Socket.IO (requires server-side implementation)

📁 File Structure
pgsql
Copy
Edit
real-time-chat/
├── index.html              # Main chat interface (your uploaded file)
└── server.js               # Socket.IO server (you need to implement this)
🖥️ How to Run
Set up a server (Node.js + Socket.IO)
Here's a simple server.js example you can use:


const app = require('express')();
const http = require('http').createServer(app);
const io = require('socket.io')(http);

app.get('/', (req, res) => {
    res.sendFile(__dirname + '/index.html');
});

io.on('connection', (socket) => {
    console.log('a user connected');
    socket.on('chat message', (msg) => {
        io.emit('chat message', msg);
    });
});

http.listen(3000, () => {
    console.log('listening on *:3000');
});
Install dependencies:
t
npm install express socket.io
Run the server:


node server.js
Open your browser and go to http://localhost:3000

⚠️ Note
The <script> tag in your HTML uses a local file path for socket.io.js. Replace this with:


<script src="/socket.io/socket.io.js"></script>
so it works properly with the server.
