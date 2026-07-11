# 📧 AI Email Classifier & Auto Logger using n8n

![n8n](https://img.shields.io/badge/n8n-Automation-orange)
![Google Gemini](https://img.shields.io/badge/AI-Google%20Gemini-blue)
![JavaScript](https://img.shields.io/badge/Code-JavaScript-yellow)
![License](https://img.shields.io/badge/license-MIT-green)

An intelligent **AI-powered email automation system** built with **n8n**, **Google Gemini AI**, **Gmail API**, **Google Sheets**, and **Telegram Bot API**.

This workflow automatically monitors incoming emails, analyzes and classifies messages using AI, extracts important information, stores structured records in Google Sheets, and sends real-time Telegram alerts for high-priority emails.

This project is part of my **30-Day n8n Automation Portfolio**, showcasing practical automation solutions using AI, APIs, and workflow engineering.

---

# 🚀 Features

✅ Automatically monitors incoming Gmail messages  
✅ AI-powered email classification using Google Gemini  
✅ Generates intelligent email summaries  
✅ Detects important and high-priority emails  
✅ Parses AI responses into structured JSON format  
✅ Stores email records in Google Sheets  
✅ Sends instant Telegram notifications  
✅ Fully automated email triage workflow  
✅ Reduces manual email checking and organization  

---

# 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **n8n** | Workflow automation platform |
| **Gmail Trigger** | Detects incoming emails |
| **Google Gemini AI** | Email classification and summarization |
| **JavaScript Code Node** | JSON processing and data formatting |
| **IF Node** | Conditional email routing |
| **Google Sheets API** | Email logging database |
| **Telegram Bot API** | Notification system |
| **Google Workspace API** | Workspace integrations |

---

# 🏗️ Workflow Architecture

```

Incoming Gmail
│
▼
Gmail Trigger
│
▼
Edit Fields
│
▼
Google Gemini AI Agent
│
▼
Code Node
(Parse AI JSON Response)
│
▼
IF Node
(Important Email?)
│
┌────┴─────┐
▼          ▼
YES        NO
│          │
▼          ▼
Important  Email
Emails     Archive
Sheet      Sheet
│
▼
Telegram Notification

```

---

# ⚙️ Workflow Breakdown

## 1. Gmail Trigger

The workflow starts by monitoring the Gmail inbox for new incoming messages.

### Configuration

```

Event:
Message Received

Label:
INBOX

Polling:
Every Minute

````

The trigger captures new email information automatically.

---

# 2. Edit Fields Node

Extracts important email information before sending it to Gemini AI.

### Extracted Data

- Email Subject
- Sender Information
- Email Preview/Snippet
- Date Received

Example:

```json
{
  "subject": "Admin VA Job Opportunity",
  "sender": "Indeed",
  "message": "Your profile matches a position..."
}
````

---

# 3. Google Gemini AI Classification

The AI Agent analyzes the email content and determines:

* Email Category
* Priority Level
* Importance Status
* Summary

### Example AI Response

```json
{
  "category": "Job Application",
  "priority": "High",
  "important": true,
  "summary": "Invitation to apply for an Admin VA position."
}
```

---

# 4. Code Node (JSON Processing)

The JavaScript Code Node converts the AI response into structured data that n8n can process.

Responsibilities:

* Parse JSON output
* Extract AI-generated fields
* Prepare data for routing and storage

---

# 5. IF Node (Email Routing)

The workflow checks:

```javascript
important == true
```

## If TRUE

The email is:

* Stored in Important Emails Sheet
* Sent as Telegram notification

## If FALSE

The email is:

* Stored in Email Archive Sheet

---

# 6. Google Sheets Logging

All processed emails are automatically stored.

## Important Emails Sheet

Stores:

* High-priority emails
* Job opportunities
* Important notifications

## Email Archive Sheet

Stores:

* Regular emails
* Non-critical messages

---

# 7. Telegram Notification

Important emails trigger instant Telegram alerts.

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

🤖 Automatically classified using Google Gemini AI.
```

---

# 📊 Google Sheets Database Structure

| Date       | Subject         | Sender | Category        | Priority | Summary                 | Important |
| ---------- | --------------- | ------ | --------------- | -------- | ----------------------- | --------- |
| 2026-07-10 | Job Opportunity | Indeed | Job Application | High     | Matching position found | TRUE      |

---

# 📁 Project Structure

```
AI-Email-Classifier/
│
├── README.md
├── workflow.json
│
├── screenshots/
│   │
│   ├── workflow.png
│   ├── gmail-trigger.png
│   ├── ai-classification.png
│   ├── code-node-output.png
│   ├── google-sheets.png
│   ├── telegram-notification.png
│   └── workflow-execution.png
```

---

# 📷 Screenshots

Add screenshots showing:

* Complete n8n Workflow
* Gmail Trigger Configuration
* Gemini AI Classification Output
* Code Node JSON Processing
* IF Node Execution
* Google Sheets Records
* Telegram Notification
* Successful Workflow Execution

---

# 🎯 Skills Demonstrated

This project demonstrates practical experience with:

### Automation

* n8n Workflow Development
* API Integration
* Event-Based Automation
* Workflow Logic Design

### Artificial Intelligence

* AI Email Classification
* Prompt Engineering
* Structured AI Output Handling
* AI-Based Decision Making

### Programming

* JavaScript Data Processing
* JSON Parsing
* Conditional Logic

### Productivity Automation

* Gmail Automation
* Google Sheets Database Logging
* Telegram Notification Systems

---

# 🔮 Future Improvements

Possible upgrades:

* 📎 Process email attachments
* 🏷️ Automatically apply Gmail labels
* ✍️ Generate AI email replies
* 🌐 Support multiple languages
* 📊 Build email analytics dashboard
* 🔔 Add Slack and Discord notifications
* 🧠 Implement AI priority scoring
* 🔗 Integrate Notion or Airtable database

---

# 📜 License

This project is licensed under the **MIT License**.

---

# 👨‍💻 Author

## Belio C. Sinangote

**BS Information Technology Student**
Cebu Technological University (CTU)

GitHub:
[https://github.com/belioautomation](https://github.com/belioautomation)

---

⭐ This project is part of my **30-Day n8n Automation Portfolio**, where I build practical automation workflows using:

* n8n
* Artificial Intelligence
* APIs
* Google Workspace Automation
* Document Processing
* Workflow Engineering

```

This version is more aligned with a **professional automation portfolio repository** and is suitable for showcasing on GitHub, LinkedIn, or a developer portfolio.
```
