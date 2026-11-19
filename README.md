# AI-Powered Customer Support Chatbot

A Python chatbot for customer support and frequently asked questions. It uses natural language processing, keeps conversation context, looks up and cancels demo orders, and stores interactions in SQLite.

## Features

- Answers common customer-support questions
- Understands follow-up questions
- Handles spelling mistakes
- Looks up and cancels demo orders
- Provides a simple chat interface
- Stores chat logs and feedback
- Includes an admin dashboard
- Supports optional Transformer-based matching

## Technology

- Python
- Flask
- NLTK
- scikit-learn
- SQLite
- HTML, CSS, and JavaScript

## Setup

### 1. Create a virtual environment

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

### 2. Install dependencies

```powershell
pip install -r requirements.txt
```

### 3. Start the application

```powershell
python app.py
```

Open [http://127.0.0.1:5000](http://127.0.0.1:5000) in your browser.

## Running Tests

```powershell
python -m pytest -q
```

## Admin Dashboard

Open [http://127.0.0.1:5000/admin](http://127.0.0.1:5000/admin).

Set an admin token before starting the application:

```powershell
$env:ADMIN_TOKEN="choose-a-long-secret"
python app.py
```

Use the token in the dashboard request header as `X-Admin-Token`.

## Docker

Build and run the application with Docker:

```powershell
docker build -t customer-support-chatbot .
docker run -p 5000:5000 -e ADMIN_TOKEN="choose-a-long-secret" -v chatdata:/data customer-support-chatbot
```

## Project Structure

```text
app.py               Flask application and routes
bot/                 Chatbot logic, NLP, and database handling
data/intents.json    Chat intents and responses
static/              Frontend CSS and JavaScript
templates/           Chat and admin HTML pages
tests/               Automated tests and evaluation scripts
```

## Customization

Edit `data/intents.json` to add or update questions and answers. Restart the application after making changes.

For better support of different wording, install the optional Transformer dependencies:

```powershell
pip install -r requirements-transformers.txt
$env:CHATBOT_BACKEND="transformers"
python app.py
```

## Author

**Author:** Raman Kumar

**GitHub Repo:** https://github.com/RamanKumar-pro/AI-Powered-Customer-Support-Chatbot.git
