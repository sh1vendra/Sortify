# Sortify 🧠

An AI-powered document organization and retrieval platform that automatically categorizes academic files and enables semantic search through a RAG pipeline.

---

## What It Does

- **Automatic categorization** — Upload PDFs, lecture notes, or assignments and Sortify classifies them into relevant folders without manual sorting.
- **Semantic search** — Query your documents in natural language using vector embeddings and retrieval-augmented generation (RAG) to surface relevant content.
- **AI chat assistant** — Ask questions about your uploaded files and receive context-aware answers grounded in your actual documents.
- **Responsive dashboard** — Access, browse, and manage all organized documents from a clean, mobile-friendly interface.

---

## Screenshots

### Login Page
![Login Page](./sortify_app/public/loginpage.png)

### Dashboard View
![Dashboard View](./sortify_app/public/sortifyss1.png)

### Sortify Assistant
![Sortify Assistant](./sortify_app/public/sortifyss2.png)

---

## Tech Stack

| Layer | Technologies |
|:------|:-------------|
| Frontend | React, TypeScript, Vite, TailwindCSS |
| Backend | Python, FastAPI |
| Database | PostgreSQL, PGVector |
| AI / ML | RAG, Sentence Transformers, Vector Similarity Search |
| Infrastructure | Supabase, Node.js |
| Version Control | Git + GitHub |

---

## Architecture

The system follows a standard RAG pipeline. Uploaded documents are parsed, split into chunks, and converted into vector embeddings using Sentence Transformers. These embeddings are stored in PostgreSQL via the PGVector extension. When a user submits a query — either through search or the chat assistant — the query is embedded, matched against stored vectors using cosine similarity, and the top-matching chunks are passed as context to a language model to generate a grounded response. Document categorization runs as a background task on upload, assigning files to folders based on content analysis.

---

## My Contributions

**Shivendra Bhagat** — Frontend engineering across 3 sprints:

- Initialized the React + Vite project, established the codebase structure, and configured the build toolchain
- Designed and implemented the main dashboard layout, landing page UI components, and navigation structure
- Built the chatbot interface and integrated the trigger flow from the AI Search action on the dashboard
- Developed the user profile section and refactored it into smaller, reusable components
- Implemented responsive design across all views and tested layouts on multiple screen sizes
- Refactored and restructured CSS across the dashboard and landing page for maintainability
- Designed the project logo and branding assets
- Planned and implemented frontend unit tests using Vitest

---

## Getting Started

**Prerequisites:** Node.js, Python 3.11+

```bash
# Clone the repository
git clone https://github.com/sh1vendra/Sortify.git
cd sortify

# Frontend
cd sortify_app
npm install
npm run dev                # → http://localhost:3000

# Backend (separate terminal)
cd embedding
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn app:app --reload   # → http://localhost:8000
```

**Environment variables** — Create `embedding/.env` with:
```
GOOGLE_API_KEY=<your-key>
SUPABASE_URL=<your-url>
SUPABASE_KEY=<your-key>
```
