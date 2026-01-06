# Gmail Integration

Connect your Gmail account to RetrieveIt.AI to search your emails and attachments alongside your other documents.

## Overview

The Gmail integration allows you to:
- Import emails from selected labels/folders
- Search email content and attachments
- Keep emails synced automatically
- Control exactly which emails are indexed

## Setting Up Gmail Integration

### Step 1: Connect Your Account

1. Go to your **Workspace** in the Dashboard
2. Find the **Gmail Integration** section
3. Click **Connect Gmail**
4. Sign in with your Google account
5. Grant RetrieveIt.AI permission to read your emails

### Step 2: Configure Labels

After connecting, configure which emails to sync:

1. Click **Configure** on your Gmail connection
2. Select which **labels** to include:
   - **INBOX** - Your main inbox
   - **SENT** - Emails you've sent
   - **Custom labels** - Any labels you've created
3. Choose how far back to sync (e.g., last 30, 60, 90 days)
4. Click **Save Configuration**

### Step 3: Initial Sync

After saving your configuration:
1. Click **Sync Now** to start the initial import
2. Wait for emails to be processed (may take several minutes)
3. Once complete, emails are searchable in Chat

## Managing Your Connection

### Manual Sync
Click **Sync Now** to pull in new emails since the last sync. Automatic syncs also happen periodically.

### Update Configuration
Click **Configure** to change which labels are synced or adjust the date range.

### Disconnect
Click **Disconnect** to remove the Gmail connection. This deletes all synced emails and attachments from the workspace.

## What Gets Indexed

- **Email body** - The text content of emails
- **Subject lines** - Email subjects are searchable
- **Attachments** - Supported file types are extracted and indexed
- **Metadata** - Sender, recipients, dates

## Labels Excluded by Default

These system labels are excluded to avoid noise:
- SPAM
- TRASH
- DRAFT
- Promotions, Social, Updates, Forums (category tabs)

You can still manually include them if needed.

## Tips

- Start with just INBOX and SENT, add more labels if needed
- Use a shorter date range initially to test
- Create Gmail labels to organize emails you want searchable
- Review your label selection periodically

## Privacy & Security

- RetrieveIt.AI only accesses emails from labels you explicitly select
- Email content is processed and stored securely
- You can disconnect and delete all data at any time
- We never send emails on your behalf
