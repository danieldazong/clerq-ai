# Clerq: AI Invoice Processor

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Status: Production](https://img.shields.io/badge/Status-Production-success.svg)

Clerq is an automated finance operations pipeline that ingests incoming vendor bills, extracts critical financial data using AI, prevents duplicate payments, and manages manager approvals entirely via email. It translates unstructured PDF chaos into a clean, deterministic, and auditable Google Sheets ledger.



## 🔗 Live Demo
- **Live Website:** N/A (Internal Finance Operations)
- **Deployment Platform:** n8n (Cloud/Self-Hosted)



## 📌 Project Overview
This repository contains the exported n8n workflow architectures, environment variables, and testing resources needed to deploy Clerq. It allows finance teams to scale back-office operations without increasing headcount by putting routine invoice processing on autopilot while enforcing strict threshold routing.

### Key Highlights
- **Automated PDF Ingestion:** Securely monitors inboxes, filtering out spam and isolating valid invoice attachments.
- **LLM Data Extraction:** Converts unstructured PDF text into strict, deterministic JSON payloads (vendor name, amounts, dates).
- **Duplicate Prevention:** Queries live Google Sheets data to block duplicate invoice numbers before processing continues.
- **1-Click Manager Approvals:** Pauses the automation to send secure HTML emails, capturing manager decisions via webhook without requiring software logins.



## 🛠 Tech Stack

| Category | Technology |
| :--- | :--- |
| **Workflow Engine** | n8n |
| **AI / LLM Extraction** | OpenAI API / Google Gemini |
| **Database / Audit Log** | Google Sheets API |
| **Intake & Notifications** | Gmail API |
| **Version Control** | Git & GitHub |



## 📁 Repository Structure

├── workflows/                     # Exported n8n workflow JSON files
│   ├── main_pipeline.json         # Core intake, extraction, and routing logic
│   ├── approval_callback.json     # Manager approval webhook handling
│   └── error_handler.json         # Fallback routing for failed extractions
├── docs/                          # Architecture diagrams and integration logs
│   ├── architecture_diagram.png
│   └── integration_status.md
├── samples/                       # Synthetic testing payloads
│   └── sample_invoices/           # Dummy PDFs for testing thresholds
├── tests/                         # Data validation logic
│   └── payload_validation_tests.js
├── .env.example                   # Template for OAuth credentials and API keys
└── README.md                      # Project documentation and setup guidelines



## 🚀 Getting Started

Follow these instructions to run a copy of the project locally for development or testing purposes.

### Prerequisites

- A modern web browser (Chrome, Edge, Firefox, Safari)
- [Node.js](https://nodejs.org/) installed (v18.x or later recommended, if using package managers)
- [Git](https://git-scm.com/) installed on your local machine
- An active n8n instance (Local desktop app or Cloud)

### Installation & Local Setup

1. **Clone the repository:**

git clone https://github.com/yourusername/clerq-invoice-processor.git
cd clerq-invoice-processor


2. **Configure Credentials:**
Review the `.env.example` file to see the necessary OAuth scopes for Google Drive/Gmail and Google Sheets. Set up these credentials securely within your n8n instance.

3. **Import Workflows into n8n:**
Navigate to your n8n workspace, create a new workflow, click the top-right menu, and select **Import from File**. Select `main_pipeline.json` from the `workflows/` directory.

4. **Run the local development server:**
Ensure your Google Sheets audit log is created with the proper headers. Click **Listen for Test Event** in n8n and email a sample PDF from the `samples/sample_invoices/` directory to trigger the pipeline.



## 📬 Contact & Connect

- **Developer:** Daniel Dazong
- **LinkedIn:** https://www.linkedin.com/in/danieldazong
- **GitHub:** https://github.com/danieldazong
- **Email:** danieldazong08@gmail.com
