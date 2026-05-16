# 🚀 FounderLogic AI

> **AI-powered startup idea validator — get a market score, verdict, and deep analysis in seconds.**

---

## 📌 Overview

**FounderLogic AI** is a real-time startup viability analyzer built with **Streamlit** on the frontend and **n8n** on the backend. The user submits a startup idea, and an AI Agent (powered by **Llama 3.3 70B via Groq** + **SerpAPI** for live web search) returns a structured verdict with a market score, validation result, and detailed analysis.

---

## 🧠 How It Works

```
User Input (Streamlit)
        ↓
n8n Webhook (Production)
        ↓
AI Agent — Llama 3.3 70B (Groq) + SerpAPI (Google Search)
        ↓
Respond to Webhook → JSON { score, verdict, analysis }
        ↓
Streamlit displays Score + Verdict + Analysis
```

---

## 🖥️ Tech Stack

| Layer     | Technology                        |
|-----------|-----------------------------------|
| Frontend  | Python · Streamlit                |
| Backend   | n8n (self-hosted or cloud)        |
| AI Model  | Llama 3.3 70B via Groq            |
| Search    | SerpAPI (real-time Google search) |
| Transport | HTTP Webhook (POST · JSON)        |

---


## 📤 Expected n8n Response Format

The `Respond to Webhook` node in n8n must return a JSON with exactly these fields:

```json
{
  "score": 8,
  "verdict": "VALIDATE",
  "analysis": "The idea addresses a real gap in the Web3 security market..."
}
```

| Field      | Type    | Description                              |
|------------|---------|------------------------------------------|
| `score`    | integer | Market viability score from 0 to 10      |
| `verdict`  | string  | `"VALIDATE"` or `"REJECT"`              |
| `analysis` | string  | Detailed AI-generated market analysis    |

---

## 🎨 UI Features

- 📊 **Market Score** displayed as a metric (0–10)
- ✅ / ❌ **Color-coded Verdict** — green for VALIDATE, red for REJECT
- 📝 **Detailed Analysis** returned by the AI Agent
- ⏳ **Spinner** while the agent searches and processes
- 🛡️ **Robust error handling** with user-friendly messages

---

## 📁 Project Structure

```
founderlogic-ai/
├── app.py          # Main Streamlit application
├── README.md       # Project documentation
└── .env            # (optional) Environment variables — do not commit
```

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

---


  © 2026 dev_gste All rights reserved

---

<p align="center">Built with ❤️ using Streamlit · n8n </p>
