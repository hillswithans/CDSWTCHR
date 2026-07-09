# CDSWTCHR (CodeSwitcher)

## Asynchronous, Zero-Nag Workflow Infrastructure & Priority Router

**Live Application:** https://cdswtchr-1033524947512.us-west1.run.app/  
**Status:** Live Production | Validated through continuous dogfooding and workflow testing

---

# Why I Built This: The Anti-"Tamagotchi" Approach

Most modern productivity apps treat users like irresponsible caretakers of a digital pet.

They require endless setup rituals: tagging, color coding, scheduling, and organizing before any real work begins.

Then, when reality happens, they punish users with missed streaks, reminder overload, and increasingly aggressive notifications.

CDSWTCHR does the opposite.

Built from frustration with rigid productivity systems and artificial planning rituals, it follows one principle:

> **Focus first. Log it later.**

CDSWTCHR is designed as a stress-free workflow ledger for real human attention: messy, nonlinear, and occasionally brilliant at inconvenient times.

Users remain in control of their data. The system does not judge schedules or force productivity habits.

It simply reduces noise.

---

# Product Architecture & Workflow Philosophy

Most task systems assume users are managing teams, projects, or perfectly organized versions of themselves.

CDSWTCHR is built differently.

It is a passive, asynchronous workflow system centered around:

- A four-quadrant Eisenhower Decision Matrix instead of a single priority score
- Retroactive time logging instead of forced upfront planning
- Flexible focus sessions instead of rigid scheduling
- Decoupled task states that remain stable when reality becomes unpredictable

The goal is not to control workflow.

The goal is to prevent workflow from becoming noise.

---

# Core Features

## 1. Eisenhower Priority Matrix

Tasks are organized by urgency and importance.

### Q1: Urgent & Important — Do First

High-impact tasks requiring immediate attention.

Examples:
- System outages
- Critical deadlines
- Emergency issues

### Q2: Important, Not Urgent — Plan

Long-term growth and strategic work.

Examples:
- Learning new skills
- Exercise
- Long-term projects

### Q3: Urgent, Not Important — Minimize

Interruptions that feel urgent but do not align with priorities.

Examples:
- Non-essential meetings
- Routine requests
- Administrative noise

### Q4: Neither — Eliminate

Low-value activities consuming time and energy.

Examples:
- Busywork
- Excessive organization
- Low-value tasks

### Backlog Capture

A staging area for quick inputs.

Tasks captured through voice or images are not forced into a category immediately. Users decide placement when they are ready.

---

# Frictionless Task Ingestion

CDSWTCHR removes the need to stop working just to create a perfectly formatted task.

## AI Photo Reader

Transforms:

- Sticky notes
- Whiteboards
- Screenshots
- Handwritten notes

into structured tasks.

## Voice Memo Capture

Users can speak naturally.

The system:

1. Records input
2. Transcribes speech
3. Uses AI processing to structure tasks
4. Places results into an inbox for review

---

# Voice, Localization & Accessibility

## Multilingual Audio System

CDSWTCHR uses cloud-based multilingual text-to-speech with Gemini-powered voice generation.

Features:

- Natural voice cadence tuning
- Localized task announcements
- Audio workflow feedback
- Language-specific voice handling

Supported languages:

- English
- Spanish
- French
- Portuguese
- Hindi
- Arabic
- German
- Italian

Arabic includes native RTL support.

---

# Advanced Streaming TTS Engine

The audio system was redesigned in:

`src/lib/audioManager.ts`

to implement sequential streaming playback.

## Zero Initial Latency

Audio begins immediately after the first chunk is fetched and decoded.

Additional chunks load asynchronously in the background.

## Precise Playback Scheduling

Future audio segments are scheduled through the Web Audio API timeline to maintain smooth, gapless playback.

## Click Prevention

Each chunk applies a short 5ms fade-in and fade-out transition to prevent audio artifacts between segments.

## Robust Cancellation

Playback uses:

- `activeCallToken`
- `AbortController`

When interrupted:

- Pending fetch requests are cancelled
- Scheduled audio nodes are cleared
- Current playback stops immediately

## Error Recovery

If a streaming chunk fails:

