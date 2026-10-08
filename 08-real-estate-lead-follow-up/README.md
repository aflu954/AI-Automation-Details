Automate Lead Follow-Up with Claude Connectors + a Custom Skill (Real Estate)
Objective
Build an automated lead-triage workflow using Claude Connectors and a Custom Skill.

The system should:

Pull leads from a Google Sheet.

Prioritize leads based on predefined criteria.

Sort leads from High → Medium → Low priority.

Generate follow-up messages for High-Priority Leads.

Step 1 — Enable Prerequisites
Go to:

Settings → Capabilities

Enable the following:

Code Execution

File Creation

Note: Skills will not run without these capabilities enabled.

Step 2 — Connect Google Sheets / Google Drive
Go to:

Customize → Connectors

Connect your Google Drive account, which also provides access to Google Sheets.

Create or use a Google Sheet containing lead information with the following columns:



Step 3 — Verify the Connector
Open a new chat and enter:

“Pull today's rows from [Sheet Name] and list them.”

Confirm that Claude:

Pulls data from the actual Google Sheet.

Returns the correct lead information.

Does not invent lead data.

Step 4 — Create the Custom Skill
Create a Custom Skill with the following details:

Skill Name: lead-triage

Trigger
The Skill should run when the user enters:

“triage today's leads”

It may also be configured to run when new leads are added to the sheet.

Skill Workflow
The Skill should first pull all rows from [Sheet Name] using the Google Drive connector where:

Status = "New"

Then score each lead using the following criteria.

High Priority
A lead should be marked High Priority when:

The budget matches available inventory.

The source is a referral or hot listing inquiry.

Medium Priority
A lead should be marked Medium Priority when:

The budget matches available inventory.

The source is a cold lead or advertisement.

Low Priority
A lead should be marked Low Priority when:

The budget does not match available inventory.

Information is incomplete.

Sorting Order
Sort all processed leads in the following order:

High → Medium → Low

Follow-Up Messages
For every High-Priority Lead, generate a short 2-line follow-up message using a professional call/SMS tone.

Required Output Format


Step 5 — Upload and Enable the Skill
Go to:

Customize → Skills

Then:

Upload or create the lead-triage Skill.

Enable the Skill by toggling it ON.

Confirm that the Skill is available for use.

Step 6 — Run the Workflow End-to-End
Open a fresh chat and enter:

“triage today's leads”

Verify that:

The Skill pulls leads from the connected Google Sheet.

Only leads with Status = New are processed.

The priority scoring follows the defined criteria.

Leads are sorted from High → Medium → Low.

High-Priority Leads receive appropriate follow-up messages.

The messages sound natural and usable by a real estate agent rather than generic AI-generated text.

If the scoring logic does not work correctly, update the Skill and run the workflow again.

Step 7 — Submission Requirements
1. Screenshots
Submit screenshots showing:

Connector Setup
Google Drive/Google Sheets connector successfully connected.

Skill Setup
lead-triage Skill created and enabled.

Complete Workflow Run
Take one complete screenshot/run of “triage today's leads” showing:

Leads pulled from the Google Sheet.

Priority scoring.

Sorted lead list.

Suggested actions.

Follow-up messages for High-Priority Leads.

2. Reflection Paragraph
Write one paragraph explaining:

Where the lead-scoring logic broke, failed, or felt inaccurate.

Which leads were incorrectly prioritized, if any.

What changes you would make to improve the Skill's scoring logic.

Submission Checklist
Before submitting, make sure you have completed all of the following:

Google Drive/Sheets connector connected successfully.

Google Sheet contains lead data.

Connector tested with real data.

lead-triage Custom Skill created.

Skill enabled.

Lead prioritization tested.

High-Priority follow-up messages generated.

Required screenshots included.

Reflection paragraph included.
