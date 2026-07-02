# CDSWTCHR (CodeSwitcher)

### Asynchronous, Zero-Nag Workflow Infrastructure & Priority Router

*   **Live Link:** [https://cdswtchr-1033524947512.us-west1.run.app/](https://cdswtchr-1033524947512.us-west1.run.app/)
*   **Status:** Live Production | Monitored via continuous dogfooding validation

---

## 👾 Why I Built This: The Anti-“Tamagotchi” Approach

Most modern task apps treat you like an irresponsible kid looking after a digital pet. They force you to do a ton of useless data entry—making you tag, color-code, and schedule a task before you can even type it out. Then, if you miss a deadline, the app guilt-trips you by breaking your "streak" or flooding your screen with annoying reminders.

CDSWTCHR does the opposite. Built out of pure frustration with rigid, cartoonish time-blocking apps, this tool runs on a simple rule: **Focus first, log it later.** It is designed to be a simple, stress-free notebook that tracks your actual work retroactively. You stay in control of your data, and the app never judges your schedule.

---

## 🎲 Product Positioning & State Architecture

Unlike legacy task management software that relies heavily on behavioral policing, metric-shaming gamification, and rigid, immutable data frames, CDSWTCHR is architected as a passive, asynchronous workflow ledger. 

Standard frameworks—such as the traditional Eisenhower Matrix—mistakenly assume a multi-tiered corporate hierarchy built on delegation. CDSWTCHR intentionally guts this overhead, engineering a bounded priority grid optimized exclusively for a team of one. Rather than locking down parameters post-deadline or enforcing fixed, unyielding focus increments, the underlying application logic permits fully retroactive time logging and implements completely decoupleable, adaptive micro-focus intervals (15m, 20m, or 25m splits) to match the real-time cognitive bandwidth of the operator.

---

## 🧰 How It Works

### 1. The Bounded Priority Grid
Standard to-do lists get paralyzing because every single item looks equally important. This grid fixes that by breaking things down visually based on real time limits.
*   **Built for Solo Workers:** Standard matrices tell you to "delegate" tasks to other people. If you work alone, you can't do that. This app drops that entirely and splits your work into two simple buckets: Q1 (Next 48 Hours) and Q2 (This Week).
*   **Trello-Style Layout:** Tasks are deployed into clean spatial columns based on when they were made and how fast they need to get done, rather than who is doing them.

### 2. Frictionless Ingestion Modalities
You shouldn't have to stop working just to type out a massive description for a new task.
*   **AI Photo Reader:** Take a quick picture of messy handwriting on a sticky note, a whiteboard drawing, or a computer screenshot, and the AI will automatically turn it into clean text for your list.
*   **Voice Memos:** If you're busy or on the move, talk directly into the app to log a thought quickly (like "need to do laundry and change cat litter"). The app reads the core idea and drops it straight into your inbox for you to approve or edit later.

### 3. Built-In Color Blind & Dyslexia Modes
Accessibility shouldn't require downloading messy third-party browser extensions that break your screen layout.
*   **High-Contrast Monochrome:** Completely removes color dependencies so it's easy to read for anyone with color blindness.
*   **Legible Typography:** Uses weighted fonts and specific text spacing to prevent visual crowding and make reading smooth for users with dyslexia.

---

## ✋ App Limits & Privacy Boundaries

To keep cloud costs low and protect your private data, I built three strict limits directly into the system:
*   **30-Second Voice Limit:** Live voice notes cut off at exactly 30 seconds. This keeps the app fast, stops the server from getting bogged down, and keeps AI costs to a minimum.
*   **No Raw Audio File Uploads:** You cannot upload massive, multi-hour audio files (like a recorded Zoom meeting). The app only accepts live, short voice streams. This keeps the backend secure from broken code or heavy file payloads.
*   **72-Hour Auto-Delete:** The app automatically purges your raw photos and voice clips 72 hours after you upload them. People naturally drop sensitive info into AI tools, so deleting files quickly ensures your privacy stays protected and our cloud storage stays completely lean.

---

## ☰ The Tech Stack

*   **Where It Lives:** Deployed on Google Cloud Run. This environment runs the app inside lightweight containers and automatically scales up or down based on activity metrics.
*   **The AI Engine:** Leveraged the Google AI Studio ecosystem to minimize infrastructure middleware, maximizing development velocity and ensuring native compatibility with containerized deployment paths.

---

## 🔜 What's Next (The 3-Week Plan)

I want to avoid "feature creep" (adding endless tools until the app gets bloated). The next 3 weeks are all about refining the core UX bone structure and hardening backend stability:
*   **Target Production Release:** The updated app containing the new advanced audio feedback systems and accessibility visual refinements will officially publish on **July 8, 2026**.
*   **Active Ingestion Testing:** Continuous dogfooding of the live processing pipeline to optimize how robustly the AI engines handle heavily warped, multi-angle handwriting captures and muffled, low-fidelity audio recordings.
*   **Cross-Device Audio Syncing:** Polishing state serialization to ensure in-progress voice memo states and playback queue positions persist smoothly across desktop-to-mobile viewport handoffs.

---

## 🔄 Revision History & Changelog

![demo](assets/demo-nebula.gif)

### July 2, 2026
#### 🎨 Visual & Accessibility UI Architecture
*   **Colorblind-Friendly Accent:** Upgraded the primary highlight anchor to a vibrant, high-contrast neon blue (`#00A3FF`), structurally designed to ensure maximum visual distinction for operators navigating deuteranopia, protanopia, or tritanopia.
*   **Explicit Accessibility Identifier:** Integrated a prominent, centered typography **"A"** glyph directly inside the theme selection matrix, eliminating color-dependency guesswork and providing a universal visual lighthouse for accessibility panels.
*   **Dynamic Contrast Text Colors:** Refactored text rendering algorithms inside the theme selector nodes, forcing real-time background color calculations so interactive symbols maintain optimal contrast bounds regardless of the active theme accent.
*   **Responsive Pomodoro Container Flow:** Restructured flex-box wrapping and container styling under accessibility viewports to prevent layout squishing, allowing expansive task microcopy to wrap gracefully and handle scaling gracefully.

#### 🎙️ Advanced Audio & Voice Feedback Engine
*   **Granular Voice Memo Playback Controls:** Engineered fully interactive Play/Pause state tracking for recorded voice fragments, allowing operators to scrub, review, and audit audio payloads locally before executing AI pipeline processing.
*   **Dynamic Localization Vocal Cues:** Implemented native, fluid female text-to-speech system alerts across all five primary locales (EN, ES, FR, PT, HI) to provide real-time audio orientation for key system transitions:
    *   *Recording Start:* "Recording memo. Speak now."
    *   *Recording Stop:* "Recording saved."
    *   *AI Processing Ingestion:* "Processing your voice memo now."
    *   *Successful Ingest:* "Tasks successfully imported."
    *   *Context Purge:* "Task removed."
*   **Acoustic Read-Aloud Previews:** Injected targeted audio speaker nodes beside every AI-parsed task option within the ingestion preview layout, allowing operators to run point-and-click vocal reviews of text snippets before committing them to the database backlog.
*   **Translation Dictionary Unification:** Localized all newly deployed audio control metadata (including `'Play Memo'` and `'Read task aloud'`) and completely audited language configuration schemas to eliminate redundant property namespace collisions.

### June 23, 2026
#### 🌐 Global Localization Expansion (Hindi HI)
*   **Native Core Architecture Integration:** Integrated native Hindi language support across the entire app ecosystem. Recognizing Hindi as one of the most widely spoken languages globally—and a primary language for a massive demographic of international tech professionals—this update bridges a critical accessibility gap, ensuring intuitive navigation, localized time-blocking semantics, and accurate microcopy rendering.

#### 🔍 Dynamic Viewport Typography Scaling Toggle
*   **Header-Level Scaling Matrix:** Engineered an on-page text scaling toggle directly into the header workspace. Operators can dynamically scale page-specific typography between a 10pt minimum (for high-density matrix scanning) and a 17pt maximum (to alleviate visual fatigue and support low-vision or dyslexic users), bypassing rigid browser-level zoom configurations that disrupt layout grids.
