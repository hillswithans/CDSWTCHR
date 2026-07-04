# CDSWTCHR (CodeSwitcher)

### Asynchronous, Zero-Nag Workflow Infrastructure & Priority Router

- **Live Link:** https://cdswtchr-1033524947512.us-west1.run.app/
- **Status:** Live Production | Monitored via continuous dogfooding validation

---

## 👾 Why I Built This: The Anti-“Tamagotchi” Approach

Most modern task apps treat you like an irresponsible kid looking after a digital pet. They force you into useless data entry rituals—tagging, color-coding, scheduling—before you’ve even had the chance to think.

Then, if you miss a deadline, they punish you with streak loss or a screen full of passive-aggressive reminders.

CDSWTCHR does the opposite.

Built out of pure frustration with rigid, cartoonish time-blocking systems, it runs on one rule:

**Focus first, log it later.**

It’s designed to be a stress-free notebook for actual human attention—messy, nonlinear, and occasionally brilliant at inconvenient times. You stay in control of your data, and nothing in the system judges your schedule.

---

## 🎲 Product Positioning & State Architecture

Most task systems quietly assume you’re managing a team, a hierarchy, or a version of yourself that enjoys planning spreadsheets at 8pm.

This doesn’t.

CDSWTCHR is a passive, asynchronous workflow ledger built around:

- A **bounded priority grid** designed for solo operators
- **Retroactive time logging** instead of upfront planning theatre
- Flexible micro-focus intervals (15 / 20 / 25 min)
- Decoupled task states that don’t collapse when reality gets messy (as it tends to do)

It doesn’t try to control your workflow. It just stops it from turning into noise.

---

## 🧰 How It Works

### 1. The Bounded Priority Grid

A simple spatial system that stops everything from shouting “urgent” at the same volume.

- **Q1:** next 48 hours  
- **Q2:** this week  
- Trello-style columns without the managerial overhead
- Built for solo operators (no “just delegate it” fantasy layer)

---

### 2. Frictionless Ingestion

Because stopping your flow just to write a perfect task description is… not the move.

- **AI Photo Reader:** turns sticky notes, whiteboards, and chaotic screenshots into structured tasks
- **Voice Memos:** speak → transcribe → AI parses → inbox staging for review

---

### 3. Built-In Accessibility

Not bolted on after the fact. Actually designed in.

- High-contrast monochrome mode for clarity and reduced fatigue  
- Dyslexia-aware typography with tuned spacing and weight  
- Reduced visual clutter so nothing competes for attention

---

## ✋ App Limits & Privacy Boundaries

These aren’t arbitrary constraints. They keep the system fast, stable, and quietly sane at scale.

- **30-second voice cap** on live memos  
- **No raw audio uploads** (keeps backend lean and predictable)  
- **72-hour auto-delete** for all raw photos and voice clips  

The system is built to forget things quickly on purpose.

---

## ☁️ Tech Stack

- **Where it lives:** Google Cloud Run (containerized, auto-scaling)
- **AI engine:** Google AI Studio ecosystem (minimal middleware, faster iteration)

---

## 🔜 What’s Next (1-Week Focus)

No feature creep. Just refinement and stability.

- **Target Release:** July 8, 2026  
- Improved audio feedback systems  
- Accessibility visual refinement pass  
- Cross-device audio state syncing (desktop ↔ mobile)  
- Better resilience for messy inputs (bad handwriting, low-quality audio, real-world chaos)

---

## 🔄 Revision History & Changelog

![demo](assets/demo-nebula.gif)

---

### July 3, 2026 — Layout & Interaction Refinement

**UI Simplification**
- Stripped heavy container framing from header modules
- Replaced with lightweight, borderless icon interactions
- Reduced visual density without losing function

**Header Restructure**
- Aligned real-time clock with “Pair Devices” on a single axis
- Collapsed full timestamp into a hover-reveal micro interaction

**Focus Engine Compression**
- Merged focus label + countdown into one cohesive module
- Grouped controls into a compact media-style cluster
- Reduced vertical footprint by ~35%

**Voice Capture Expansion**
- Expanded active recording surface for better interaction fidelity
- Reduced padding to maximize usable input space

**Accessibility + Audio Systems**
- High-luminance theme override for accessibility mode
- Improved dyslexia readability via spacing + weight tuning
- Conditional UI mounting removes redundant controls in accessibility state
- TTS engine isolated from rendering lifecycle to prevent accidental triggers
- Migrated from browser TTS to cloud-based multilingual voice system
- Added localized voice support: EN / ES / FR / PT / HI

---

### July 2, 2026 — Accessibility & Voice Engine Upgrade

**Visual System**
- Introduced high-contrast accent system (`#00A3FF`)
- Added explicit “A” accessibility glyph for instant recognition
- Dynamic contrast recalculation across theme states
- Improved layout stability under scaling

**Voice System**
- Play/pause controls for memo playback
- System voice cues:
  - Recording start / stop
  - Processing state
  - Successful ingestion
  - Task removal feedback
- Inline audio previews for AI-parsed tasks
- Unified translation schema across UI + audio metadata

---

### June 23, 2026 — Localization & Typography Controls

**Globalization**
- Added native Hindi support across core workflows
- Improved multilingual consistency across UI and audio systems

**Typography Controls**
- Header-level scaling (10pt–17pt range)
- Designed to avoid browser zoom distortion
- Supports both dense scanning and low-vision readability modes
