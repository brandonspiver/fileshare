## Peer-to-peer file sharing (Java + Swing)

A simple peer-to-peer file sharing and chat app. A central TCP server handles
presence and messaging, while clients send files directly to each other over UDP.

### Features
- Global chat and one-to-one whisper messages
- File search across connected clients
- Direct client-to-client downloads with progress bars
- Simple Swing GUI

### Requirements
- Java 8+ (JDK recommended for compiling)
- A `files/` directory next to `client.java` for shared files

### Setup
1. Create a local folder for files:

   ```powershell
   mkdir files
   ```

2. Compile:

   ```powershell
   javac Server.java client.java
   ```

### Run
1. Start the server:

   ```powershell
   java Server <port>
   ```

   Example:

   ```powershell
   java Server 5555
   ```

2. Start one or more clients (in new terminals):

   ```powershell
   java client <server_address> <server_port> <client_port>
   ```

   Example:

   ```powershell
   java client 127.0.0.1 5555 6001
   ```

### Notes
- Each client must choose a unique username at startup.
- `client_port` is the UDP port used for file transfers; use a free port per client.
- Files are sent from the local `files/` directory only.
