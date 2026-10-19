# AI Resume Screening & Job Matching System

An AI-powered resume screening tool built with Python and Groq LLMs that parses resumes, analyzes job descriptions, evaluates candidate-job compatibility, and ranks candidates based on their estimated match scores.

## Overview

Recruitment teams often receive multiple resumes for a single job opening. This project automates the initial screening process by extracting candidate information and comparing it with job requirements using a Large Language Model (LLM).

## Features

- **Job Description Analysis:** Extracts role requirements, skills, education, and responsibilities into structured data.
- **Resume Parsing:** Reads PDF and DOCX resumes and extracts candidate information.
- **AI-Powered Matching:** Compares candidate profiles with job requirements.
- **Match Scoring:** Generates an estimated compatibility score from 0 to 100.
- **Candidate Ranking:** Displays the top and lowest-scoring candidates.
- **Structured Output:** Uses Pydantic models to organize and validate extracted data.

## Tech Stack

- **Language:** Python
- **LLM Provider:** Groq API
- **Model:** `openai/gpt-oss-20b`
- **Data Validation:** Pydantic
- **PDF Processing:** pypdf
- **Word Documents:** python-docx
- **Environment Management:** uv
- **Configuration:** python-dotenv

## Project Structure

```text
AI-Resume-Screening/
├── resumes/              # Local resume files (not committed)
├── src/
│   └── project/
│       └── __init__.py
├── project1.py            # Main application
├── .env                   # API key (not committed)
├── .env.example           # Example environment configuration
├── .gitignore
├── .python-version
├── pyproject.toml
├── uv.lock
└── README.md
```

## Prerequisites

- Python 3.11 or a compatible version
- Git
- uv package manager
- A Groq API key

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/lordmoon-dev/AI-Resume-Screening.git
cd AI-Resume-Screening
```

### 2. Install dependencies

```bash
uv sync
```

### 3. Configure environment variables

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key_here
```

Get your API key from the [Groq Console](https://console.groq.com/).

**Security:** Never commit your real API key or share your `.env` file.

### 4. Add resumes

Create a `resumes` folder in the project root and add the resumes you want to analyze in PDF or DOCX format.

### 5. Run the application

```bash
uv run python project1.py
```

Alternatively, activate your virtual environment and run:

```bash
python project1.py
```

## How It Works

1. Reads the job description.
2. Extracts structured job requirements using the LLM.
3. Reads candidate resumes in PDF or DOCX format.
4. Extracts candidate skills, experience, education, projects, and certifications.
5. Compares each candidate's profile with the job requirements.
6. Generates estimated match scores and explanations.
7. Ranks candidates and displays the top and lowest matches.

## Example Output

```text
Processing... candidate_resume.pdf
Score: 75.0

Top 2 candidates:
Candidate A - 75.0 %
Candidate B - 60.0 %

Lowest 2 candidates:
Candidate C - 35.0 %
Candidate D - 33.0 %
```

*Scores above are illustrative examples, not guaranteed results.*

## Limitations

- Match scores are LLM-generated estimates, not objective measures of candidate quality.
- Results may vary between runs and can contain extraction or reasoning errors.
- Scanned PDFs may require OCR if text extraction returns no content.
- Resume quality and formatting can affect parsing accuracy.
- Human review is necessary before making recruitment decisions.

## Future Improvements

- Build a web dashboard for HR teams.
- Export candidate rankings to CSV or Excel.
- Add OCR support for scanned resumes.
- Improve scoring consistency using stricter validation and explicit evaluation criteria.
- Add batch processing, logging, and error handling.

## Responsible Use

Use this tool to assist, not replace, human recruitment decisions. Evaluate candidates fairly, protect personal information, and review AI-generated assessments before taking action.

## Author

**lordmoon-dev**

GitHub: [@lordmoon-dev](https://github.com/lordmoon-dev)

---

If you find this project useful, consider giving the repository a ⭐ on GitHub.