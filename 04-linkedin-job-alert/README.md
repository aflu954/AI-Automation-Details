Build a LinkedIn Job Alert Automation with n8n

## Client Scenario

A recruitment agency helps software engineers find relevant jobs. Every morning, recruiters manually search LinkedIn for newly posted jobs, copy the listings into a spreadsheet, and send them to candidates.

The client wants this process to be fully automated.

## Objective

Build an n8n workflow that automatically scrapes the latest LinkedIn jobs using Apify and stores them in Google Sheets.

## Requirements

Your workflow must include the following nodes:

* Webhook – Accept the following input:

* Job Title (e.g., Python Developer)

* Location (e.g., Bangladesh, Remote)

* Number of Jobs

* HTTP Request – Trigger an Apify LinkedIn Jobs Scraper actor using the Apify API.

* HTTP Request – Check the actor run status until it completes.

* HTTP Request – Retrieve the scraped dataset from Apify.

* Process the returned data.

Save the following information to *Google Sheets**:

* Job Title

* Company Name

* Location

* Posted Time

* Job URL

* Company URL (if available)

## Example Input

```json

{

"jobTitle": "Python Developer",

"location": "Remote",

"limit": 20

}

```

## Expected Output

A Google Sheet containing the latest LinkedIn job postings that match the requested criteria.

## Constraints

Use *Webhook** as the trigger.

Use *HTTP Request** nodes for all interactions with Apify.

* Do not use the Apify node.

* The workflow must wait for the scraping job to finish before fetching the dataset.

* Handle failed actor runs gracefully.

## Bonus Challenge

After saving the jobs to Google Sheets, use an AI node to generate a 2–3 sentence summary highlighting:

* The most common hiring companies.

* The most common locations.

* Any noticeable hiring trends.

## Deliverables

* Exported n8n workflow (.json)

* Google Sheet with scraped job data

* A README explaining:

* How to configure the Apify API token

* How to trigger the webhook

* Sample webhook payload

* Screenshot of the final Google Sheet

