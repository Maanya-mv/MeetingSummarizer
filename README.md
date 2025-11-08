# Meeting Summarizer (Python)

## Overview

Meeting Summarizer is a Python-based application that allows users to upload an audio file of a meeting. The system processes the input, extracts key points, and generates a concise meeting summary. This eliminates manual note-taking and provides quick insights.

---

## Features

* Audio Upload: Accepts `.mp3`, `.wav`, and other formats.
* Automatic Speech-to-Text: Converts audio to text using ASR (Automatic Speech Recognition).
* Transcript Upload: Users can upload an existing transcript instead of audio.
* Smart Summarization: Uses NLP to generate a clear summary of the meeting content.
* Action Item Detection (optional enhancement): Extracts tasks, deadlines, and decisions.
* Export Options (optional enhancement): Output summary as `.txt`, `.pdf`, or `.json`.

---

## Tech Stack

| Component         | Technology Used                            |
| ----------------- | ------------------------------------------ |
| Backend API       | FastAPI / Flask                            |
| Speech-to-Text    | Whisper, SpeechRecognition                 |
| NLP Summarization | Transformers, Hugging Face / OpenAI models |
| File Handling     | Python standard libs + pydub               |

---

## Project Structure

```
meeting-summarizer/
├── main.py                # Backend logic (API endpoints)
├── summarizer.py          # Summarization/NLP logic
├── speech_to_text.py      # Audio → text processing
├── uploads/               # User files (audio/transcripts)
└── README.md              # Documentation
```

---

## How It Works

1. User uploads audio or transcript through UI/API.
2. If audio is uploaded, the system generates a transcript using a speech-to-text model.
3. Text/transcript is summarized using NLP.
4. Summary is returned to the user via API/UI.

---

## Setup Instructions

### Prerequisites

Install:

* Python 3.8 or above
* pip

### Install Dependencies

```
pip install -r requirements.txt
```

### Run Application

```
uvicorn main:app --reload
```

Open `http://127.0.0.1:8000/docs` to test the API.

---

## API Endpoints

| Method | Endpoint             | Description                                        |
| ------ | -------------------- | -------------------------------------------------- |
| POST   | `/upload-audio`      | Upload audio file to generate transcript + summary |
| POST   | `/upload-transcript` | Upload transcript to generate summary              |

---

## Output Example

```
Summary:
- Discussed next sprint deliverables
- Deadline moved to Friday
- Action item: John to send progress update by tomorrow
```

---

## Future Enhancements

* Real-time summarization during live meetings
* Key topic extraction and tagging
* Support for multiple languages

---

## License

This project is licensed under the MIT License.

---

