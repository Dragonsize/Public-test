# Elearn Solver – Userscript
A lightweight Tampermonkey script that adds an AI-powered helper UI to TDTU eLearning quizzes.  
The tool reads each multiple-choice question, sends it to the Gemini API, and selects the most likely answer automatically.

---

Features
- Toggle UI with Ctrl + Shift + F
- Paste & store your **Gemini API key** securely (local storage via Tampermonkey)
- Draggable, collapsible, modern UI panel
- “Solve” button scans all visible multiple-choice questions
- Confidence-based coloring:
  - 🟢 High confidence  
  - 🟡 Medium  
  - 🔴 Low (flagged for manual review)
- “Test” button to check API connectivity
- Auto-retry on rate limiting (429)
- Works on:  
  `https://elearning.tdtu.edu.vn/mod/quiz/*`

- Tampermonkey browser extension
- A valid Gemini API Key

## 📥 Installation
1. Install Tampermonkey.
2. Create a new script → paste the userscript from this repository.
3. Save.
4. Open a quiz on eLearning.
5. Press Ctrl + Shift + F to show/hide the AI panel.
6. Paste your API key.
7. Click Solve.

---

 🧠 How It Works
1. The script extracts:
   - Question text  
   - Answer choices  
2. Sends them to Gemini using:
model: gemini-2.0-flash-lite
endpoint: /v1beta/models/...:generateContent
3. Expects output:
INDEX|CONFIDENCE
4. Auto-selects the returned option in the quiz UI.
4. Auto-selects the returned option in the quiz UI.

---

## ⚙️ Hotkeys
| Keys | Action |
|------|---------|
| **Ctrl + Shift + F** | Toggle AI Solver panel |

---

## 🛠 Technical Overview
- Tampermonkey Userscript
- Uses:
- `GM_xmlhttpRequest` for API calls
- `GM_setValue` / `GM_getValue` for storing API key
- No backend — fully client-side









