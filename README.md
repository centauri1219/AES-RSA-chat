# AES Chat 🔐

A secure, encrypted chat application that enables private communication between two parties using military-grade AES encryption.

## 📋 Overview

This project implements a secure chat application where two users can exchange encrypted messages over a network. All communications are protected using AES-256 encryption with message integrity verification, ensuring conversations remain private and tamper-proof even over untrusted networks.

## ✨ Features

- **🔒 AES-256 Encryption**: Military-grade encryption protects all message content
- **🛡️ Message Integrity**: SHA-256 hashes verify messages haven't been tampered with
- **⚡ Real-time Communication**: Bidirectional messaging with simultaneous send/receive
- **🕐 Timestamped Messages**: Each message includes transmission timestamp
- **✅ Integrity Verification**: Visual indicators (☑/☒) show message authenticity
- **🔑 Pre-shared Key Security**: Both parties must know the same encryption key

## Preview
When correct key is entered
<img width="1517" height="331" alt="image" src="https://github.com/user-attachments/assets/57fda044-d908-409f-afdc-3fe3b3b2fd46" />

When incorrect key is entered
<img width="1498" height="302" alt="image" src="https://github.com/user-attachments/assets/a9424dc4-a058-4a94-8f09-453cdf20cc98" />


## 🚀 How It Works

1. **Server Setup**: One person runs the server and waits for connections
2. **Client Connection**: Another person connects using the server's IP and port
3. **Key Exchange**: Both parties enter the same pre-shared encryption key
4. **Secure Chat**: Messages are automatically encrypted before sending and decrypted upon receipt
5. **Verification**: Each message's integrity is verified using SHA-256 hashes

## 📦 Requirements

- Python 3.x
- `pyaes` module for pure Python AES implementation

```bash
# Windows
python -m pip install pyaes

# Linux/macOS
pip install pyaes
```

> **Note**: We chose `pyaes` for its simple, pure Python implementation. Other options like `pycrypto` (vulnerable and unmaintained) or `pycryptodome`/`pycryptodomex` are available, but we prioritized simplicity and security.

## 🛠️ Installation & Usage

### 1. Clone the Repository
```bash
git clone https://github.com/centauri1219/AES-chat.git
cd AES-chat
```

### 2. Install Dependencies
```bash
pip install pyaes
```

### 3. Start the Server
```bash
python server.py [optional_port]
```
- Default port: 5555
- Server will wait for client connection

### 4. Connect with Client
```bash
python client.py
```
- Enter server IP address
- Enter server port
- Enter the same encryption key as the server

### 5. Start Chatting!
- Type messages and press Enter to send
- Type `quit()` to exit the chat

## 🔧 Technical Details

- **Encryption**: AES block cipher with 16-byte blocks
- **Key Derivation**: SHA-256 hash of user-provided key
- **Message Format**: JSON with timestamp, message, and integrity hash
- **Padding**: Uses `~` characters to pad messages to 16-byte boundaries
- **Threading**: Multi-threaded for simultaneous send/receive operations

## 🔒 Security Features

- **Confidentiality**: AES-256 encryption protects message content
- **Integrity**: SHA-256 hashes detect message tampering
- **Authentication**: Pre-shared key ensures only authorized parties can communicate

## ⚠️ Important Notes

- Server must be started before client attempts connection
- Both parties must use the exact same encryption key
- This is for educational/demonstration purposes
- Consider additional security measures for production use

## 📄 License

This project is open source. Feel free to use and modify as needed.

