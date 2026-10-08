# Course Inquiry Auto-Triage Bot

## 1. Project Overview

This workflow is built in n8n to automatically process course inquiries received through a webhook.

The workflow checks the incoming information, sends valid inquiries to the AI step for classification, validates the AI response, assigns a lead score, and routes the inquiry based on the result.

The workflow supports Bangla, English, and Banglish messages.

---

## 2. Main Workflow

The basic flow is:

**Webhook → Input Validation → Prepare Prompt → AI Processing → JSON Validation → Lead Routing → Google Sheets / Slack / Gmail**

The workflow also has separate handling for rejected inputs and invalid AI responses.

---

## 3. Required Input

The webhook expects the following fields:

* `name`
* `phone`
* `email`
* `course_interest`
* `message`

Example:

```json
{
  "name": "Rahim Ahmed",
  "phone": "1712345678",
  "email": "rahim@gmail.com",
  "course_interest": "AI Automation",
  "message": "আমি AI Automation কোর্সে ভর্তি হতে চাই। কোর্সের ফি কত?"
}
```

---

## 4. Input Validation

The workflow checks the required `phone` and `message` fields.

If either one is missing, the inquiry does not continue to the AI step.

It is recorded as:

**Route:** `REJECTED`

**Reason:** `Missing phone or message`

This was tested with requests where the phone number was missing.

---

## 5. AI Processing

The AI step classifies each valid inquiry and returns these fields:

* `intent`
* `lead_score`
* `language`
* `summary`
* `suggested_reply`
* `needs_human`

The supported intent values are:

* `price`
* `schedule`
* `job_placement`
* `complaint`
* `spam`
* `other`

The lead score is between **1 and 10**.

---

## 6. Lead Routing

The workflow uses the AI result to decide where the inquiry should go.

| Condition                    | Route    |
| ---------------------------- | -------- |
| Lead score 7–10              | HOT      |
| Lead score 4–6               | MEDIUM   |
| Lead score 1–3               | LOW      |
| Complaint / human assistance | SUPPORT  |
| Spam inquiry                 | SPAM     |
| Missing required input       | REJECTED |
| Invalid AI JSON              | FALLBACK |

The routing result is also stored in the Google Sheet.

---

## 7. Google Sheets Logging

The workflow records the processing result in Google Sheets.

The log contains information such as:

* Timestamp
* Name
* Phone
* Email
* Course
* Message
* Intent
* Lead Score
* Language
* Summary
* Suggested Reply
* Needs Human
* Route
* Reason
* AI Raw Output
* Prompt Tokens
* Completion Tokens
* Total Tokens
* Estimated Token Cost

This makes it easier to check the result of each test request.

---

## 8. Error and Fallback Handling

There are two important edge cases in the workflow.

### Missing Input

If `phone` or `message` is missing:

**Route:** `REJECTED`

**Reason:** `Missing phone or message`

### Invalid AI Output

If the AI does not return valid JSON in the expected format, the workflow does not continue with normal routing.

Instead:

**Route:** `FALLBACK`

**Reason:** `Invalid AI JSON output`

A Security Test was used to check this case.

---

## 9. Language Testing

The workflow was tested with:

* Bangla
* English
* Banglish

Example Bangla inquiry:

`আমি AI Automation কোর্সে ভর্তি হতে চাই। কোর্সের ফি কত?`

Example Banglish inquiry:

`AI Automation course er fee koto? Installment e payment kora jabe?`

Example English inquiry:

`Does the course provide job placement support after completion?`

---

## 10. Google Sheets Setup

Before running the workflow, connect the Google Sheets credential in the Google Sheets nodes.

Select the spreadsheet and the required worksheet.

Make sure the sheet columns match the fields used by the workflow.

For example:

`Timestamp | Name | Phone | Email | Course | Message | Intent | Lead Score | Language | Summary | Suggested Reply | Needs Human | Route | Reason | AI Raw Output | Prompt Tokens | Completion Tokens | Total Tokens | Estimated Token Cost`

---

## 11. AI Credential Setup

The AI node requires the configured AI provider credential.

For the current workflow, the AI processing step uses the configured Groq connection.

If the workflow is imported into another n8n account, the credential needs to be selected again in the AI node.

Do not put API keys directly inside the workflow JSON.

---

## 12. Webhook Testing

For testing, send a POST request to the webhook URL with JSON data.

Example:

```json
{
  "name": "Rahim Ahmed",
  "phone": "1712345678",
  "email": "rahim@gmail.com",
  "course_interest": "AI Automation",
  "message": "আমি AI Automation কোর্সে ভর্তি হতে চাই। কোর্সের ফি এবং পেমেন্ট পদ্ধতি জানতে চাই।"
}
```

The response and routing result can then be checked in n8n and in the Google Sheet.

---

## 13. Test Cases

The workflow was checked with different types of inputs, including:

1. Price inquiry
2. Schedule inquiry
3. Complaint
4. Missing phone
5. Banglish price inquiry
6. Job placement inquiry
7. Spam message
8. Low-intent inquiry
9. Missing phone
10. Invalid AI JSON

The selected test cases were recorded in the test table.

**Test Result: 10/10 PASS**

---

## 14. Cost Tracking

The workflow records:

* Prompt Tokens
* Completion Tokens
* Total Tokens
* Estimated Token Cost

The cost changes depending on the size of the incoming message and the AI response.

The recorded test data can be used to estimate the expected cost before using the workflow with a larger number of inquiries.

---

## 15. Import and Setup

To use the workflow on another n8n instance:

1. Import the workflow JSON.
2. Open the Webhook node and check the authentication settings.
3. Select the required AI credential.
4. Select the Google Sheets credential.
5. Check the spreadsheet and worksheet.
6. Select Slack/Gmail credentials if those nodes are being used.
7. Save the workflow.
8. Activate the workflow if a production webhook is required.
9. Send a test POST request.
10. Check the route and Google Sheet log.

---

## 16. Submission Files

The project submission contains:

* Workflow JSON export
* README.md setup guide
* Test Table with 10 test cases
* Google Sheets execution logs
* Test/result screenshots
* Video demonstration

The exported submission JSON should not contain API keys, passwords, or other credential secrets.
