# Contact Form Automation with n8n

A modern and professional Contact Us page integrated with an n8n automation workflow for handling customer inquiries automatically.

This project includes:

- Modern Contact Form UI
- n8n Webhook Integration
- AI-generated Welcome Messages
- Automated Gmail Responses
- Google Sheets Integration
- Spam/Approval Workflow

---

# Features

- Premium fintech-style UI
- Fully responsive design
- Glassmorphism effects
- AJAX form submission
- Instant success message
- n8n webhook automation
- AI-powered welcome message generation
- Automated email sending
- Google Sheets logging
- Spam handling workflow

---

# Tech Stack

## Frontend
- HTML5
- CSS3
- Vanilla JavaScript

## Automation & Backend
- n8n
- Groq AI
- Gmail API
- Google Sheets API

---

# Project Structure

```bash
project/
│
├── index.html
├── README.md
└── workflow/
    └── My workflow.json
```

---

# Workflow Overview

```text
User Submits Contact Form
          ↓
Frontend Sends Request to n8n Webhook
          ↓
AI Generates Personalized Welcome Message
          ↓
Gmail Sends Auto Response
          ↓
Spam / Approval Check
          ↓
Store Submission in Google Sheets
```

---

# n8n Workflow Setup

## 1. Import Workflow

Open your n8n dashboard.

Navigate to:

```text
Workflows → Import from File
```

Import the workflow file:

```text
My workflow.json
```

---

## 2. Configure Credentials

You must connect the following services inside n8n:

### Gmail OAuth2
Used for sending welcome emails.

### Google Sheets OAuth2
Used for storing contact form submissions.

### Groq API
Used for AI-generated welcome messages.

Get your API key from:

https://console.groq.com

---

## 3. Activate Workflow

After completing the setup:

```text
Activate Workflow
```

n8n will generate two webhook URLs.

### Test Webhook URL

```text
/webhook-test/contact-form
```

### Production Webhook URL

```text
/webhook/contact-form
```

Use the Production URL in your frontend project.

---

# Frontend Setup

Open:

```text
index.html
```

Replace the webhook URL inside the JavaScript section.

```javascript
const webhookUrl = "YOUR_N8N_WEBHOOK_URL";
```

Example:

```javascript
const webhookUrl = "https://yourdomain.com/webhook/contact-form";
```

---

# Expected Request Payload

The frontend sends the following JSON payload to n8n:

```json
{
  "firstname": "John",
  "email": "john@example.com",
  "description": "Need website development services"
}
```

---

# AI Prompt Used

```text
You are an AI customer relations assistant for a premium fintech and automation company.

Write a polished, personalized thank-you message for a contact form submission.

Instructions:
- Use the customer's first name: {{ $json.body.firstname }}
- Reference their inquiry about: {{ $json.body.description }}
- Sound confident, modern, and professional
- Keep it under 5 lines
- Make the customer feel valued and acknowledged
- Confirm that our team will get back to them soon
- Do not sound robotic, repetitive, or overly formal

Return only the final message text.
```

---

# Deployment Options

You can deploy this project using:

- Netlify
- Vercel
- GitHub Pages
- cPanel Hosting
- AWS S3
- Firebase Hosting

---

# Security Recommendations

Recommended production improvements:

- Enable proper CORS configuration
- Add Google reCAPTCHA
- Enable webhook authentication
- Add rate limiting
- Validate form inputs
- Sanitize request data

---

# Future Improvements

Possible upgrades for this project:

- File upload support
- WhatsApp integration
- Telegram notifications
- CRM integration
- Admin dashboard
- Tailwind CSS version
- React / Next.js version
- Multi-step forms
- AI chatbot support

---

# Screenshots

Add project screenshots inside:

```text
/assets/
```

Example:

```text
/assets/contact-page.png
```

---

# Author

Arnab Roy

---

# License

This project is licensed under the MIT License.