# retainiq-plugnplay-agents

# RetainIQ Plug-and-Play Agents

This repository contains the full source code, prompts, and test files for the **RetainIQ Plug-and-Play Agent System** — an AI-powered onboarding engine designed to help SMBs activate faster with intelligent data upload, validation, and insight generation.

---

## 🚀 Project Purpose
To enable SMB users to onboard into RetainIQ by simply uploading a CSV or Excel file and getting instant:
- Schema mapping suggestions
- Data quality checks
- Churn predictions
- GPT-powered insights
- Smart feedback and error correction

All powered by lightweight assistive AI agents, integrated into Lovable (frontend), Pipedream (workflow), Supabase (data), and Render (model serving).

---

## 🧠 Architecture Overview

```
┌────────────┐      ┌──────────────┐      ┌──────────────────┐
│ Lovable UI │────▶│ Pipedream API│────▶│ GPT + Model Layer │
└────────────┘      └──────────────┘      └──────────────────┘
     ▲                      │                      │
     │                      ▼                      ▼
     │              Supabase Staging        OpenAI / Render
     │                      │                      │
     └──────────────────────┴──────────────────────┘
```

Each agent lives in its own folder and is responsible for a specific onboarding micro-task.

---

## 🧩 Folder Structure

```
retainiq-plugnplay-agents/
├── workflows/              # Agent logic
│   └── file_format_assistant/
│       ├── index.js
│       └── sample_input.csv
├── prompts/                # GPT system prompts
│   └── file_format_prompt.txt
├── test_data/              # CSV/XLS files for QA
├── docs/
│   └── agents-blueprint.md
├── .env.example            # Template for required keys
└── README.md               # This file
```

---

## 🛠 How to Run Agents Locally (Test)

### Requirements
- Node.js 18+
- OpenAI API Key
- `csv-parse`, `node-xlsx`, `dotenv`

### 1. Clone the Repo
```bash
git clone https://github.com/yourusername/retainiq-plugnplay-agents.git
cd retainiq-plugnplay-agents
```

### 2. Install Dependencies
```bash
npm install csv-parse node-xlsx dotenv
```

### 3. Set Environment Variables
Create a `.env` file:
```
OPENAI_API_KEY=sk-xxx
```

### 4. Run Agent Script
```bash
node workflows/file_format_assistant/index.js
```

---

## 🧪 Test File Upload Example
Put your test file inside `test_data/`:
- `customer_sample_good.csv`
- `customer_sample_missing_cols.xlsx`

Then test it using Postman or your frontend to hit the HTTP trigger endpoint (once deployed via Pipedream).

---

## 📄 License
MIT License — use with attribution.

---

## 💬 Maintainer
Chintamani Modak  
Founder, RetainIQ  
[LinkedIn](https://linkedin.com/in/chintamanimodak)
