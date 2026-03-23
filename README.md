# ComicCraft AI 🎨

> **Turn any story idea into a comic strip — instantly.**

ComicCraft AI is a generative AI-powered platform that transforms a user's story prompt into a fully structured comic strip — complete with consistent characters, genre-specific panel artwork, dialogue with speech bubbles, and a downloadable storyboard PDF.

---

## 🚀 The Problem

Millions of aspiring comic creators, educators, and students have compelling stories but lack the drawing skills or tight budget for professional tools. Existing AI image generators produce isolated visuals with no narrative continuity, character consistency, or structured panel flow.

**ComicCraft AI bridges this gap.**

---

## ✨ Features

| Feature | Description |
|---|---|
| 📝 Story prompt input | Plain text in any language — describe your story naturally |
| 🎭 Genre selector | Manga, superhero, fantasy, horror, slice-of-life and more |
| 👤 Character consistency | Same characters look identical across all panels |
| 💬 Dialogue & speech bubbles | Auto-placed with correct character attribution |
| 📄 PDF storyboard export | Print-ready output with panels, dialogue and scene notes |

---

## 🧠 How It Works

ComicCraft AI uses a **two-stage generative pipeline**:

### Stage 1 — Script Generation (Gemini 1.5 Flash)
- Parses the user's story prompt and genre selection
- Generates a full comic script: named characters with reusable visual descriptors, panel-by-panel narrative, dialogue, and scene composition notes
- Builds **character anchors** — detailed visual descriptions embedded into every subsequent image prompt to maintain consistency

### Stage 2 — Panel Rendering (Stable Diffusion XL)
- Each panel is rendered using character-anchored prompts
- Ensures visual continuity of characters across all panels
- Genre-specific style guidance applied per render

### Output Assembly (ReportLab)
- Panels assembled into a PDF storyboard
- Dialogue overlaid with speech bubble placement
- Scene notes and production details included

```
User Prompt + Genre
        │
        ▼
┌─────────────────────┐
│  Gemini 1.5 Flash   │  ← Stage 1: Script + Character Anchors
└─────────────────────┘
        │
        ▼
┌─────────────────────┐
│  Stable Diffusion XL│  ← Stage 2: Panel Image Rendering
└─────────────────────┘
        │
        ▼
┌─────────────────────┐
│  ReportLab PDF      │  ← Output: Storyboard PDF
└─────────────────────┘
```

---

## 🛠️ Tech Stack

> **100% free and open-source — zero cost to deploy**

| Layer | Technology | Purpose |
|---|---|---|
| AI / LLM | Google Gemini 1.5 Flash | Script, dialogue & character anchor generation |
| Image Generation | Stable Diffusion XL (Hugging Face) | Panel rendering with character-consistent prompts |
| Frontend | React | User interface — prompt input & comic preview |
| Backend | Python / FastAPI | Pipeline orchestration & API handling |
| PDF Assembly | ReportLab | Storyboard PDF with panels & dialogue |
| Hosting | Vercel + Render | Frontend & backend deployment (free tier) |

---

## 📁 Project Structure

```
comiccraft-ai/
├── backend/
│   ├── main.py              # FastAPI app entry point
│   ├── script_gen.py        # Gemini 1.5 Flash comic script generator
│   ├── character_anchor.py  # Character visual descriptor builder
│   ├── image_gen.py         # Stable Diffusion XL panel renderer
│   └── pdf_builder.py       # ReportLab storyboard PDF assembler
├── frontend/
│   └── src/
│       ├── App.jsx
│       ├── StoryInput.jsx   # Prompt + genre selector UI
│       └── ComicPreview.jsx # Panel grid + PDF download
├── requirements.txt
├── package.json
└── README.md
```

---

## ⚙️ Setup & Installation

### Prerequisites
- Python 3.10+
- Node.js 18+
- Google AI Studio API key (free) — [aistudio.google.com](https://aistudio.google.com)
- Hugging Face API token (free) — [huggingface.co](https://huggingface.co)

### Backend

```bash
# Clone the repository
git clone https://github.com/[your-username]/comiccraft-ai
cd comiccraft-ai/backend

# Install dependencies
pip install -r requirements.txt

# Set environment variables
export GEMINI_API_KEY=your_gemini_api_key
export HF_API_TOKEN=your_huggingface_token

# Run the server
uvicorn main:app --reload
```

### Frontend

```bash
cd frontend
npm install
npm start
```

---

## 🔑 Getting Free API Keys

**Gemini 1.5 Flash (Google AI Studio)**
1. Visit [aistudio.google.com](https://aistudio.google.com)
2. Sign in with your Google account
3. Click "Get API key" — no credit card required

**Stable Diffusion XL (Hugging Face)**
1. Visit [huggingface.co](https://huggingface.co) and create a free account
2. Go to Settings → Access Tokens
3. Create a new token — free tier gives ~1000 image calls/month

---

## 🎯 Use Cases

- 🎓 **Students** — Visualize essays, history, and science as comic strips
- ✏️ **Indie creators** — Prototype story ideas without hiring an artist
- 👩‍🏫 **Teachers** — Create engaging comic-based learning material
- 📱 **Content creators** — Generate social media comic strips at scale
- 🌍 **Regional storytellers** — Tell stories in local languages and styles
- 🏢 **Agencies** — Rapid storyboard prototyping for pitches|

---

## 📄 License

MIT License — free to use, modify and distribute.

---

> *"ComicCraft AI — Because every story deserves to be seen."*
