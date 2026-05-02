# 💬 MockChat — Streamlit Chat Demo

A ChatGPT-style chat application built with **Streamlit**, running entirely locally.  
**No external LLMs, no APIs, no API keys required.**

---

## Features

| Feature            | Detail                                  |
| ------------------ | --------------------------------------- |
| Chat UI            | `st.chat_message` + `st.chat_input`     |
| State management   | `st.session_state.messages`             |
| Mock responses     | Keyword-matching Python function        |
| Clear conversation | Sidebar button                          |
| Styling            | Custom CSS (dark theme, IBM Plex fonts) |

---

## Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/<your-username>/mockchat.git
cd mockchat

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the app
streamlit run chat_app.py
```

Open your browser at **http://localhost:8501**.

---

## How the mock responses work

```
User input
    │
    ▼
generate_response(text)
    │
    ├─ normalise to lowercase
    │
    ├─ iterate keyword groups
    │       (hello/hi/hey → greeting replies)
    │       (python/code  → Python replies)
    │       (joke/funny   → jokes)
    │       … etc.
    │
    ├─ keyword matched? → random.choice(matched replies)
    │
    └─ no match?        → random.choice(FALLBACK_RESPONSES)
```

Zero network calls. Zero external dependencies beyond Streamlit itself.

---

## Tech skills used

- **Python 3.x** — core language
- **Streamlit** — `st.chat_message`, `st.chat_input`, `st.session_state`
- **State management** — conversation history persisted in `st.session_state`
- **CSS** — custom dark-theme styling injected via `st.markdown`
- **Simple NLP simulation** — keyword matching + `random.choice`

---

## Project structure

```
.
├── chat_app.py        # Single-file application (< 200 lines)
├── requirements.txt   # Streamlit only
└── README.md
```
# mockchat
