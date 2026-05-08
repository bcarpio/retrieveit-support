# Google Drive Integration

Connect Google Drive to RetrieveIt.AI to make specific Drive files searchable in chat.

## Overview

The Google Drive integration lets you:
- Pick **individual files** from your Drive to sync into a workspace
- Search Google Docs, Sheets, Slides, and uploaded files
- Add or remove files from the sync set whenever you want

**Important:** RetrieveIt.AI does **not** sync your entire Drive. You browse your Drive in a file picker and select the specific files you want indexed. Only those files (and any updates to them) are pulled into the workspace.

## Setting Up Google Drive Integration

### Step 1: Connect Your Account

1. Go to your **Workspace** in the Dashboard
2. Find the **Google Drive Integration** tile
3. Click **Connect Google Drive**
4. Sign in with your Google account
5. Grant RetrieveIt.AI permission to access the Drive files you select

### Step 2: Select Files

After connecting, you'll land on the configuration page:

1. Click **Add Files** to open the Google Drive file picker
2. Browse your Drive — double-click a folder to open it, then select files inside
3. You can select multiple files at once
4. Click **Select** in the picker to add them to your sync list
5. Repeat as many times as you need to build out the full set
6. When the list looks right, click **Save & Start Sync**

### Step 3: Initial Sync

After saving:
1. RetrieveIt.AI pulls each selected file
2. Supported file types are converted to text and indexed
3. Once complete, content is searchable in Chat

## Managing Your Connection

### Adding Files Later

To add more files to an existing connection:

1. Open the workspace and find the Google Drive connection
2. Click **Configure**
3. Click **Add Files** and select more files in the picker
4. Click **Save**
5. The new files sync on the next automatic run, or click **Sync Now** for immediate sync

### Removing Files

To stop syncing a file:

1. Click **Configure** on your Google Drive connection
2. Find the file in the **Selected Files** list
3. Click the remove icon next to it
4. Click **Save**

The file is deleted from RetrieveIt.AI on the next sync.

### Manual Sync

Click **Sync Now** to immediately pull updates to your selected files. Use this when you've just edited a Google Doc and want the new content searchable right away.

### Automatic Sync

Selected files sync automatically **every hour**. Edits, additions, and deletions to those specific files are detected and processed.

### Disconnect

Click **Disconnect** to remove the Google Drive connection. This deletes all synced documents from the workspace. Files remain untouched in your Drive.

## What Gets Indexed

Only files you've explicitly added to the sync list. For each:

### Google Workspace Files
- **Google Docs** — converted to text
- **Google Sheets** — cell content extracted
- **Google Slides** — slide text extracted

### Uploaded Files
Files in your Drive in supported formats:
- PDF documents
- Microsoft Office files (Word, Excel, PowerPoint)
- Text and Markdown files
- Images with text (OCR may be limited)

## Why Per-File Selection?

Earlier versions of this integration synced entire folders or the whole Drive. We changed to per-file selection because:

- **Privacy** — you don't accidentally sync personal files mixed in with work files
- **Cost** — workspaces only carry the storage and indexing cost of files you actually want searchable
- **Clarity** — the sync set is exactly what you picked, with no surprises about what got pulled in

If you previously had folder-level sync, your existing files are still synced. The new files you add use the per-file picker.

## Frequently Asked Questions

### I added a new file to my Drive. Will it sync automatically?

No. Only files you explicitly add to the sync list are pulled. Click **Configure**, **Add Files**, pick the new file, and **Save**.

### I edited a file that's already in the sync list. When will the changes appear?

Edits to files already in the sync list are picked up automatically on the next hourly sync. Click **Sync Now** to pull them immediately.

### I deleted a file from my Drive. Is it removed from RetrieveIt.AI?

Yes. The next sync notices the file is gone and removes it from the workspace.

### Can I sync an entire folder at once?

Not in the picker — you select files individually. To approximate a folder sync, open the folder in the picker, use **Select All** or hold Shift to multi-select, then **Select** to add them all.

### How do I see what's currently synced?

The **Configure** page shows the **Selected Files** list — every file currently being synced. Use this to audit what RetrieveIt.AI has access to.

## Privacy & Security

- RetrieveIt.AI only reads files you explicitly add via the picker
- We don't modify or delete any files in your Drive
- Content is processed and stored securely
- Disconnect anytime to remove all synced data
- Your Drive permissions are still respected — you can only sync files you have access to
