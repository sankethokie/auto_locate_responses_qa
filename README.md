# auto_locate_responses_qa
Automatically locate responses to previously asked questions in a live chat transcript using AI
This project implements an end-to-end Artificial Intelligence (AI) solution that automatically:
Detects questions in a live chat
Finds the best-matching answer from later messages
Resolves “open questions” in real time
Computes similarity confidence
Tracks unanswered questions
Runs fully offline — ideal for corporate laptops

The system works perfectly inside Jupyter Notebook, requires no external model downloads, and uses lightweight NLP techniques (TF-IDF + cosine similarity). It mimics patent-style behavior for “automatic linking of Q→A pairs” in teleconference and chat systems.

Features
1 Live Q/A Tracking
Messages are processed one at a time as they arrive.
2 Automatic Question Detection
Regex-based interrogative detection
Handles “?” and “soft questions” (“Can you”, “How long”, etc.)
3 Semantic Answer Matching
Uses TF-IDF + cosine similarity over a sliding window of messages.
4 Open Question Memory
Stores unresolved questions and resolves them when an appropriate answer appears.
5 Answer Confidence Score
Cosine similarity determines how confident the system is.
6 Unanswered Question Tracking
7 Zero External Dependencies
No spaCy, no NLTK, no HuggingFace, no internet.

Installation
Install required libraries (offline-safe):
pip install pandas scikit-learn

Input Format
Each chat message must contain:
speaker	text	timestamp (optional)
Alice	What is the release date?	10:01
Bob	We deploy next week.	10:02

Messages can come from:
A DataFrame
A CSV
A live message stream (API/websocket)
Manual calls to add_message()
