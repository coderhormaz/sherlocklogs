# SherlockLogs — Log to Story

SherlockLogs turns cryptic security logs — syslog, `auth.log` and the like — into a readable incident story, so a junior analyst doesn't have to decode raw log lines line by line to work out what actually happened.

Built for junior analysts and Blue Team work.

## Features

- Upload and parse security logs (syslog, auth.log formats)
- Reconstructs the incident as a readable narrative/story
- Retrieval over reference material with FAISS (RAG), guided by `playbook.md`
- Uses a Gemini model to generate the incident story
- Stores data in SQLite

## Tech Stack

- Python 3.12
- FastAPI-style backend
- Gemini client
- FAISS for retrieval
- SQLite

## Project Structure

- `main.py` — application entry point
- `playbook.md` — the incident-response playbook used as reference material for retrieval
- Uploads handling for incoming log files

## Getting Started

Prerequisites: Python 3.12.

```bash
pip install -r requirements.txt
python main.py
```

Set your Gemini API key as an environment variable before running — the app needs it to generate incident stories, and it won't work without one. Don't commit the key to the repo.

## Notes

- No live demo — run it locally with your own logs and API key.
