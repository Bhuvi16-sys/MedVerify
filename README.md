# MedVerify

MedVerify is a hackathon-ready medicine verification app for the SWASTHYA theme.
It provides OCR-based strip scanning, authenticity lookup, Hindi voice guidance,
interaction risk checks, and a counterfeit trend heatmap.

## Screenshots

| Home | Scan | Result | Heatmap |
|------|------|--------|---------|
| ![Home](docs/screenshot-home.png) | ![Scan](docs/screenshot-scan.png) | ![Result](docs/screenshot-result.png) | ![Heatmap](docs/screenshot-heatmap.png) |

## Demo

> 🎥 [Watch demo video](#) — replace this link with your YouTube/Loom URL

## Quick Start

```bash
# Backend
cd backend && npm install && npm run import:data -- data/1mgData.csv "data/All Drugs Ceiling Prices.csv" data/jan_aushadhi.csv && npm run dev

# Frontend
cd frontend && npm install && npm run dev
Team Roles
Person 1: Backend API, MongoDB data pipeline, AI logic, endpoint contracts
Person 2: Frontend scan/OCR/result flow, interaction UI, voice and camera UX
Person 3: PWA, heatmap, deployment, live demo flow, backup recording
Tech Stack
Frontend: React + Vite + Tesseract.js + Leaflet + vite-plugin-pwa
Backend: Node.js + Express + MongoDB + Google Gemini API
Project Structure
frontend/: React app and PWA surface
backend/: API server, Mongo models, CSV import script
Local Setup
1) Backend
Open terminal in backend folder.
Create backend/.env using backend/.env.example.
Install packages:
bash


npm install
Add the required CSV files in backend/data/:
1mgData.csv
All Drugs Ceiling Prices.csv
jan_aushadhi.csv No raw text files are needed for the import flow.
Import data:
bash


npm run import:data -- data/1mgData.csv "data/All Drugs Ceiling Prices.csv" data/jan_aushadhi.csv
Start backend:
bash


npm run dev
2) Frontend
Open terminal in frontend folder.
Set frontend/.env:
env


VITE_API_URL=http://localhost:5000
Install and run:
bash


npm install
npm run dev
Open app at http://localhost:5173
API Endpoints
GET /api/verify?name=Metformin
POST /api/scan-log
POST /api/interactions
GET /api/heatmap
PWA and Android Testing
Build frontend:
bash


npm run build
For live mobile tests, deploy backend to Render and frontend to Vercel.
Set frontend env on Vercel:
VITE_API_URL=https://your-render-url.onrender.com
Test "Add to Home Screen" from Android Chrome.
Validate full flow on at least 3 Android devices.
Deployment Checklist
Backend (Render)
Root directory: backend
Build command: npm install
Start command: node server.js
Environment variables:
MONGO_URI
GEMINI_API_KEY
GEMINI_MODEL=gemini-2.0-flash
PORT=5000
Frontend (Vercel)
Root directory: frontend
Environment variables:
VITE_API_URL=https://your-render-url.onrender.com
Demo Flow (Stage)
Scan a genuine strip and show green result + Hindi voice.
Scan a risky/expired strip and show alert card.
Open heatmap and pause for 3 seconds.
Close with: "This data did not exist before MedVerify."
Required Screenshots For Judges
Home scan screen
OCR result card (green state)
Alert card (red/yellow state)
Heatmap screen
PWA install prompt / home icon
Live URLs
Backend (Render): https://your-render-url.onrender.com
Frontend (Vercel): https://your-vercel-url.vercel.app

