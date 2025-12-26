# Resume Parser & Candidate Management System - n8n Workflow

## Overview

An automated resume parsing and candidate management system built with n8n that extracts structured information from PDF resumes using Google Gemini AI, evaluates candidates against job requirements, and sends automated email notifications to shortlisted and rejected candidates via SMTP.

## Features

- **PDF Resume Processing**: Automatically extracts text from PDF resume files
- **AI-Powered Extraction**: Uses Google Gemini AI for intelligent information extraction
- **Candidate Evaluation**: Automatically evaluates candidates against job descriptions
- **Automated Email Notifications**: Sends personalized emails to candidates via SMTP
  - Shortlisted candidates receive acceptance notifications
  - Rejected candidates receive professional rejection emails
- **Structured Output**: Returns standardized JSON format with candidate details
- **Batch Processing**: Supports processing multiple resumes simultaneously
- **Error Recovery**: Includes fallback mechanisms when extraction fails

## Architecture

```
[Resume Upload] → [Text Extraction] → [AI Processing] → [Data Parser] → [Candidate Evaluation] → [Email Notification]
                                                                               ↓                        ↓
                                                                          [Shortlisted]           [Rejected]
                                                                               ↓                        ↓
                                                                         [SMTP Email]            [SMTP Email]
```

### Workflow Components

1. **File Download**: Retrieves resume PDF from source
2. **Text Extraction**: Converts PDF to plain text
3. **AI Processing**: Sends text to Gemini for structured extraction
4. **Data Parsing**: Validates and formats the AI response
5. **Candidate Evaluation**: Matches candidate qualifications with job requirements
6. **Email Dispatch**: Sends appropriate notifications via SMTP to candidates

## Prerequisites

- n8n instance (self-hosted or cloud)
- Google Gemini API key
- SMTP server credentials (Gmail, Outlook, or custom SMTP)

## Setup

1. Obtain a Google Gemini API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Configure SMTP credentials for email delivery
3. Import the workflow into your n8n instance
4. Configure the Gemini API and SMTP credentials
5. Activate the workflow

## Usage

1. Upload or provide a resume PDF file with job description
2. The workflow executes automatically:
   - Extracts candidate information
   - Evaluates against job requirements
   - Determines shortlist or rejection status
   - Sends appropriate email notification
3. Retrieve structured JSON output containing candidate information and status

## Output

The system extracts and returns:
- Candidate name and contact information
- Years of experience
- Education background
- Skills and competencies
- Previous companies
- Key achievements
- Relevant experience summary
- Evaluation status (Shortlisted/Rejected)
- Email delivery status

## Email Notifications

### Shortlisted Candidates
- Receive personalized acceptance email
- Include next steps in the hiring process
- Sent via configured SMTP server

### Rejected Candidates
- Receive professional rejection notification
- Maintain positive candidate experience
- Sent via configured SMTP server

## Limitations

- PDF text extraction quality depends on document formatting
- Complex multi-column layouts may affect extraction accuracy
- Handwritten or image-based resumes require OCR preprocessing
- Email delivery depends on SMTP server configuration and availability

## License

This workflow is provided as-is for educational and commercial use.

---

**Built with n8n** | **Powered by Google Gemini AI** | **Email via SMTP**
