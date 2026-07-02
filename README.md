# 📧 AI Email Classifier & Auto Logger using n8n

An intelligent email automation workflow built with **n8n** and **Google Gemini AI**. This project automatically monitors incoming Gmail messages, classifies each email using AI, stores the results in Google Sheets, and sends Telegram notifications only for important emails.

Designed as part of a **30-Day n8n Automation Portfolio**, this project demonstrates how AI can automate email triage and improve productivity.

---

# 📌 Features

- 📩 Automatically monitors new Gmail messages
- 🤖 Uses Google Gemini AI to classify emails
- 📝 Generates AI-powered email summaries
- ⭐ Detects whether an email is important
- 📊 Automatically logs every email to Google Sheets
- 📲 Sends Telegram notifications for important emails only
- 🧠 Uses structured JSON output for workflow decisions
- 🆓 Uses free Google Workspace services

---

# 🛠 Technologies Used

- n8n
- Gmail Trigger
- Google Gemini AI
- Google Sheets API
- Telegram Bot API
- JavaScript (Code Node)

---

# 📂 Workflow

```
Gmail Trigger
      │
      ▼
Edit Fields
      │
      ▼
AI Agent (Google Gemini)
      │
      ▼
Code (Parse AI JSON)
      │
      ▼
IF (Important?)
 ┌──────────────┐
 ▼              ▼
Google Sheets Google Sheets
(Important)   (Archive)
 │
 ▼
Telegram
```

---

# ⚙ Workflow Explanation

## 1. Gmail Trigger

Monitors the Gmail inbox for newly received emails.

Configuration:

- Event: Message Received
- Polling: Every Minute
- Label: INBOX

---

## 2. Edit Fields

Extracts only the necessary email information before sending it to the AI.

Fields:

- Subject
- Sender
- Email Preview (Snippet)
- Date

---

## 3. AI Agent (Google Gemini)

Google Gemini analyzes the email and determines:

- Email category
- Priority level
- Whether the email is important
- Short summary

Expected AI Output:

```json
{
  "category": "Job Application",
  "priority": "High",
  "important": true,
  "summary": "Invitation to apply for an Admin VA position."
}
```

---

## 4. Code Node

Parses the JSON returned by Gemini into structured data that n8n can process.

This replaces the Structured Output Parser, making the workflow compatible with older n8n versions.

---

## 5. IF Node

Checks:

```
important == true
```

If **True**

- Save to Important Emails sheet
- Send Telegram notification

If **False**

- Save to Email Archive sheet

---

## 6. Google Sheets

Stores all classified emails.

### Important Emails

Stores high-priority emails.

### Email Archive

Stores non-important emails.

---

## 7. Telegram

Sends an instant notification whenever an important email is detected.

Example:

```
📧 Important Email Detected

📌 Subject:
Admin VA (Airtable Specialist)

👤 From:
Indeed

📂 Category:
Job Application

⭐ Priority:
High

📝 Summary:
Your background appears to match an Admin VA position.

🤖 Classified automatically by Gemini AI
```

---

# 📊 Google Sheets Structure

| Date | Subject | Sender | Category | Priority | Summary | Important |
|------|---------|--------|----------|----------|---------|------------|

---

# 📁 Repository Structure

```
AI-Email-Classifier/
│
├── README.md
├── workflow.json
│
├── screenshots/
│   ├── workflow.png
│   ├── gmail-trigger.png
│   ├── ai-classification.png
│   ├── google-sheets.png
│   ├── telegram-notification.png
│   └── workflow-execution.png
│
└── assets/
    └── sample-output.json
```

---

# 📷 Screenshots

Include the following screenshots:

- Complete Workflow
- Gmail Trigger
- AI Agent Output
- Code Node Output
- IF Node Execution
- Google Sheets Results
- Telegram Notification

---

# 🎯 Learning Objectives

This project demonstrates:

- Gmail Automation
- AI Email Classification
- Prompt Engineering
- JSON Parsing
- JavaScript in n8n
- Conditional Workflow Logic
- Google Sheets Automation
- Telegram Automation
- AI-Powered Decision Making

---

# 🚀 Possible Improvements

- Support email attachments
- AI sentiment analysis
- Auto-label Gmail messages
- Auto-reply using AI
- Multi-language email classification
- Slack notifications
- Discord notifications
- Email prioritization scoring
- Weekly email analytics dashboard
- Integration with Notion or Airtable

---
# 🙌 Acknowledgements

- n8n
- Google Gemini AI
- Gmail API
- Google Sheets API
- Telegram Bot API

---
# 📄 License

This project is licensed under the MIT License.

---



