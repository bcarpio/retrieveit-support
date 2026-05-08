# Clio Integration

Connect a Clio account to RetrieveIt.AI to sync legal practice management data — matters, documents, activities, communications, contacts, calendar entries, and tasks — into a workspace.

> **Clio data is privileged client information.** Workspace admins are responsible for confirming they're authorized to share their firm's Clio data with RetrieveIt.AI before connecting.

## Overview

The Clio integration lets you:
- Connect to your firm's Clio account
- Pick which **resource types** to sync (matters, documents, activities, etc.)
- Search Clio data alongside your other workspace content in chat
- Keep everything synced automatically (hourly)

The integration is read-only — RetrieveIt.AI never writes back to Clio.

## Setting Up Clio Integration

### Step 1: Connect Your Account

1. Go to your **Workspace** in the Dashboard
2. Find the **Clio Integration** tile
3. Click **Connect Clio**
4. Sign in with your Clio credentials
5. Grant RetrieveIt.AI read access to the Clio resources you want to sync

### Step 2: Select Resource Types

After authorizing, you'll land on a resource type picker. Pick which categories of Clio data to sync into this workspace:

| Resource Type | What it pulls |
|---|---|
| **Matters** | Case files and metadata (display number, status, client, responsible attorney, description) |
| **Documents** | Files attached to matters (PDFs, Word docs, etc.) |
| **Activities** | Time entries and notes (date, hours, matter, user) |
| **Communications** | Emails, calls, internal notes |
| **Contacts** | Clients and related parties |
| **Calendar entries** | Events and deadlines |
| **Tasks** | To-do items with status, due dates, assignees |

Pick any combination, then click **Save & Start Sync**.

### Step 3: Initial Sync

After saving:
1. RetrieveIt.AI pulls every item of each selected type from your Clio account
2. Each item becomes a searchable record in your workspace
3. Documents are downloaded; everything else is rendered as a structured summary
4. Once complete, your Clio data is searchable in Chat

The first sync of a large Clio account can take a while — the connection card shows the running file count.

## Managing Your Connection

### Changing Resource Types

To add or remove resource types:

1. Open the workspace and find the Clio connection
2. Click **Configure**
3. Check or uncheck resource types
4. Click **Save**

Newly checked types sync on the next run. Unchecked types have their existing data deleted from RetrieveIt.AI on the next sync.

### Manual Sync

Click **Sync Now** to immediately pull new and changed Clio items.

### Automatic Sync

Clio connections sync automatically **every hour**. Per-type cursors mean each sync only pulls items modified since the last run, so syncs stay fast.

### Re-authentication

If your Clio session is rejected (revoked, password change, etc.), the connection's status flips to **Re-auth needed** and a banner appears in the integration panel. Click **Reconnect** to re-run the sign-in flow. Resource type selections and sync history are preserved.

### Switching Clio Accounts

Each workspace can be connected to **one Clio account at a time**. If you try to OAuth a different Clio account against a workspace that already has a connection, the flow rejects with an error. Disconnect the existing connection first, then connect the new account.

### Disconnect

Click the trash icon on the connection card. You'll be asked to confirm. On confirm:

- The connection is removed from RetrieveIt.AI immediately
- Your stored Clio access token is deleted
- All synced Clio data is queued for deletion from the workspace

Files remain untouched in Clio.

## What Gets Indexed

Only the resource types you've selected. Each item becomes a markdown record (or, for documents, the original file) inside the workspace.

### Matters
A summary card per matter — display number, client, responsible attorney, description, and custom fields.

### Documents
The original file bytes (PDF, Word, etc.) — same handling as documents from Drive or SharePoint.

### Activities, Communications, Contacts, Calendar Entries, Tasks
A structured summary per item with the relevant fields, including back-references to the matter when applicable.

## Frequently Asked Questions

### I created a new matter in Clio. When will it be searchable?

New and updated items are picked up automatically on the next hourly sync. Click **Sync Now** to pull immediately.

### I deleted a matter in Clio. Is it removed from RetrieveIt.AI?

Yes. The next sync notices the deletion and removes the item from the workspace.

### Can I filter within a resource type? (e.g., only matters where status = open)

Not in v1. The integration syncs all items of each selected resource type. If you want to limit scope, only select the resource types you actually need.

### I picked Documents but a specific file isn't appearing.

Files larger than 200 MB are skipped at processing time. Otherwise, check that the document is attached to a matter — the integration pulls documents that live in Clio's document store.

### I'm seeing "Clio is throttling requests" — what's going on?

Clio rate-limits API requests per account. The integration retries with backoff, but if your Clio account has heavy API usage from other tools the limit may be saturated. Try again in a minute, or click **Sync Now** later.

### Does the integration write back to Clio?

No. RetrieveIt.AI only requests read scopes (`matters:read`, `documents:read`, `activities:read`, `communications:read`, `contacts:read`, `calendar_entries:read`, `tasks:read`). We never modify or delete anything in Clio.

## Privacy & Security

- Clio data is treated as confidential — encrypted at rest and in transit
- Your Clio access token is stored encrypted with AWS KMS
- RetrieveIt.AI is read-only; nothing is ever written back to Clio
- Disconnect anytime to remove all synced Clio data from the workspace
- Clio permissions are honored — you can only sync data your account has access to in Clio
