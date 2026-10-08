# AI Job Application Agent

An automated job-application assistant built with Python and the Groq API (Llama 3.3 70B). It reads your master CV, scores how well you match each target job, tailors your CV and cover letter for that role, and logs everything to a Google Sheet.

## Features

- **Match scoring:** rates your CV against each job, estimates acceptance chance, and suggests interview-prep topics
- **CV tailoring:** rewrites your summary, bullets, and skills to fit the job's keywords, without inventing qualifications
- **Cover letters:** writes a role-specific cover letter for each job
- **PDF and DOCX output:** saves print-ready and editable files for every application
- **Google Sheets tracking:** logs each application and skips duplicates

## Tech Stack

Python, Groq API, ReportLab, python-docx, pypdf, gspread

## Project Structure

```
├── main.py              # Main script (CV parsing, job loop, Sheets logging)
├── groq_client.py       # Groq API calls (scoring, CV tailoring, cover letters)
├── doc_generator.py     # PDF and DOCX file generation
├── my-cv.pdf            # Your master CV (input)
├── linkedin_ai_jobs.json# Job listings (input)
├── requirements.txt     # Dependencies
└── outputs/             # Generated CVs and cover letters, one folder per job
```

## Setup

1. Clone the repo and install dependencies:
```
   pip install -r requirements.txt
```
2. Create a `.env` file in the project folder:
```
   GROQ_API_KEY=your_groq_api_key
```
3. Replace `my-cv.pdf` with your own CV.
4. (Optional) For Google Sheets logging, set your sheet ID in `main.py` and add your Google OAuth or service-account credentials JSON file to the project folder.

## Usage

```
python main.py
```

Tailored CVs and cover letters are saved in the `outputs/` folder.

## Notes

- Never commit your `.env` file or credential JSON files.
- Review all generated documents before sending them to employers.

## Credits

Based on [AIwithhassan/AI-Job-Hunt-Agent](https://github.com/AIwithhassan/AI-Job-Hunt-Agent).
