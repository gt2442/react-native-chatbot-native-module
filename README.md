# React Native Chatbot with Native Android Module (Kotlin) & Socket Communication

A mobile chatbot application built in React Native that communicates with a backend service using a Native Android Module written in Kotlin. The app exchanges messages over a socket connection and uses Lottie animations to visualize connection status and bot thinking states. Developed and tested on macOS using the Android Emulator in Android Studio.

---

## Overview

This project is a small but functional proof of concept chatbot application demonstrating:

- **React Native mobile development**
- **Integration of a Native Android Module (Kotlin)**
- **Socket-based client-server communication**
- **Use of Lottie animations in mobile UI**
- **Asynchronous message handling and UI updates**

The app features:

- A messaging UI where the user interacts with a simple chatbot
- A Kotlin native module (`ChatSocket`) that manages:
  - Opening a socket connection
  - Sending user messages to a backend
  - Receiving replies
- A dynamic **Lottie status Cat** at the top of the screen showing:
  - Connecting (see image in repo)
  - Connected  (see image in repo)
  - Disconnected  (see image in repo)
- A **Lottie “catbot is thinking” animation** when waiting for server responses

---

## Tech Stack

### **Frontend**
- React Native (Android)
- TypeScript
- Lottie for React Native
- Custom chat UI 

### **Native Android**
- Kotlin
- Android Studio
- React Native Native Modules API
- Sockets using Java/Kotlin standard library

### **Backend**
- Node.js (simple socket server)
- JSON-based message protocol

### **Tools**
- macOS
- Android Emulator
- Git + GitHub

---

## Project Architecture

### High-level Flow

1. User types a message in the React Native chat input.
2. RN calls the **Native Android Module** (`ChatSocket.sendMessage()`).
3. Kotlin module opens or reuses a socket connection.
4. Message is sent to a lightweight Node.js server.
5. Server returns a response (e.g., a bot reply string).
6. Kotlin module resolves the promise back to React Native.
7. React Native:
   - Appends the bot reply to the chat history  
   - Shows or hides the **Lottie thinking animation**  
   - Updates the **connection status orb**
  

### Challenges
Challenge 1 — Socket communication errors

Problem: Disconnections caused silent failures.
Solution: Added connection status tracking + Lottie orb UI states.

### Future Improvements
- Add user profiles

- Add persistent chat history

- Integrate AI chat capabilities