- Playback stops gracefully
- Successful audio remains preserved
- The system avoids unnecessary full fallback behavior

---

# Focus Timer

An integrated execution system for completing tasks.

Features:

- Default 25-minute focus sessions
- Adjustable 15 and 20-minute sessions
- 5-minute recovery breaks
- Voice announcements for:
  - Session start
  - Break periods
  - Completion states

Users can execute tasks without constantly monitoring the screen.

---

# Analytics Dashboard

CDSWTCHR includes productivity analysis tools.

Features:

- Daily performance ratios
- Historical completion tracking
- Focus session analysis
- Productivity trend visualization

---

# 48-Hour Auto Archive System

Completed tasks remain visible temporarily for review.

After 48 hours:

- Tasks move automatically into chronological Cycle Archives
- Active boards remain focused
- Completion history remains available

---

# Accessibility System

Accessibility was designed into the foundation rather than added afterward.

Features:

- High-contrast monochrome mode
- Dynamic contrast recalculation
- Dyslexia-aware typography adjustments
- Adjustable header typography scaling (10pt–17pt)
- Reduced visual clutter
- Screen-reader-friendly workflows

---

# Application Limits & Privacy Boundaries

CDSWTCHR intentionally limits stored raw inputs.

Constraints:

- 30-second maximum voice memo length
- No raw audio uploads
- Raw photos and voice clips automatically deleted after 72 hours

The system is designed to remember what matters and forget what does not.

---

# Technical Stack

## Deployment

- Google Cloud Run
- Containerized deployment
- Auto-scaling infrastructure

## AI Platform

- Google AI Studio ecosystem

## Application Systems

- Interactive drag-and-drop workflow board
- Localization framework
- Audio lifecycle management
- Analytics visualization systems

---

# Release Milestones & Changelog

![demo](assets/demo-nebula.gif)

## July 8, 2026 — Localization Expansion & Feedback Infrastructure

### Globalization Expansion

- Added full German (`de`) localization support across core workflows
- Added full Italian (`it`) localization support across UI components and datetime formatting
- Expanded multilingual consistency across task management, analytics, and audio systems

### Feedback System Integration

- Added in-app feedback submission workflow powered by Tally
- Integrated dedicated feedback access directly into application navigation
- Created a streamlined method for collecting user input without interrupting workflow

### Product Refinement

- Continued improving CDSWTCHR as a globally accessible productivity system
- Improved communication between users and ongoing development

---

## July 3, 2026 — Layout & Interaction Refinement

### UI Simplification

- Removed heavy container framing from header modules
- Replaced dense layouts with lightweight interactions
- Reduced visual density while preserving functionality

### Header Restructure

- Aligned real-time clock with Pair Devices controls
- Converted timestamp display into hover-based micro interaction

### Focus Engine Improvements

- Combined focus label and countdown into one module
- Reduced vertical footprint by approximately 35%

### Voice Capture Expansion

- Increased recording interaction surface
- Improved input accessibility

### Audio & Accessibility Improvements

- Added high-luminance accessibility theme
- Improved dyslexia readability through spacing and weight adjustments
- Isolated TTS engine from rendering lifecycle
- Migrated from browser speech synthesis to cloud multilingual voice generation

---

## July 2, 2026 — Accessibility & Voice Engine Upgrade

### Visual System

- Added accessibility indicator
- Added dynamic accent handling
- Improved layout stability under scaling

### Voice System

- Added playback controls
- Added recording and processing voice cues
- Added inline AI task audio previews
- Unified translation schema across UI and audio metadata

---

## June 23, 2026 — Localization & Typography Controls

### Globalization

- Added Hindi language support
- Improved multilingual consistency across workflows

### Typography

- Added header-level scaling controls
- Improved readability across accessibility modes

---

# Current Development Focus

## July 2026 Refinement Goals

Focus remains on stability, accessibility, and refinement.

Upcoming improvements:

- Improved audio feedback systems
- Accessibility visual refinement
- Cross-device audio state synchronization
- Better resilience for messy inputs:
  - Poor handwriting
  - Low-quality audio
  - Real-world notes and interruptions

---

# Feedback

A dedicated feedback submission workflow is available inside the application.

Feedback platform:

https://tally.so/r/vGb88X
