# AEGIS — Forensic Command Center

AES-256 encrypted investigation platform: autopsy records, evidence RAG search, case timelines, movement traces, and AI copilot.

**Repo:** [github.com/Athina09/Hacksprint6.0](https://github.com/Athina09/Hacksprint6.0)

## Quick start

```bash
# Frontend
npm install
npm run dev
# → http://localhost:8080/

# Backend (separate terminal)
cd backend
python3 -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
cp ../.env.example ../.env  # set DATABASE_ENCRYPTION_KEY
uvicorn main:app --host 127.0.0.1 --port 8000 --reload
# → http://127.0.0.1:8000/docs
```

Or start everything together:

```bash
npm run dev:all
```

| Service | URL |
|---------|-----|
| AEGIS UI | http://localhost:8080/ |
| API | http://127.0.0.1:8000 |
| API docs | http://127.0.0.1:8000/docs |
| RAG dashboard | http://localhost:8501 (when Streamlit is running) |

## What's included

| Area | Details |
|------|---------|
| **Command Center** | Stats, risk map, live feed, case table |
| **Cases** | Investigation graph, hypotheses, autopsy panel, timeline |
| **Copilot** | Vector evidence search over encrypted index |
| **Heatmap / Alerts / Reports** | Investigation support views |
| **Settings** | AES-256 encryption status |
| **Backend** | FastAPI + encrypted stores (`autopsies`, `evidence`, `timelines`, `movement`) |

## Encryption

All database files are encrypted at rest with **AES-256-GCM**. Set `DATABASE_ENCRYPTION_KEY` in `.env` (32+ character secret). See [backend/README.md](./backend/README.md).

## Stack

React 19 · TanStack Router · Vite · Tailwind · FastAPI · cryptography (AES-256-GCM) · Streamlit RAG eval
