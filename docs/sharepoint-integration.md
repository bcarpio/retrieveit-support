# SharePoint Integration

Connect your SharePoint sites to RetrieveIt.AI to search documents and site pages alongside your other content.

## Overview

The SharePoint integration allows you to:
- Import documents from selected SharePoint sites
- Search document content and site pages
- Keep content synced automatically (hourly)
- Control exactly which sites are indexed

## Setting Up SharePoint Integration

### Step 1: Connect Your Account

1. Go to your **Workspace** in the Dashboard
2. Find the **SharePoint Integration** section
3. Click **Connect SharePoint**
4. Sign in with your Microsoft account
5. Grant RetrieveIt.AI permission to read your SharePoint sites

### Step 2: Select Sites

After connecting, choose which sites to sync:

1. Click **Configure** on your SharePoint connection
2. You'll see a list of SharePoint sites you have access to
3. Select the sites you want to index
4. Optionally enable **Include Pages** to index SharePoint site pages (not just documents)
5. Click **Save**

### Step 3: Initial Sync

After saving your configuration:
1. The initial sync starts automatically
2. Wait for documents to be processed (may take several minutes for large sites)
3. Once complete, documents are searchable in Chat

## Managing Your Connection

### Manual Sync

Click **Sync Now** to immediately pull in new or changed documents. Use this when you've just uploaded new files and want them searchable right away.

### Automatic Sync

SharePoint connections sync automatically **every hour**. New documents, updates, and deletions are detected and processed.

### Adding New Sites

To add a new SharePoint site to an existing connection:

1. Go to your workspace and find the SharePoint connection
2. Click **Configure**
3. Select the additional site(s) from the list
4. Click **Save**
5. The new site will sync on the next automatic run, or click **Sync Now** for immediate sync

### Disconnect

Click **Disconnect** to remove the SharePoint connection. This deletes all synced documents and pages from the workspace.

## What Gets Indexed

### Documents
- **PDF files** - Full text extracted and searchable
- **Word documents** (.docx) - Full text extracted
- **Excel spreadsheets** (.xlsx) - Content extracted
- **PowerPoint presentations** (.pptx) - Text from slides
- **Text files** (.txt, .md, .csv) - Full content indexed

### Site Pages (optional)
When "Include Pages" is enabled:
- SharePoint site pages are indexed
- Page content and titles are searchable
- Updates to pages are synced automatically

## Frequently Asked Questions

### I just added a new SharePoint site. How do I make it searchable?

1. Go to your workspace and find the SharePoint connection
2. Click **Configure**
3. Select the new site from the list (it should appear automatically)
4. Click **Save**
5. Click **Sync Now** or wait for the next hourly sync

### I uploaded a new document. When will it be searchable?

Documents sync automatically every hour. To make it searchable immediately:
1. Go to your SharePoint connection
2. Click **Sync Now**

The document should be searchable within a few minutes after the sync completes.

### Why doesn't my new site appear in the list?

Make sure you have access to the site in SharePoint. RetrieveIt.AI can only see sites that your Microsoft account has permission to access. If you just got access, try:
1. Click **Configure** to refresh the site list
2. If it still doesn't appear, try disconnecting and reconnecting

### I deleted a document in SharePoint. Is it removed from RetrieveIt.AI?

Yes. Deleted documents are automatically removed during the next sync cycle (hourly, or when you click Sync Now).

### I renamed or moved a document. Will it update?

Yes. Document changes including renames, moves, and content updates are detected and synced automatically.

### How do I remove a site from syncing?

1. Click **Configure** on your SharePoint connection
2. Deselect the site you want to remove
3. Click **Save**

Documents from that site will be deleted from RetrieveIt.AI on the next sync.

### Can I sync specific folders instead of entire sites?

Currently, the integration syncs entire document libraries within selected sites. Folder-level filtering is not yet available.

### How often does automatic sync happen?

SharePoint content syncs automatically **every hour** for active connections.

## Privacy & Security

- RetrieveIt.AI only accesses sites you explicitly select
- Document content is processed and stored securely
- You can disconnect and delete all data at any time
- We use read-only access and never modify your SharePoint content
