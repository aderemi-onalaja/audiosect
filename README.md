# Audiosect
**AI Sectioned Audio Reader**

A minimalist, Apple-esque web app that converts long text documents into intelligently sectioned audio chapters — optimised for listening, revision, and focus.

Unlike traditional text-to-speech tools that read everything as one continuous block, Audiosect uses AI to detect logical topic boundaries and generates structured audio sections, making long content easier to listen to, navigate, and revisit.

---

## ✨ What Audiosect Does

- Accepts long-form text via paste or file upload
- Uses AI to:
  - Analyse document structure
  - Detect semantic topic shifts
  - Create logical listening chapters
- Converts each chapter into high-quality audio
- Displays results as clean, playable cards
- Allows audio to be downloaded and revisited later

---

## 🧠 Key Differentiator

Most text-to-speech tools treat documents as a single blob.

**Audiosect treats documents like chapters — optimised for listening.**

Each section is intentional, navigable, and designed to stand on its own.

---

## 🖥️ Supported Inputs

- Paste text directly
- Upload files:
  - `.pdf`
  - `.docx`
  - `.txt`

---

## 🔊 Output Format

Each document is transformed into **multiple audio sections**.

Each section includes:
- Topic title (AI-generated)
- One-line summary
- Audio player with progress bar
- Accurate total duration
- Minimal download control (icon-only)

Internally, long sections may be chunked for reliability, but playback is presented as a single continuous experience wherever possible.

---

## 🎨 Design Philosophy

- Minimal  
- Calm  
- Apple-inspired  

No dashboards.  
No clutter.  
No unnecessary controls.

Think:
- Apple Notes  
- Apple Podcasts  
- macOS Utilities  

---

## 🚀 Core Features

### Content & Audio
- ✅ Paste text
- ✅ Upload documents
- ✅ AI topic sectioning
- ✅ High-quality UK English audio
- ✅ Clean, card-based playback UI
- ✅ Downloadable audio per section

### Accounts & Persistence
- ✅ Optional Google sign-in
- ✅ Guest mode (no sign-in required)
- ✅ Saved library for signed-in users
- ✅ Revisit audio at a later date

---

## 👤 Guest vs Signed-In Experience

### Guest Mode
Users can:
- Paste text
- Generate audio
- Listen immediately

With limitations:
- Lower word limit
- No saved library
- Audio cleared on refresh

### Signed-In Users
Unlock:
- Higher word limit
- Saved documents and audio
- Library view with document cards
- Persistent access and downloads

Sign-in is encouraged but never forced.

---

## 🧩 How AI Sectioning Works

The LLM:
- Detects headings when available
- Infers topic shifts when headings are missing
- Merges trivial sections
- Splits overly long sections
- Targets listenable chapter lengths

This ensures every section:
- Makes sense on its own
- Is easy to listen to
- Feels intentional

---

## 💡 Ideal Use Cases

- Study notes
- Exam revision
- Research papers
- Essays
- Contracts
- Long articles
- Meeting transcripts
- Reports and documentation

---

## 🛠️ Non-Goals (By Design)

Audiosect intentionally does **not** include:
- Social features
- Analytics dashboards
- Highlighting or annotation
- Collaboration tools
- Feature-heavy editors

This product is focused on **reading → listening → understanding**.

---

## 🔮 Future Extensions (Non-MVP)

- Additional voices
- Playback speed controls
- Section renaming
- Search and filtering in library
- Offline support
- iOS wrapper

---

## 📄 License

MIT
