# AI-Enhanced Learning Assistant Platform

This project is a full-stack application for generating and evaluating academic questions using Google Gemini AI, with PDF upload, web search, and threaded chat features.

## Project Structure

```
backend/
  server.py           # Flask backend server
  requirements.txt    # Python dependencies
frontend/
  ...                 # React frontend (see below)
```

## Backend (Flask)
- Handles PDF uploads, question generation, answer evaluation, web search, and threaded chat APIs.
- Uses Google Gemini API for AI tasks.
- Requires Python 3.8+ and the following packages:
  - Flask
  - flask_cors
  - python-dotenv
  - PyPDF2
  - google-generativeai

### Setup
1. Install Python dependencies:
   ```powershell
   cd backend
   pip install -r requirements.txt
   ```
2. Create a `.env` file in `backend/` with your Gemini API key:
   ```env
   GEMINI_API_KEY=your_api_key_here
   ```
3. Run the server:
   ```powershell
   python server.py
   ```
   The server runs on `http://localhost:5002`.

## Frontend (React)
- Located in `frontend/`.
- Uses React, Tailwind CSS, and Firebase.
- Handles user authentication, PDF upload, question display, answer evaluation, chat threads, and web search.

### Setup
1. Install Node.js dependencies:
   ```powershell
   cd frontend
   npm install
   ```
2. Start the frontend:
   ```powershell
   npm start
   ```
   The app runs on `http://localhost:3000`.

## API Endpoints
- `POST /process-pdf` — Upload PDF and generate questions
- `POST /evaluate-answer` — Evaluate student answer vs model answer
- `POST /web-search` — Get academic answer to a query
- `GET/POST /threads` — Manage chat threads
- `POST /threads/<thread_id>/messages` — Add message to thread
- `POST /threads/<thread_id>/messages/<message_id>/report` — Report a message

## Notes
- Ensure both backend and frontend are running for full functionality.
- All AI features require a valid Gemini API key.
- For development, CORS is enabled for `http://localhost:3000`.

## License
MIT
