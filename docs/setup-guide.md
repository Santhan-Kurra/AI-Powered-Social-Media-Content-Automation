# Setup Guide

This guide explains how to import and configure the AI-Powered Social Media Content Automation workflow in n8n.

## 1. Prerequisites

- n8n account
- Google account and Google Sheets
- Google Gemini API key
- LinkedIn account with API access
- Buffer account connected to an X account
- Buffer API key

## 2. Import the Workflow

1. Download `social-media-automation.json` from the workflow folder.
2. Open your n8n workspace.
3. Select Import from File.
4. Choose the downloaded JSON file.
5. Open the imported workflow.

## 3. Configure Google Sheets

1. Create a Google Sheet.
2. Add a column named `newslinks`.
3. Add article URLs in new rows.
4. Open the Google Sheets Trigger node.
5. Connect your Google account.
6. Select your spreadsheet and worksheet.

## 4. Configure Google Gemini

1. Generate an API key through Google AI Studio.
2. Open each Google Gemini Chat Model node.
3. Create or select your Gemini credentials.
4. Save and test each model connection.

## 5. Configure LinkedIn

1. Create or configure a LinkedIn Developer App.
2. Enable the required Share on LinkedIn permission.
3. Configure OAuth authentication in n8n.
4. Select your LinkedIn account and personal profile.
5. Test publishing carefully.

## 6. Configure Buffer and X

1. Create a Buffer account.
2. Connect your X account to Buffer.
3. Generate a Buffer API key.
4. Open the Publish X Post via Buffer HTTP Request node.
5. Configure the Authorization header using your own Buffer API key.
6. Replace the channel ID placeholder with your Buffer X channel ID.
7. Configure your Buffer publishing schedule.

## 7. Test the Workflow

1. Test the Google Sheets Trigger.
2. Verify article summarization.
3. Check LinkedIn content generation.
4. Check X content generation.
5. Test LinkedIn publishing.
6. Test Buffer post scheduling.
7. Verify the scheduled post in your Buffer dashboard.

## 8. Activate the Workflow

After successful testing:

1. Save the workflow.
2. Check that no nodes are incomplete.
3. Publish the workflow in n8n.
4. Verify that the Google Sheets trigger is active.

## 9. Security Notes

- Never upload API keys or OAuth secrets to GitHub.
- Configure credentials using your own accounts.
- Replace all placeholder IDs with your own values.
- Keep sensitive credentials inside n8n.

## 10. Current Workflow Limitation

The current summarization node receives the article URL from Google Sheets. It does not independently fetch and extract the complete webpage content. For reliable summarization of arbitrary article URLs, add an article-fetching and text-extraction step before Gemini.

---

**Project:** AI-Powered Social Media Content Automation  
**Author:** Santhan Kurra
