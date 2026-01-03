# Collaborative Code Editor API

A real-time collaborative coding platform built with FastAPI and WebSockets. Two users can share a room, write code together, and execute it in real-time.

## Features

- Create and join coding rooms with 6-digit codes
- Real-time code synchronization via WebSockets
- Support for 2 participants per room
- Live cursor position sharing
- In-browser Python code execution
- Automatic room cleanup after 24 hours

## Installation

```bash
pip install -r requirements.txt
```

## Running Locally

```bash
python main.py
```

Server runs on `http://localhost:8000`

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
- `WS /ws/rooms/{room_code}` - Real-time collaboration

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

Configured for Render.com deployment via `render.yaml`. Set `autoDeploy: true` for automatic deployments.

## Tech Stack

- FastAPI - Web framework
- WebSockets - Real-time communication
- Pydantic - Data validation
- Uvicorn - ASGI server

## License

Open source project for educational purposes.
