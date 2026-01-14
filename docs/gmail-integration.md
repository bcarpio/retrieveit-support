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

These system labels are always excluded:
- **SPAM** - Unwanted emails
- **TRASH** - Deleted emails
- **DRAFT** - Unfinished drafts

Gmail's category tabs (Promotions, Social, Updates, Forums) are **not** excluded. Emails in these tabs are still in your Inbox - the tabs are just a visual organization feature in Gmail.

## Tips

- Start with just INBOX and SENT, add more labels if needed
- Use a shorter date range initially to test
- Create Gmail labels to organize emails you want searchable
- Review your label selection periodically

## Frequently Asked Questions

### What does "Sync Now" do?

**Sync Now** performs an incremental sync - it only fetches new emails that arrived since the last sync. It does not re-download all your emails.

### I added new labels to my configuration. Will old emails with those labels be synced?

No. When you add new labels to an existing configuration, only **new emails** from those labels (received after you save the config) will be synced. To include older emails from the new labels, you need to do a full resync (see below).

### How do I force a full resync of all emails?

To resync all emails from scratch:
1. Click **Disconnect** to remove the Gmail connection
2. Wait for all data to be deleted (this may take a minute)
3. Click **Connect Gmail** to reconnect
4. Configure your labels and date range
5. Click **Save & Start Sync**

This will import all emails matching your configuration fresh.

### I changed my date range. Will it sync older emails now?

Similar to labels - changing the date range only affects new syncs going forward. To include emails from the expanded date range, do a full resync by disconnecting and reconnecting.

### How often does automatic sync happen?

Emails are synced automatically every hour for active connections.

### Why are some emails missing?

Check these common causes:
- The email might be in a label you haven't selected
- The email might be older than your configured date range
- The email might still be syncing (large inboxes take time)

### Can I search email attachments?

Yes! Supported attachment types (PDF, Word, Excel, PowerPoint, text files) are extracted and indexed. You can search for content within attachments.

## Privacy & Security

- RetrieveIt.AI only accesses emails from labels you explicitly select
- Email content is processed and stored securely
- You can disconnect and delete all data at any time
- We never send emails on your behalf
