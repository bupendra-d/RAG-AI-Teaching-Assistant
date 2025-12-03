## 📚 RAG-AI Teaching Assistant:
# A Retrieval-Augmented Generation system that turns your own lecture videos into a personalized AI tutor.


## 🚀 Overview:
# RAG-AI Teaching Assistant is a complete pipeline that takes your lecture videos, extracts their audio, transcribes them to structured JSON, converts them into vector embeddings, and finally answers user questions using an LLM with context from your lecture content.

# This lets students and educators build their own AI-powered teaching assistant from scratch — on their own data, without manually writing notes.


## 🎯 Key Features:
🎥 Convert videos → mp3
🎧 Transcribe mp3 → JSON text using Whisper
🧠 Generate vector embeddings from the transcript
🔍 Similarity search to find the most relevant chunks
💬 LLM-powered answer generation
🗂️ Clean and simple project structure
🛠️ Easy to extend or plug into your app


│
├── video_to_mp3.py          # Convert videos → MP3
|
├── mp3_to_json.py           # Convert MP3 → JSON transcript
|
├── preprocess_json.py       # Create embeddings + save vector store
|
├── process_incoming.py      # Takes user query → returns AI answer
│
├── videos/                  # Place raw lecture videos here
|
├── mp3/                     # Auto-generated MP3 outputs
|
├── json/                    # Auto-generated transcripts
|
├── data/                    # Embeddings, vector store, joblib files
│
└── Readme.md                # Documentation (this file)


## 📂 Project Structure:
# RAG-AI-Teaching-Assistant:
(1) video_to_mp3.py - Convert videos → MP3;

(2) mp3_to_json.py - Convert MP3 → JSON transcript;

(3) preprocess_json.py - Create embeddings + save vector store;

(4) process_incoming.py - Takes user query → returns AI answer;

(5) videos - Place raw lecture videos here;

(6) mp3 - Auto-generated MP3 outputs;

(7) json - Auto-generated transcripts;

(8) data - Embeddings, vector store, joblib files;

(9) Readme.md - Documentation (this file).


## 🧰 Tech Stack:
Python 3.10+
OpenAI Whisper – for transcription
Sentence Transformers / Embeddings
Pandas – for DataFrames
Joblib – for saving vector stores
FAISS / Similarity Search (depending on your implementation)
Any LLM API (OpenAI / Groq / others)


## 🛠️ Installation:
1️⃣ Install dependencies:
pip install -r requirements.txt


## 🚦 How to Use the Project:
# Step 1 – Place your lecture videos
Put all your videos inside the videos/ folder.
videos/
   ├── Lecture1.mp4
   ├── Lecture2.mkv
   └── ...

# Step 2 – Convert Videos → MP3
Run: python video_to_mp3.py
This creates:
mp3/
   ├── Lecture1.mp3
   ├── Lecture2.mp3

# Step 3 – Convert MP3 → JSON Transcripts
Run: python mp3_to_json.py
This generates:
json/
   ├── Lecture1.json
   ├── Lecture2.json

# Step 4 – Preprocess JSON → Embeddings & Vector Store
Run: python preprocess_json.py
This script will:
Combine all JSONs → DataFrame
Generate embeddings
Save them to a .joblib file

Output saved inside:
data/
   ├── embeddings.joblib
   └── dataframe.pkl

# Step 5 – Question Answering (RAG)
Now query the teaching assistant:
python process_incoming.py "Explain SQL indexes"

The system:
Loads embeddings
Finds the most relevant chunks
Builds a contextual prompt
Sends to your LLM
Returns a detailed answer


## 🧠 How the RAG Pipeline Works:
# 🎥 Video → 🔊 Audio → ✍️ Transcript → 🔢 Embeddings → 🔍 Search → 🤖 Answer
Flow:
1) Extract audio
2) Transcribe audio
3) Split + clean text
4) Create embeddings
5) Store embeddings
6) Query via cosine similarity
7) Combine top chunks with the question
8) Feed into the LLM
9) Return contextual answer


## 📌 Example Prompt:
python process_incoming.py "What is Flexbox? Explain like I am a beginner."

# output example:
Flexbox is a CSS layout system that helps you arrange items in a row or column without fighting with margins and positioning.


## 🌟 Future Improvements:
Add UI (Streamlit / Flask)
Add PDF support
Add chunk summaries
Add GPU acceleration for faster Whisper processing
Add vector store options (FAISS, ChromaDB)


## 🤝 Contributing:
Pull requests are welcome!
Feel free to fork the repo and improve any stage of the pipeline.


## 🛡️ License:
MIT License.



