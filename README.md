AI Resume Screening Agent
An automated, agentic workflow built in n8n that streamlines the recruitment process. The system captures application data, securely manages files via Google Drive, extracts and processes resume details using an AI Agent powered by Google Gemini, and automatically handles candidate communication and data tracking.

🚀 Workflow Overview
The workflow is broken down into four primary logical stages:

Data Ingestion & Extraction (Green Zone)

Receives incoming candidate data via a POST Webhook (Application data).

Uploads and downloads the resume file using Google Drive.

Extracts text content from both the candidate's resume and the initial job description using PDF extraction nodes.

AI Processing & Decision Making (Orange Zone)

Passes the extracted text data to an advanced AI Agent node.

The agent uses the Google Gemini Chat Model along with custom memory and tools to evaluate the candidate's fit against the job requirements.

A JavaScript code node processes or formats the AI agent's structured response.

Automation & Integration (Purple Zone)

Gmail Integration: Automatically sends a personalized email update to the applicant based on the AI's evaluation.

Data Logging: Appends the final evaluation metrics and candidate status directly into a database or spreadsheet row (e.g., Google Sheets, Airtable, or Supabase).

🛠️ Architecture & Nodes Used
Webhook Trigger: Application data (POST)

Google Drive: Upload Resume, Download file, Initial Job (download)

File Operations: Extract from File & Extract File (PDF to Text conversion)

Advanced AI:

AI Agent (Root node)

Google Gemini Chat Model

Associated Memory and Tool sub-nodes

Data Transformation: Code in JavaScript

Communication: Gmail (Send a message)

Storage: Database / Spreadsheet integration (Create a row)

📋 Prerequisites & Setup
Before importing this workflow into your n8n instance, ensure you have configured the following credentials and environment variables:

1. Credentials Required
Google Drive OAuth2 API: For file uploads and downloads.

Google Gemini API Key: To power the AI Agent reasoning and analysis.

Gmail OAuth2 API: To send automated candidate emails safely.

Target Integration Credentials: For whichever service hosts your candidate database tracker (e.g., Google Sheets, Postgres, etc.).

2. Environment Setup
Ensure your n8n instance has file system access or binary data properties properly configured to handle PDF text extraction.

Configure the webhook URL in your external application platform to point to the Application data webhook node.

🔧 How to Import & Run
Copy the raw JSON file of this workflow.

In your n8n dashboard, click on Workflows > Add Workflow (or open a blank canvas).

Press Ctrl + V (or Cmd + V on Mac) to paste the workflow directly onto the canvas.

Open each node to map your specific credentials and adjust any hardcoded folder/file IDs.

Click Execute workflow to test it end-to-end with a sample payload.

Switch the toggle from Development to Active to put it into production.

📝 License
This project is licensed under the MIT License - feel free to customize and expand it for your own automated HR pipelines.
