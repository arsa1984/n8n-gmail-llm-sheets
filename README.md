# 📧 Gmail → 🧠 OpenAI → 📊 Google Sheets with n8n

This project is a **workflow automation** built with [n8n](https://n8n.io) that demonstrates how to:

- ✅ Read incoming emails from **Gmail**
- ✅ Process the email content with **OpenAI (LLM Chain)** to generate a short summary
- ✅ Store sender, subject, and summary into **Google Sheets**

Perfect as a **portfolio project** (GitHub, LinkedIn) or as a starting point for real-world automations.

---

## 🚀 Features
- Gmail integration with filters (subject, sender, etc.)
- AI-powered summarization of email content
- Automatic logging into Google Sheets
- Fully dockerized setup → run anywhere with one command

---

## 🛠 Tech Stack
- [n8n](https://n8n.io) (workflow automation platform)
- [Docker + Docker Compose](https://docs.docker.com/)
- Gmail API
- Google Sheets API
- OpenAI API (LLM Chain)

---

## ⚡ Getting Started

### 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/n8n-gmail-llm-sheets.git
cd n8n-gmail-llm-sheets

### 2. Configure environment variables
cp .env.example n8n.env  
Edit `n8n.env`:  
- Set `N8N_BASIC_AUTH_USER` and `N8N_BASIC_AUTH_PASSWORD`  
- Generate an encryption key:  
python3 -c "import secrets;print(secrets.token_hex(32))"  
- Add your license key if you use n8n Enterprise  

### 3. Run with Docker
docker compose up -d  

Access the n8n UI at: 👉 http://localhost:5678

---

## 📄 Import Workflow
- Go to the n8n UI  
- Workflows → Import from File  
- Select `workflow-gmail-to-sheets.json`  
- Configure your own Gmail, Google Sheets, and OpenAI credentials  

---

## 📊 Google Sheets Setup
Create a new Google Sheet with the following headers in row 1:  
name | email | message | text  
This ensures the workflow can append new rows correctly.  

---

## 🔐 Security Notes
- This repo does not contain any real credentials.  
- `.env.example` is provided as a template — replace with your own values.  
- The actual `n8n.env` file should **never** be pushed to GitHub.  
- API keys and OAuth secrets are stored securely in n8n, not in the workflow JSON.  

---

## 🎯 Use Cases
- Automated email summarization (personal inbox assistant)  
- Logging customer support requests into Sheets  
- Tracking newsletters or specific alerts in a spreadsheet  
- Portfolio / demo project to showcase n8n + AI automation skills  

---

## 🖼 Screenshots
(Optional: Add workflow diagram or screenshots here)  

---

## 💡 Next Steps
- Extend the workflow to send Slack/Telegram notifications  
- Add labels/filters in Gmail for smarter routing  
- Use structured JSON output from OpenAI for richer logging  

---

## 📜 License
MIT License. Free to use, modify, and share.
