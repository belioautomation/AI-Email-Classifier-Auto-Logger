# 📧 AI Email Classifier & Auto Logger using n8n

An intelligent email automation workflow built with **n8n** and **Google Gemini AI**. This workflow automatically monitors incoming Gmail messages, classifies emails using AI, logs the results to Google Sheets, and sends Telegram notifications for important emails.

Built as part of my **30-Day n8n Automation Portfolio**, this project demonstrates AI-powered email classification, workflow automation, and productivity enhancement.

---

## 📌 Features

- 📩 Automatically monitors incoming Gmail messages
- 🤖 Classifies emails using Google Gemini AI
- 📝 Generates AI-powered email summaries
- ⭐ Detects high-priority emails
- 📊 Logs classified emails to Google Sheets
- 📲 Sends Telegram notifications for important emails
- 🧠 Uses structured JSON output for workflow automation
- ⚡ Fully automated workflow

---

## 🛠️ Technologies Used

- n8n
- Gmail Trigger
- Google Gemini AI
- Code Node (JSON Parser)
- IF Node
- Google Sheets API
- Telegram Bot API
- JavaScript

---

## 📂 Workflow

```text
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

## ⚙️ Workflow Explanation

### 1. Gmail Trigger

Monitors the Gmail inbox for newly received emails.

Configuration:

- Event: Message Received
- Label: INBOX
- Polling: Every Minute

---

### 2. Edit Fields

Extracts the required email information before sending it to the AI.

Fields:

- Subject
- Sender
- Email Preview (Snippet)
- Date

---

### 3. AI Agent (Google Gemini)

Google Gemini analyzes each email and determines:

- Email Category
- Priority
- Importance
- Summary

Example Output:

```json
{
  "category": "Job Application",
  "priority": "High",
  "important": true,
  "summary": "Invitation to apply for an Admin VA position."
}
```

---

### 4. Code Node

Parses the JSON response returned by Google Gemini into structured data that n8n can process.

---

### 5. IF Node

Checks:

```text
important == true
```

If **True**

- Save to **Important Emails**
- Send Telegram notification

If **False**

- Save to **Email Archive**

---

### 6. Google Sheets

Stores all classified emails.

**Important Emails**

Stores high-priority emails.

**Email Archive**

Stores non-important emails.

---

### 7. Telegram

Sends an instant notification whenever an important email is detected.

Example:

```text
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

🤖 Classified automatically using Google Gemini AI.
```

---

## 📊 Google Sheets Structure

| Date | Subject | Sender | Category | Priority | Summary | Important |
|------|---------|--------|----------|----------|---------|-----------|

---

## 📁 Repository Structure

```text
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
```

---

## 📷 Screenshots

Include the following screenshots:

- Complete Workflow
- Gmail Trigger
- AI Agent Output
- Code Node Output
- IF Node Execution
- Google Sheets Results
- Telegram Notification
- Workflow Execution

---

## 🎯 Learning Objectives

This project demonstrates:

- Gmail Automation
- AI Email Classification
- Prompt Engineering
- Structured JSON Parsing
- JavaScript Data Processing
- Conditional Workflow Logic
- Google Sheets Automation
- Telegram Automation
- AI-Powered Email Triage

---

## 🚀 Future Improvements

- Support email attachments
- AI sentiment analysis
- Auto-label Gmail messages
- AI-generated email replies
- Multi-language email classification
- Slack and Discord notifications
- Email priority scoring
- Weekly analytics dashboard
- Integration with Notion or Airtable

---

## 📜 License

This project is licensed under the MIT License.

---

## 👨‍💻 Author

**Belio Sinangote**

**30-Day n8n Automation Roadmap**

Building portfolio-ready automation projects using **n8n**, **Google Gemini AI**, and modern workflow automation technologies.
