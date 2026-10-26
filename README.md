# ITE183_Lab2_Websocket
# ITE183 Lab 2 – WebSocket Server

A simple chat server built using **Bonezegei Script Language (`.bzg`)**. It uses HTTP to serve a web page and WebSockets to send messages between connected clients.

## Features

- Runs a web server on port `8000`
- Supports WebSocket connections
- Sends a welcome message when a client connects
- Broadcasts messages to all connected clients
- Logs connections, messages, and disconnections
- Includes a simple browser-based chat client
- Shows a custom 404 page for unknown routes

## Project Structure

```text
.
├── app.bzg
├── package.json
├── lib/
│   ├── http.bzg
│   ├── http.json
│   └── http/
│       └── http.dll
├── public/
│   ├── index.html
│   └── 404.html
|   └── beluga-logo.jpg
└── README.md
```

## Requirements

- Windows
- Bonezegei interpreter
- A modern web browser

## How to Run

1. Open a terminal in the project folder.
2. Start the server:

   ```bash
   bonezegei app.bzg
   ```

   Or use npm:

   ```bash
   npm start
   ```

3. Open `http://localhost:8000` in your browser.
4. Open the same page in another tab to test the chat.
5. Send a message and check if it appears in both tabs.

## How It Works

### HTTP Routes

| Route | Purpose |
|---|---|
| `/` | Opens the main web page |
| Other routes | Shows the 404 page |

### WebSocket Events

| Event | Purpose |
|---|---|
| `onConnect` | Runs when a client connects and sends a welcome message |
| `onData` | Runs when a client sends a message and broadcasts it to everyone |
| `onDisconnect` | Runs when a client disconnects |

## Main HTTP Methods

| Method | Purpose |
|---|---|
| `http(port)` | Creates the server |
| `sendFile()` | Sends a file to the browser |
| `sendResponse()` | Sends an HTTP response |
| `send()` | Sends a message to one client |
| `sendAll()` | Sends a message to all clients |
| `run()` | Starts the server |

## Customization

- **Change the port:** Update `http(8000)` in `app.bzg` and the WebSocket URL in `index.html`.
- **Send a reply to one client:** Use `server.send(clientId, "Your message")`.
- **Add a page:** Add a route in `app.bzg` and create the corresponding file in the `public` folder.

## Troubleshooting

- **Cannot connect:** Make sure the server is running and the port matches.
- **Port is already in use:** Close the program using port `8000` or choose another port.
- **Command not recognized:** Make sure Bonezegei is installed and added to your PATH.

Lab Documentation
Verification & Screenshot Deliverables
<img width="510" height="135" alt="Screenshot 2026-10-26 150443" src="https://github.com/user-attachments/assets/1cbe1afd-10da-4669-83a2-8f8eda7ceb8c" />

Demonstrating successful installation of Bonezegei v1.3.3.

bzg -v

Figure 1: Terminal output showing version 1.3.3.

Server Startup
<img width="1111" height="353" alt="Server Startup" src="https://github.com/user-attachments/assets/3619cbb7-9f9d-42e4-9b9f-c0730626ff6a" />

startup

Figure 2: Successful active server startup on port 

Multi-Client Real-Time Interaction
<img width="1903" height="1023" alt="Multi-Client Real-Time Interaction" src="https://github.com/user-attachments/assets/1f7812e1-efb2-454f-9994-05d4f8f3745e" />

Chatting around

Figure 3: Multi-client concurrent session testing demonstrating real-time message broadcasting and character updates.

Custom 404 Response Page
<img width="1100" height="355" alt="Custom 404 Response Page" src="https://github.com/user-attachments/assets/f904ed1e-b00e-428c-8c4b-5cf3c1977e16" />

404

Figure 4: Custom 404.html error page rendered for undefined path requests.

beluga whale
<img width="612" height="433" alt="beluga-logo" src="https://github.com/user-attachments/assets/0daa719c-0083-4a74-aafd-2539f82818c9" />

## License

MIT
