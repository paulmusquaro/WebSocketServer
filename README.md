# WebSocketServer

## Overview
This project is a simple HTTP server with WebSocket communication, built using Python. The server allows users to send messages through an HTML form, which are then processed and stored in a JSON file via a UDP socket server.

## Features
- Serves static HTML, CSS, and other assets
- Handles form submissions via POST requests
- Uses a socket server for message processing and storage
- Implements basic error handling with a 404 page
- Multi-threaded execution for handling HTTP and socket communication concurrently

## Project Structure
```
├── main.py              # Main HTTP server with socket communication
├── socket_server.py     # UDP socket server for storing messages
├── socket_client.py     # Example client to send messages via socket
├── templates
│   ├── index.html       # Main page
│   ├── message.html     # Message submission page
│   ├── error.html       # 404 error page
├── static
│   ├── style.css        # Styling file
│   ├── logo.png         # Logo file (if available)
│   ├── favicon.ico      # Favicon
├── storage
│   ├── data.json        # JSON file for storing messages
└── README.md            # Documentation
```

## Installation
1. Clone the repository:
   ```sh
   git clone https://github.com/paulmusquaro/WebSocketServer.git
   cd WebSocketServer
   ```
2. Create a virtual environment (optional but recommended):
   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```
3. Install dependencies (if required in the future):
   ```sh
   pip install -r requirements.txt
   ```

## Usage
### Running the HTTP Server
Start the HTTP server by running:
```sh
python main.py
```
The server will be available at `http://localhost:3000/`.

### Running the Socket Server
The socket server runs automatically as a separate thread when executing `main.py`. If needed, you can manually run it using:
```sh
python socket_server.py
```

### Sending Messages
1. Open `http://localhost:3000/message.html` in your browser.
2. Fill in the form and submit your message.
3. The message will be processed and stored in `storage/data.json`.

### Running the Socket Client (Optional)
You can also use `socket_client.py` to send messages via the socket:
```sh
python socket_client.py
```

## Configuration
- The server runs on `http://0.0.0.0:3000/` by default.
- The socket server listens on `127.0.0.1:5000`.
- You can change these settings in `main.py`.

## License
This project is licensed under the MIT License. Feel free to modify and distribute it.

