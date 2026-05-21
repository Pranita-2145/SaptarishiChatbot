# Shaastra Samvad AI — RAG Chatbot
A modern AI-powered RAG (Retrieval-Augmented Generation) chatbot built for the industry project of Shaastra Samvad.

This chatbot uses:

Next.js for frontend
FastAPI for backend
Groq Llama 3.3 as LLM
ChromaDB as vector database
HuggingFace Embeddings
LangChain for RAG pipeline

The chatbot provides contextual answers based on uploaded knowledge documents related to:

Saptarishis
Vedic wisdom
Ramayana
Mahabharata
Ancient Indian knowledge systems
Features
ChatGPT-style UI
RAG-based semantic retrieval
Groq Llama 3.3 integration
Fast responses
Source-based answers
Modern responsive interface
Company-branded chatbot
Fully free AI stack (except internet usage)
Tech Stack
Layer	Technology
Frontend	Next.js + Tailwind CSS
Backend	FastAPI
LLM	Groq Llama 3.3
Embeddings	HuggingFace
Vector DB	ChromaDB
RAG Framework	LangChain
Project Structure
shaastra-rag-chatbot/
│
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── rag.py
│   │   ├── ingest.py
│   │   └── prompts.py
│   │
│   ├── data/
│   │   └── saptarishis.txt
│   │
│   ├── db/
│   ├── venv/
│   ├── .env
│   └── requirements.txt
│
├── frontend/
│   ├── src/
│   │   └── app/
│   │       ├── page.tsx
│   │       ├── globals.css
│   │       └── layout.tsx
│   │
│   ├── package.json
│   └── ...
│
└── README.md
Setup Instructions
1. Clone Project
git clone <your_repo_url>
cd shaastra-rag-chatbot
2. Backend Setup

Go to backend folder:

cd backend

Create virtual environment:

python -m venv venv

Activate virtual environment:

Windows
.\venv\Scripts\Activate
Mac/Linux
source venv/bin/activate

Install dependencies:

pip install -r requirements.txt
3. Create .env

Inside backend/, create:

.env

Add:

GROQ_API_KEY=your_groq_api_key
4. Get Groq API Key
Visit:

Groq Console

Sign up/login
Create API key
Copy key into .env
5. Create Embeddings

Inside backend folder run:

python app/ingest.py

This creates:

embeddings
vector database
semantic retrieval index
6. Start Backend
uvicorn app.main:app --reload

Backend runs on:

http://127.0.0.1:8000

Swagger docs:

http://127.0.0.1:8000/docs
7. Frontend Setup

Open new terminal.

Go to frontend:

cd frontend

Install packages:

npm install

Run frontend:

npm run dev

Frontend runs on:

http://localhost:3000
Running the Project

You must run BOTH:

Terminal	Command
Backend	uvicorn app.main:app --reload
Frontend	npm run dev
RAG Workflow
User Query
     ↓
Semantic Search (ChromaDB)
     ↓
Relevant Context Retrieval
     ↓
Groq Llama 3.3
     ↓
Final AI Response
How RAG Works
Documents are converted into embeddings.
Embeddings are stored in ChromaDB.
User query is converted into vector embedding.
Similar chunks are retrieved.
Retrieved context is sent to LLM.
LLM generates contextual response.
Example Questions
Who is Atri Rishi?
Explain Saptarishis
Stories from Mahabharata
Explain Vedic wisdom
Tell me about Kashyap Rishi
API Endpoints
Root Endpoint
GET /

Response:

{
  "message": "Shaastra Samvad AI Backend Running"
}
Chat Endpoint
POST /chat

Request:

{
  "message": "Who is Atri Rishi?"
}

Response:

{
  "answer": "...",
  "sources": ["source1"]
}
Important Notes
Keep db/ folder safe. It stores embeddings.
Internet connection is required for Groq API.
Backend must run before frontend.
.env file should NOT be uploaded publicly.
Future Improvements
PDF upload support
Voice chatbot
Streaming responses
Authentication
Deployment on cloud
Multi-document support
Chat history
Better citations
Author

Developed as an industry internship project for:

Shaastra Samvad

Using modern RAG architecture and open-source AI technologies.
