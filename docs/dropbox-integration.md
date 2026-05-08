# Dropbox Integration

Connect a Dropbox account to RetrieveIt.AI to sync files from selected folders into a workspace.

## Overview

The Dropbox integration lets you:
- Connect a personal or Dropbox Business account
- Pick **specific folders** to sync into a workspace
- Keep folder content synced automatically (hourly)

You select which folders are indexed — Dropbox folders you don't pick are not visible to RetrieveIt.AI.

## Setting Up Dropbox Integration

### Step 1: Connect Your Account

1. Go to your **Workspace** in the Dashboard
2. Find the **Dropbox Integration** tile
3. Click **Connect Dropbox**
4. Sign in with your Dropbox account
5. Grant RetrieveIt.AI permission to read your Dropbox files

### Step 2: Select Folders

After connecting:

1. You'll land on the folder picker
2. Browse your Dropbox folder tree
3. Check the folders you want to sync
4. Click **Save & Start Sync**

You can pick a single folder, multiple folders, or top-level folders that include their subfolders.

### Step 3: Initial Sync

After saving:
1. RetrieveIt.AI pulls files from each selected folder
2. Supported file types are extracted and indexed
3. Once complete, content is searchable in Chat

The first sync of a large folder can take a while — check back on the connection card to see the file count grow.

## Managing Your Connection

### Adding or Removing Folders

To change which folders are synced:

1. Open the workspace and find the Dropbox connection
2. Click **Configure**
3. Check or uncheck folders in the picker
4. Click **Save**

Folders you uncheck have their files deleted from RetrieveIt.AI on the next sync. Newly added folders sync on the next automatic run, or click **Sync Now** for immediate sync.

### Manual Sync

Click **Sync Now** to immediately pull new and changed files from your selected folders.

### Automatic Sync

Dropbox connections sync automatically **every hour**. New files, edits, and deletions inside selected folders are detected and processed.

### Disconnect

Click **Disconnect** to remove the Dropbox connection. This deletes all synced documents from the workspace. Files remain untouched in your Dropbox.

## What Gets Indexed

For each selected folder:

- **PDF documents** — full text extracted
- **Word documents** (.docx) — full text extracted
- **Excel spreadsheets** (.xlsx) — content extracted
- **PowerPoint presentations** (.pptx) — text from slides
- **Text and Markdown files** (.txt, .md) — full content indexed
- **CSV files** — content indexed

Files in unsupported formats are skipped. Files larger than 200 MB are also skipped.

## Dropbox Business

If you're connecting a Dropbox Business (Team) account, you'll see both your personal folders and team folders you have access to. You can select either or both. The integration honors your Dropbox permissions — you can only sync folders you can already see in Dropbox.

## Frequently Asked Questions

### I added a new file to a synced folder. When will it be searchable?

New files in already-synced folders are picked up automatically on the next hourly sync. Click **Sync Now** to pull them immediately.

### I deleted a file from Dropbox. Is it removed from RetrieveIt.AI?

Yes. The next sync notices the file is gone and removes it from the workspace.

### I created a new folder in Dropbox. Why isn't it being synced?

Only folders you've explicitly checked in the configuration page are synced. To add the new folder:

1. Click **Configure** on your Dropbox connection
2. Find the new folder in the picker (refresh if it doesn't appear)
3. Check it
4. Click **Save**

### Can I sync only certain file types from a folder?

Not currently — when you select a folder, all supported files in that folder (and its subfolders) are synced. If you want finer-grained control, organize the files you want into a dedicated folder and sync just that one.

### How does RetrieveIt.AI handle nested folders?

Selecting a folder includes everything inside it, including subfolders. If you want one branch of a folder tree but not another, select only the specific subfolders you want.

### What about shared folders that other people own?

Folders that have been shared with you appear in the picker if you have read access. Selecting one syncs the current contents — but if the folder owner removes your access, the integration loses visibility on the next sync.

## Privacy & Security

- RetrieveIt.AI only accesses folders you explicitly select
- Document content is processed and stored securely
- We use read-only access — files in Dropbox are never modified or deleted
- You can disconnect at any time to remove all synced data
- Dropbox permissions are respected — you cannot sync folders you don't have access to
