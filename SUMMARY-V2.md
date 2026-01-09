# Audiosect — Conception to Live (January 9)

## Overview

Audiosect was conceived as a focused utility: a fast, minimal way to turn long-form text into short, listenable audio sections.

The guiding principle from day one was **clarity over cleverness** — a tool that removes friction for reading-heavy users without introducing dashboards, feeds, or configuration overhead.

Target users identified early:
- Students
- Healthcare professionals
- Knowledge workers dealing with long documents

---

## Phase 1 — Core Idea & Validation

**Problem observed**

People want to consume long text (articles, notes, reports, research papers) while walking, commuting, or resting — but existing text-to-speech tools are:
- overly linear
- poorly structured
- heavy with controls and setup

**Key insight**

Splitting text into **short, meaningful sections** dramatically improves:
- listenability
- navigation
- reusability

This led to the core concept:

> **Audio + Sections = Audiosect**

---

## Phase 2 — Product Definition

Early product decisions that shaped Audiosect:

- One primary action: **Paste or upload text → generate audio**
- No playlists, feeds, or discovery layer
- No manual chaptering or editing
- Audio generated as **sections**, not rigid “chapters”
- Minimal, calm UI inspired by Apple utilities

### Language decisions

Canonical headline:
> **Turn text into audio**

Supporting explanation:
> *Paste or upload text to generate short, listenable audio sections.*

Deliberately avoided terms:
- chapters
- snippets
- summaries

(to prevent confusion and feature creep)

---

## Phase 3 — Guest vs Signed-In Model

Audiosect launched with a **guest-first experience** to reduce onboarding friction.

### Guest users
- Can generate audio up to **500 words**
- Can listen immediately
- No downloads
- No saved library

### Signed-in users
- Tiered limits (up to 5,000+ words)
- Unlimited audio sections
- Downloadable audio
- Saved audio library
- Persistent access across sessions

This balances:
- Immediate value
- Clear upgrade incentive
- No forced sign-up wall

---

## Phase 4 — Technical Architecture

Audiosect is intentionally simple in architecture to maximise reliability and iteration speed.

### Frontend
- Built using **Lovable**
- Single-page application with route-level auth guards
- `/` is state-aware:
  - Guest users see guest experience
  - Signed-in users see saved audio/projects
- Public routes:
  - `/`
  - `/about`
  - `/pricing`
  - `/privacy`
  - `/terms`
- Auth route:
  - `/auth`

### Authentication
- **Lovable Cloud Auth**
- Supported methods:
  - Google OAuth
  - Email / password
- Apple sign-in temporarily disabled to reduce surface area
- Custom auth email templates not supported (confirmed limitation)
- Auth state determines UI, not routing (single-route, state-aware model)

### APIs & AI
- **LLM** used to:
  - Analyse document structure
  - Detect semantic topic shifts
  - Merge trivial sections
  - Split overly long sections
- **Text-to-Speech API** used to:
  - Generate audio per section
  - Produce independent audio files for each section
- Audio metadata includes section titles to support:
  - iOS lock screen playback
  - Notification / Now Playing contexts

### Data & Storage
- Managed database (Lovable Cloud–backed)
- Stores:
  - User accounts
  - Generated audio metadata
  - Section titles and summaries
- Audio files stored and retrieved via managed object storage
- No external Supabase project currently used in production

### Playback
- Audio rendered as **card-based UI**
- Each section:
  - Has its own player
  - Can be expanded to show full summary
- Background playback supported

---

## Phase 5 — UX Iteration & Clarity

Heavy iteration focused on **first-time comprehension**.

Key improvements:
- Simplified CTA to **“Generate”**
- Removed redundant helper copy
- Repositioned **“Try an example”** close to the text input
- Unified language across:
  - Guest view
  - Auth screen
  - Signed-in experience
- Footer navigation added:
  - About · Pricing · Privacy · Terms
- Logo made globally clickable to return users to `/`

---

## Phase 6 — Compliance & Public Readiness

To support Google OAuth and public beta:

- Public homepage enabled (no forced auth redirect)
- Privacy Policy and Terms of Service added
- Footer links visible without sign-in
- OAuth consent screen branded as **Audiosect**
- Authorised domains configured:
  - audiosect.com
  - audiosect.lovable.app
  - internal auth domains as required

---

## Current State (January 9)

Audiosect is now:
- Live
- Stable
- Understandable to non-technical users
- Mobile-friendly
- Ready for public beta testing

The product intentionally remains:
- Narrow in scope
- Opinionated in UX
- Light on configuration

---

## Next Focus Areas

- Case studies (students, healthcare professionals)
- SEO content (pillar page + blog posts)
- Monetisation (credits + subscription, hidden initially)
- Android playback notification parity
- Public beta onboarding feedback

---

**Status**

> From concept to a functioning, user-tested product — without losing simplicity.
