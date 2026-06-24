# CDSWTCHR (CodeSwitcher)
### Asynchronous, Zero-Nag Workflow Infrastructure & Priority Router

**Live Link:** https://cdswtchr-1033524947512.us-west1.run.app/  
**Status:** Live Production | Monitored via continuous dogfooding validation

---

## 👾 Why I Built This: The Anti-“Tamagotchi” Approach

Most modern task apps treat you like an irresponsible kid looking after a digital pet. They force you to do a ton of useless data entry—making you tag, color-code, and schedule a task before you can even type it out. Then, if you miss a deadline, the app guilt-trips you by breaking your "streak" or flooding your screen with annoying reminders.

`CDSWTCHR` does the opposite. Built out of pure frustration with rigid, cartoonish time-blocking apps, this tool runs on a simple rule: **Focus first, log it later.** It is designed to be a simple, stress-free notebook that tracks your actual work retroactively. You stay in control of your data, and the app never judges your schedule.

### 🎲 Product Positioning & State Architecture

Unlike legacy task management software that relies heavily on behavioral policing, metric-shaming gamification, and rigid, immutable data frames, CDSWTCHR is architected as a passive, asynchronous workflow ledger. Standard frameworks—such as the traditional Eisenhower Matrix—mistakenly assume a multi-tiered corporate hierarchy built on delegation. CDSWTCHR intentionally guts this overhead, engineering a bounded priority grid optimized exclusively for a team of one. Rather than locking down parameters post-deadline or enforcing fixed, unyielding focus increments, the underlying application logic permits fully retroactive time logging and implements completely decoupleable, adaptive micro-focus intervals (15m, 20m, or 25m splits) to match the real-time cognitive bandwidth of the operator.

---

## 🧰 How It Works

### 1. The Bounded Priority Grid
Standard to-do lists get paralyzing because every single item looks equally important. This grid fixes that by breaking things down visually based on real time limits.
* **Built for Solo Workers:** Standard matrices tell you to "delegate" tasks to other people. If you work alone, you can't do that. This app drops that entirely and splits your work into two simple buckets: **Q1 (Next 48 Hours)** and **Q2 (This Week)**.
* **Trello-Style Layout:** Tasks are deployed into clean spatial columns based on when they were made and how fast they need to get done, rather than who is doing them.

### 2. Easy Ways to Add Tasks
You shouldn't have to stop working just to type out a massive description for a new task.
* **AI Photo Reader:** You can take a quick picture of messy handwriting on a sticky note, a whiteboard drawing, or a computer screenshot, and the AI will automatically turn it into clean text for your list.
* **Voice Memos:** If you're busy or on the move, you can talk directly into the app to log a thought quickly (like "need to do laundry and change cat litter"). The app reads the core idea and drops it straight into your inbox for you to approve or edit later.

### 3. Built-In Color Blind & Dyslexia Modes
Accessibility shouldn't require downloading messy third-party browser extensions that break your screen layout.
* **High-Contrast Monochrome:** Completely removes color dependencies so it's easy to read for anyone with color blindness.
* **Legible Typography:** Uses weighted fonts and specific text spacing to prevent visual crowding and make reading smooth for users with dyslexia.

---

## ✋App Limits & Privacy Boundaries

To keep cloud costs low and protect your private data, I built three strict limits directly into the system:

* **30-Second Voice Limit:** Live voice notes cut off at exactly 30 seconds. This keeps the app fast, stops the server from getting bogged down, and keeps AI costs to a minimum.
* **No Raw Audio File Uploads:** You cannot upload massive, multi-hour audio files (like a recorded Zoom meeting). The app only accepts live, short voice streams. This keeps the backend secure from broken code or heavy file payloads.
* **72-Hour Auto-Delete:** The app automatically purges your raw photos and voice clips 72 hours after you upload them. People naturally drop sensitive info into AI tools, so deleting files quickly ensures your privacy stays protected and our cloud storage stays completely lean.

---

## ☰ The Tech Stack

* **Where It Lives:** Deployed on **Google Cloud Run**. This environment runs the app inside lightweight containers and automatically scales up or down based on activity metrics.
* **The AI Engine:** Leveraged the **Google AI Studio ecosystem** to minimize infrastructure middleware, maximizing development velocity and ensuring native compatibility with containerized deployment paths.

---

## 🔜 What's Next (The 3-Week Plan)

I want to avoid "feature creep" (adding endless tools until the app gets bloated). The next 3 weeks are all about refining what's already there:

* **Active Testing:** I am currently dogfooding the live system to see how well the AI parses incredibly sloppy handwriting and muffled audio recordings.
* **Better Language Translations:** Making sure the entire interface translates perfectly into **French, Spanish, and Portuguese**, with two more common languages coming next. This ensures anyone using English as a second language or balancing schedules across borders isn't locked out.

---

## 🔄 Revision History & Changelog

### **June 23, 2026**
*   **Global Localization Expansion (Hindi `HI`):** Integrated native Hindi language support across the entire interface. Recognizing Hindi as one of the most widely spoken languages globally—and a primary language for a massive demographic of international tech professionals—this update bridges a critical accessibility gap, ensuring intuitive navigation, localized time-blocking semantics, and accurate microcopy rendering.
*   **Dynamic Viewport Typography Scaling Toggle:** Engineered an on-page text scaling toggle directly into the header workspace. Operators can dynamically scale page-specific typography between a **10pt minimum** (for high-density matrix scanning) and a **17pt maximum** (to alleviate visual fatigue and support low-vision or dyslexic users), bypassing rigid browser-level zoom configurations that disrupt layout grids.

```
