Job Application Automation

Project Overview

This project automates the process of tailoring resumes and cover letters to individual job listings, using n8n for orchestration, Apify for job scraping, and OpenAI for content generation.

Workflow

* Source: Job listings saved to a Google Sheet (title, company, URL) as I find them on SEEK
* Scraping: Apify crawls each job URL and extracts title, company, location, and full description
* Content generation: OpenAI (GPT-4.1) rewrites my master resume's summary, skills, and work experience bullets to match each listing's language and requirements, and generates a tailored four-paragraph cover letter
* Document assembly: Google Docs templates are copied and auto-filled via the Google Docs batchUpdate API
* Tracking: Final resume and cover letter links are written back to the Google Sheet against each job

Files

* `SEEK-AI_Tailored_Resume_Cover_Letter.json` - Exported n8n workflow (API keys removed)

Tools Used

* n8n: Workflow orchestration
* Apify: Job listing web scraping
* OpenAI API (GPT-4.1): Resume and cover letter content generation
* Google Sheets API: Job tracking and task queue
* Google Docs API: Template-based document generation

How to Use

1. Import `SEEK-AI_Tailored_Resume_Cover_Letter.json` into your own n8n instance
2. Connect your own Apify, OpenAI, and Google credentials
3. Point it at your own master resume, cover letter, and work history docs
4. Add job listings to a tracking sheet and run the workflow

Status: In Use

Currently used to manage my own job applications. Built to solve a real problem: manually tailoring every resume and cover letter was slow and inconsistent, so I automated it.

Last updated: 22/09/2026
