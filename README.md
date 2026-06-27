# 🎮 Pocket Life

> A life report card you can *live* and level up in.

**Pocket Life** is an interactive "report card for your life." Instead of grading yourself once and walking away, you step into a little pixel room where every object represents a different area of your life. Walk up to it, log your daily effort, and grade yourself either by hand or with a tap of the **✨ AI** button (powered by the Claude API). 

This project was built in **4 hours** for a **Mini Vibe-Coding Hackathon** during my internship at **Hanwha Life Insurance**. The theme was *"Life Report Card"*, and I put a spin on it by turning a static grade into a "living" room.

---

## ✨ The idea

A normal report card is a snapshot. Pocket Life is an active loop meant for growth:

**Log → Grade → Improve → Re-grade.**

Each category of life is an item in your room. Every day you record your small efforts toward those categories, then either grade yourself or ask the AI to grade you and suggest what to do next. The goal is to make self-improvement feel less like a spreadsheet and more like a game you check in on.

---

## 🕹️ How to Use

Click the pages and use everyday. Since this was hosted only for frontend/demonstration purposes, your data is saved and exported/imported through JSON files in the 'Customize' tab.

Everything runs in the browser and saves to local storage, so your data persists between visits on the same device.

**Controls**
- **Move:** `WASD` or arrow keys
- **Interact:** `E` or `Space`
- A prompt pops up when you're near an interactable object.

---

## 🏡 The Living Room

Walk up to any object and press `E`/`Space` to open it. Each one maps to a part of your life:

| Object | Category | What you do there |
|---|---|---|
| 🐷 Piggy bank | **Finances** | Log income & expenses in an account book. AI reviews your habits and suggests how to spend smarter. |
| 💻 Computer (desk) | **Career** | Log jobs, skills, and certifications. |
| 🖨️ Printer | **Resume** | Turns your Career log into a clean, printable résumé (print → save as PDF). |
| 💧 Water cooler | **Water Intake** | Tap glasses to track how much water you drank. |
| 🏋️ Dumbbell | **Health & Fitness** | Log workouts and exercises (with custom workout categories). |
| 🍳 Fridge | **Meal Intake** | Log what you eat each day. |
| 📔 Table | **Mental Health** | A journal plus a mood/emotion picker. |
| 📚 Bookshelf | **Reading** | Track what you're reading. |
| 📬 Mailbox | **Report Card** | Jump to your overall grades. |
| 🐶 Dog | — | Pet it. Hearts happen. (Purely for joy.) |

---

## 🗂️ The tabs

- **🏡 Room** — the playable pixel room described above.
- **📋 Report** — your big-picture report card. Grades for each section (Health, Career, Mental Health, Finances, Reading) roll up into a GPA-style view, with A+ → F mapped to grade points. **Export the whole thing as a PNG.**
- **📜 Logs** — a day-by-day history of everything you logged, per category.
- **🎨 Customize** — change your avatar (shirt color, hair color, and 11 hairstyles) and switch room themes (Cozy or a Hanwha-orange theme). Also where you manage **data backup** and your **AI key**.

---

## 🤖 AI grading (Claude)

Every category screen has an **✨ AI** button. Press it and Pocket Life sends *only your logged data for that category* to **Claude** (`claude-haiku-4-5`) with a "concise life coach" system prompt. Claude returns:

- a **letter grade** (A+ → F), and
- **2–3 short, specific suggestions** for improving.

The response is requested as **structured JSON output** (constrained to a fixed grade enum + suggestions list), so the grade and tips drop straight into the UI.

- Add your API key once in the **🎨 Customize** tab. It's stored locally on your device and is **never included in data exports**.
- A **Google Gemini** fallback (`gemini-2.0-flash-lite`) is also supported; the app auto-detects the provider from your key.

---

## 💾 Data & privacy

- All progress is saved to your browser's **local storage** (no account, no server).
- **Export / Import** your full backup as a JSON file from the Customize tab (your API key is deliberately excluded).

---

## 🛠️ Built with

- **Vanilla HTML, CSS, and JavaScript** in a single self-contained `index.html`; pixel-art rendered to a `<canvas>` with classic Game Boy proportions.
- **[Claude Code](https://www.anthropic.com/claude-code)** — the entire thing was *vibe coded*. All the visuals, code, and execution came out of Claude Code; the **strategy, concept, and setup were my own**.
- Custom **Claude Code subagents** to keep quality up during a 4-hour sprint:
  - `product-manager` — scoped features, wrote specs, and budgeted effort.
  - `design-reviewer` — critiqued the UI and pushed the visual polish.
- **Claude API** for the in-app AI grading.

```
hackathon/
├── index.html                 # the entire app
├── pocket-life-backup.json     # sample data backup
├── 272210.KS-e7eafd81.png      # asset
├── hanwha-logo.jpg             # asset (Hanwha theme)
└── .claude/
    └── agents/
        ├── product-manager.md
        └── design-reviewer.md
```

---

## 🚀 Future directions

This was a 4-hour build, but if it were a real product, future updates would include the following:
- **Let each user customize their own room** — pick which categories to add, since everyone's goals are different.
- **Add more room themes** and more playful tidbits (more pets, decorations, easter eggs) like the dog.
- Lean further into the gamification, until it's almost a **"metaverse of yourself"** — a place where improving your life feels like leveling up a character.

---

## 🏷️ Context

Made for a **Mini Vibe-Coding Hackathon** (~4 hours) during my internship at **Hanwha Life Insurance**. Theme: *Life Report Card*.