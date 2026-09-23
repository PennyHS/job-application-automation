# Job Application Automation

An n8n workflow that tailors my resume and cover letter to each job listing, using Apify for scraping and OpenAI for content generation.

## About

Tailoring every resume and cover letter by hand was slow and inconsistent, so I automated it. I currently use this workflow for my own job applications.

## How It Works

1. **Source** – I save job listings I find on SEEK to a Google Sheet (title, company, URL).
2. **Scraping** – Apify crawls each job URL and extracts the title, company, location, and full description.
3. **Content generation** – OpenAI (GPT-4.1) rewrites the summary, skills, and experience bullets from my master resume to match each listing, and writes a four-paragraph cover letter.
4. **Document assembly** – Google Docs templates are copied and filled in using the Google Docs `batchUpdate` API.
5. **Tracking** – Links to the finished resume and cover letter are written back to the Google Sheet next to each job.

## Built With

- **n8n** – workflow orchestration
- **Apify** – job listing scraping
- **OpenAI API (GPT-4.1)** – resume and cover letter generation
- **Google Sheets API** – job tracking and task queue
- **Google Docs API** – template-based document generation

## Files

- `SEEK-AI_Tailored_Resume_Cover_Letter.json` – exported n8n workflow (API keys removed)

## How to Use

1. Import `SEEK-AI_Tailored_Resume_Cover_Letter.json` into your own n8n instance.
2. Connect your own Apify, OpenAI, and Google credentials.
3. Point the workflow at your own master resume, cover letter, and work history docs.
4. Add job listings to the tracking sheet and run the workflow.
