# Look4Job

![Python](https://img.shields.io/badge/Python-3-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-App-009688?style=flat-square&logo=fastapi&logoColor=white)

Look4Job is a Python-based job search and resume matching application.
It automatically finds jobs from multiple job boards and ranks them based on how well they match a user's resume.

The system allows users to upload a resume (PDF), extract skills, search job platforms, and display the most relevant job listings.

---

## Features

- Upload resume in PDF format
- Automatically convert PDF resume to text
- Extract skills from resume
- Smart job search based on resume content
- Scrape jobs from multiple job websites
- Remove duplicate job listings
- Filter jobs based on experience level
- Rank jobs based on skill match
- Detect internship vs regular jobs
- Simple web interface

---

## Supported Job Sites

Look4Job collects jobs from multiple platforms including:

- LinkedIn
- Indeed
- ZipRecruiter
- Glassdoor
- Google Jobs
- Naukri
- Bayt
- BDJobs

Jobs from these sites are scraped concurrently for faster results.

---

## Project Structure

```text
look4job/
|-- __init__.py       Main job scraping engine
|-- web.py            FastAPI web application
|-- matcher.py        Resume parsing and job ranking logic
|-- model.py          Data models and job structures
|-- util.py           Utility functions
|-- exception.py      Custom exceptions
`-- requirements.txt  Project dependencies
```

---

## Tech Stack

Backend
- Python
- FastAPI

Data Processing
- Pandas
- NumPy
- Regex

Web Scraping
- Requests
- BeautifulSoup
- TLS Client

Resume Processing
- PyPDF

Web Templates
- Jinja2

---

## Installation

Clone the repository:

```bash
git clone https://github.com/tharunsridhar/look4job-app.git
cd look4job-app
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Run the Application

Start the server:

```bash
uvicorn web:app --reload
```

Open in browser:

```text
http://127.0.0.1:8000
```

---

## How It Works

1. User uploads a resume (PDF).
2. The system converts the PDF into text.
3. Skills are extracted from the resume.
4. A job search query is inferred from the resume.
5. Job listings are scraped from multiple job boards.
6. Jobs are filtered based on experience requirements.
7. Jobs are ranked based on skill matching and relevance.
8. The best matching jobs are displayed to the user.

---

## Job Ranking Logic

Jobs are ranked using multiple signals:

**Skill Match**
Counts how many skills from the resume appear in the job description.

**Experience Match**
Compares required experience with the candidate's experience.

**Title Relevance**
Filters out irrelevant roles such as sales or marketing.

**Seniority Rules**
Adjusts ranking based on titles like:
- Intern
- Junior
- Senior
- Lead

The final ranking score determines which jobs appear first.

---

## Input Requirements

Resume must be:

- PDF format
- Contain readable text (not scanned image only)

---

## Output

The application displays ranked job results with:

- Job Title
- Company
- Location
- Date Posted
- Match Score
- Matched Skills
- Experience Fit
- Job URL

---

## Future Improvements

Possible improvements:

- NLP based skill extraction
- Resume semantic analysis
- AI job recommendation system
- Resume-job embedding matching
- Automatic job application support

---

## Author

Tharun Sridhar Natarajan
