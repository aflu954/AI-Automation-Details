Build an AI-Powered Lead Qualification & CRM Automation with Make.com
Objective
Build a complete automation in Make.com that captures new leads, qualifies them using AI, and stores the results in a CRM or Google Sheets.

Scenario
A training company receives inquiries through a Google Form. The sales team wants every lead to be automatically analyzed before contacting them.

Requirements
Your Make.com scenario must:

Trigger when a new Google Form response is submitted.

Extract the following lead information:

Name

Email

Company

Job Title

Budget

Message

Send the lead's message to an AI model (OpenAI or another LLM) to:

Summarize the inquiry

Identify the lead's intent

Assign a Lead Score (1–10)

Recommend the next action

Use a Router to categorize leads:

High-quality: Score ≥ 8 → Send to Slack or Email

Medium-quality: Score 5–7 → Store in CRM or Google Sheets

Low-quality: Score < 5 → Archive separately

Log every processed lead into Google Sheets.

Add proper error handling so the scenario continues even if the AI request fails.

Deliverables
Submit the following:

Make.com Scenario Blueprint (.json)

Loom/Video Walkthrough (3–5 minutes)

Screenshots of:

Scenario Overview

Successful Execution

Google Sheets Output

AI Response

A brief explanation of:

How the Router works

How the Filters categorize leads

How Error Handling is implemented

Submission Format
Scenario Blueprint: .json

Video: Loom link

Screenshots: JPG/PNG

Explanation: PDF/Doc/Google Doc
