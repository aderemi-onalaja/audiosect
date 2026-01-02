# Audiosect — Project Summary

This document captures the iterative build process of **Audiosect**, a tool that converts long-form text into clean, listenable audio chapters with a minimal, Apple-style UI.  
This file will be appended to daily as the project evolves.

---

## Goal
Create a lightweight, low-friction tool to help with study and revision by:
- Turning large text inputs into structured audio sections
- Producing high-quality, downloadable audio
- Keeping the UX calm, minimal, and non-distracting
- Allowing optional sign-in without blocking first-time use

Primary user: **exam study / revision**.

---

## Iteration Summary (to date)

### 1. Initial Concept
- Paste long text → AI sections → audio per section
- Card-based UI showing section title, summary, and audio player
- Focus on clarity and listenability rather than “podcast” polish

### 2. Early TTS Challenges
- Explored multiple TTS options (ElevenLabs, Web Speech API, local TTS)
- Local TTS (Piper) proved unsuitable for a Lovable-only workflow
- Web Speech API lacked downloadable audio and persistence

### 3. Final TTS Direction (Current)
- **Google Cloud Text-to-Speech** integrated via Lovable Edge Functions
- UK voices selected for clarity and neutrality (exam-friendly)
- Audio generated per section with internal chunking when needed
- Seamless playback even when sections are chunked

### 4. Audio UX Improvements
- Real audio players with progress bars
- Correct total duration displayed per section
- Minimal icon-only download control
- Internal chunking hidden from main UI
- Optional collapsible view for audio parts (fallback only)

### 5. Persistence & Accounts
- **Google Sign-In via Supabase Auth**
- Audio and documents saved per user
- Library view introduced:
  - Documents shown as cards
  - Click-through to section/audio view
- Audio stored in Supabase Storage with secure access

### 6. Guest Mode vs Signed-In Users
- Guests can use the tool without signing in
- Guest limits introduced to reduce cost and encourage sign-in:
  - Lower word limit
  - No saved library
  - Audio clears on refresh
- Signed-in users unlock:
  - Higher word limit
  - Saved audio library
  - Revisit and download audio later

### 7. UI & UX Polish
- Removed redundant word count displays
- Single compact word/character indicator
- Clean sign-in landing page with “Continue as guest” option
- Inline, non-intrusive prompts for sign-in when useful
- No aggressive modals or forced auth

---

## Current State
- End-to-end flow works reliably
- Audio quality is clear and suitable for study
- UX is minimal and calm
- System scales to ~3,000 word inputs comfortably
- Project is stable enough for daily personal use

---

## Next (Future Entries)
- Performance optimisations
- Voice/speed “study mode”
- Search and organisation in library
- Cost monitoring and optimisation
- Mobile UX refinements

---

_Last updated: Day 1_
