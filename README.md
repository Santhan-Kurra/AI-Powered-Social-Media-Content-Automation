# AI-Powered Social Media Content Automation

An AI-powered workflow automation project built using **n8n, Google Gemini, Google Sheets, LinkedIn and Buffer API**.

This project automates the process of converting article content into platform-specific social media posts. It generates professional LinkedIn content and engaging X (Twitter) posts, reducing repetitive manual work.

## Project Overview

Managing social media updates manually involves reading articles, summarizing information, writing posts for different platforms and publishing them individually.

This project simplifies the process using an automated AI workflow.

Users add article information to Google Sheets, which triggers the n8n workflow. Google Gemini analyzes the content and generates customized posts for LinkedIn and X.

LinkedIn posts are published through the LinkedIn integration, while X posts are added to Buffer's publishing queue for automatic scheduling.

## Key Features

- **Google Sheets Integration:** Uses new spreadsheet entries to trigger the workflow.
- **AI Article Summarization:** Uses Google Gemini to extract important insights from article content.
- **LinkedIn Content Generation:** Creates structured, professional LinkedIn posts.
- **X Content Generation:** Generates short and engaging X posts.
- **Automated LinkedIn Publishing:** Publishes generated content to LinkedIn.
- **X Post Scheduling:** Uses Buffer API to add generated posts to the X publishing queue.
- **Workflow Automation:** Connects multiple services through n8n without building a complete application from scratch.

## Workflow Architecture

```text
Google Sheets Trigger
        |
        v
Gemini - Article Summarization
        |
        +----------------------+
        |                      |
        v                      v
Generate LinkedIn          Generate X
        |                      |
        v                      v
LinkedIn Create Post     Buffer API
                               |
                               v
                         X Publishing Queue
                               |
                               v
                      Automatic X Publishing
```

## Technologies Used

| Technology | Purpose |
|---|---|
| n8n | Workflow automation |
| Google Sheets | Article input |
| Google Gemini | AI summarization and content generation |
| LinkedIn API integration | LinkedIn publishing |
| Buffer API | X post scheduling and publishing |
| HTTP Request | API communication |
| OAuth 2.0 | Account authentication |

## Project Structure

```text
ai-powered-social-media-automation/
│
├── workflow/
│   └── social-media-automation.json
│
├── screenshots/
│   ├── workflow-overview.png
│   ├── linkedin-publishing.png
│   └── x-buffer-scheduling.png
│
├── docs/
│   └── setup-guide.md
│
├── README.md
└── .gitignore
```

## How It Works

1. Add an article entry to the Google Sheet.
2. The Google Sheets Trigger starts the workflow.
3. Gemini summarizes the article and extracts important insights.
4. The workflow generates separate LinkedIn and X posts.
5. The LinkedIn integration publishes the LinkedIn post.
6. The Buffer API adds the X post to the connected X channel's publishing queue.
7. Buffer publishes the post according to the configured schedule.

## Setup Instructions

1. Import the workflow JSON file into an n8n instance.
2. Configure Google Sheets OAuth credentials.
3. Configure Google Gemini API credentials.
4. Connect the LinkedIn account and configure the required permissions.
5. Connect an X account to Buffer.
6. Configure Buffer API authentication in the HTTP Request node.
7. Update the Google Sheets document and worksheet references.
8. Test each workflow branch before activating the workflow.

**Note:** The uploaded workflow is a sanitized template. You must configure your own credentials, API keys, account connections and document IDs before running it.

## Screenshots

### Complete Workflow
![Workflow Overview](screenshots/workflow-overview.png)

### LinkedIn Publishing
![LinkedIn Publishing](screenshots/linkedin-publishing.png)

### X Post Scheduling through Buffer
![Buffer X Scheduling](screenshots/x-buffer-scheduling.png)

## Security

- API keys and OAuth secrets are not included in this repository.
- Store credentials securely using n8n's credential management.
- Never commit access tokens, passwords or private configuration data.

## Future Improvements

- Add Instagram and other social media platforms.
- Introduce human approval before publishing.
- Improve article extraction and summarization.
- Add duplicate article detection.
- Store publishing history and workflow execution status.
- Implement error notifications and retry mechanisms.

## Project Status

Completed – Core workflow tested with LinkedIn publishing and Buffer-based X post scheduling.

---

**Built as a practical project to explore AI-powered workflow automation and multi-platform content publishing.**
