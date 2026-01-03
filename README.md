# Collaborative Code Editor

A real-time collaborative coding platform built with a FastAPI backend and a modern React frontend. Two users can share a room, write code together using a full-featured code editor, and execute it in real-time.

## Features

- **Real-time Collaboration**: Synchronized code editing via WebSockets
- **Modern UI**: Built with React, TypeScript, and Shadcn UI (Tailwind CSS)
- **Code Editor**: Professional coding experience using Monaco Editor (VS Code core)
- **Live Updates**: Real-time cursor position sharing and typing indicators
- **Code Execution**: In-browser Python code execution with output display
- **Room Management**: Create and join rooms with unique 6-digit codes
- **Auto Cleanup**: Automatic room cleanup after 24 hours

## Tech Stack

### Frontend
- **Framework**: React 18 + Vite
- **Language**: TypeScript
- **Styling**: Tailwind CSS & Shadcn UI
- **Editor**: Monaco Editor (`@monaco-editor/react`)
- **State/Data**: TanStack Query & React Hook Form
- **Icons**: Lucide React

### Backend
- **Framework**: FastAPI
- **Protocol**: WebSockets (Real-time communication)
- **Validation**: Pydantic
- **Server**: Uvicorn (ASGI)

## Project Structure

```
├── main.py                # Backend entry point
├── requirements.txt       # Backend dependencies
├── render.yaml           # Deployment configuration
└── Frontend/             # React Frontend application
    ├── src/              # Frontend source code
    ├── package.json      # Frontend dependencies
    └── ...
```

## Running Locally

### 1. Backend Setup

Initialize the Python backend service:

```bash
# Install dependencies
pip install -r requirements.txt

# Run the server
python main.py
```

The backend API will run on `http://localhost:8000`.

### 2. Frontend Setup

In a new terminal, set up the React client:

```bash
# Navigate to the frontend directory
cd Frontend

# Install dependencies
npm install

# Start the development server
npm run dev
```

The frontend will typically run on `http://localhost:5173` (check your terminal output).

## API Endpoints

### REST API
- `POST /rooms` - Create a new room
- `GET /rooms/{room_code}/status` - Check room status
- `POST /rooms/{room_code}/join` - Join a room
- `POST /rooms/{room_code}/leave` - Leave a room
- `POST /rooms/{room_code}/run` - Execute code
- `DELETE /rooms/{room_code}` - Delete a room
- `GET /rooms` - List all active rooms

### WebSocket
- `WS /ws/rooms/{room_code}` - Real-time collaboration endpoint

## WebSocket Protocol

Connect and send an INIT message:

```json
{
  "type": "INIT",
  "clientId": "unique-client-id",
  "participantId": "optional-participant-id"
}
```

Message types:
- `EDIT` - Code changes
- `CURSOR` - Cursor position updates
- `PING` - Connection keepalive

## Deployment

The project includes a `render.yaml` configuration for deploying the backend service to Render.com.

To build the frontend for production:

```bash
cd Frontend
npm run build
<<<<<<< HEAD
```
=======
```
>>>>>>> edfb23b0baebcd6ea3cfaebd4eb13974bea92e8e
