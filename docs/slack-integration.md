# Slack Integration

Connect a Slack workspace to RetrieveIt.AI to sync messages, threads, and files from selected channels into a workspace.

> **Privacy note — please read first.** Slack messages can contain private business information. The boundary for what RetrieveIt.AI can see is **the channels you explicitly invite the bot to AND select to sync**. Direct messages are never accessed. If syncing channel messages doesn't fit your team's data-sharing policy, don't connect this integration.

## Overview

The Slack integration lets you:
- Connect a Slack workspace via the Slack app install flow
- Pick which **channels** to sync into a RetrieveIt workspace
- Search synced Slack messages, threaded replies, and shared files in chat
- Keep selected channels synced automatically (hourly)

The integration is read-only — RetrieveIt.AI never posts, reacts, edits, or deletes anything in Slack.

## What Gets Synced (and What Doesn't)

### Synced
- **Messages** in channels the bot is in AND you've selected
- **Threaded replies** to those messages, inlined into the parent message
- **File attachments** (PDFs, images, docs) shared in those channels
- **User mentions** (`<@USER>`) resolved to display names so they're readable in citations

### NOT synced
- **Direct messages and group DMs** — the integration doesn't request the scopes that would let us read them
- **Channels the bot isn't in** — inviting the bot is the consent boundary
- **Channels you didn't select** — even if the bot is in them
- **Reactions, pinned-message metadata, channel descriptions**
- **Files larger than 200 MB**

## Setting Up Slack Integration

There are three steps because Slack's permission model has two layers — installing the app gives RetrieveIt.AI permission to *exist* in your Slack workspace, but you separately have to invite the bot to each channel you want to sync.

### Step 1: Install the Slack App

1. Go to your **Workspace** in the Dashboard
2. Find the **Slack Integration** tile
3. Click **Connect Slack**
4. You'll be redirected to Slack to install the RetrieveIt app
5. Review the permissions and click **Allow**

You typically need to be a Slack workspace admin to install the app. If your Slack workspace restricts app installation to admins (most do), you may need to request approval.

### Step 2: Invite the Bot to Channels

In Slack, go to each channel you want to sync and run:

```
/invite @retrieveit-bot
```

The bot can only see channels it's been explicitly invited to — this is how Slack enforces permission boundaries, and we deliberately work within that model so users see who has visibility into their channels.

### Step 3: Select Channels in RetrieveIt

Back in RetrieveIt.AI:

1. Click **Configure** on the new Slack connection
2. The picker shows every channel the bot has been invited to
3. Select the channels you want to sync
4. Click **Save & Start Sync**

If the picker is empty, the bot isn't in any channels yet — go back to Step 2, invite the bot, then click **Refresh** in the picker.

### Step 4: Initial Sync

After saving:
1. RetrieveIt.AI pulls message history from each selected channel
2. Threaded replies are inlined into parent messages
3. Shared files are downloaded and indexed
4. Once complete, channel content is searchable in Chat

How much history Slack returns depends on your Slack plan. Newer free workspaces have a recent-history-only window; paid workspaces with full history will sync further back.

## Managing Your Connection

### Changing Channels

To add or remove channels from sync:

1. **To add a channel** — first `/invite @retrieveit-bot` to it in Slack, then click **Configure** on the connection, click **Refresh**, check the new channel, click **Save**.
2. **To remove a channel** — click **Configure**, uncheck the channel, click **Save**. Synced messages from that channel are deleted from RetrieveIt.AI on the next sync.
3. **To remove the bot entirely from a channel** — in Slack, run `/kick @retrieveit-bot`. The integration loses visibility on the next sync.

### Manual Sync

Click **Sync Now** to immediately pull new messages and files from your selected channels.

### Automatic Sync

Slack connections sync automatically **every hour**. New messages, new replies on existing threads, and new file attachments are detected and processed.

### Re-authentication

Slack bot tokens don't normally expire, so re-authentication is rare. It can happen if a Slack workspace admin **uninstalls** the RetrieveIt app from your Slack workspace. If that happens, the connection shows a **Re-auth needed** banner — click **Reconnect** to reinstall. Channel selections and sync history are preserved.

### Switching Slack Workspaces

Each RetrieveIt workspace can be connected to **one Slack workspace at a time**. If you try to install the app from a different Slack workspace against a RetrieveIt workspace that already has a Slack connection, the flow rejects with an error. Disconnect the existing connection first, then install from the new Slack workspace.

### Disconnect

Click the trash icon on the connection card. You'll be asked to confirm. On confirm:

- The connection is removed from RetrieveIt.AI immediately
- Your stored Slack bot token is deleted
- All synced Slack messages and files are queued for deletion from the workspace

You should also remove the RetrieveIt app from your Slack workspace afterward (Slack's **Apps → RetrieveIt → Remove app**) so the bot is fully evicted.

## Frequently Asked Questions

### I just invited the bot to a channel. Why isn't it in the picker?

Click **Refresh** on the configuration page. If it still doesn't appear, double-check you ran `/invite @retrieveit-bot` in the channel (not in a DM with the bot).

### A teammate added a new channel. When will it sync?

Never, until you (a) invite the bot to it and (b) select it in the configuration page. The integration is opt-in per channel — there's no auto-discovery of new channels.

### Why don't `<@U01ABCDEF>`-style mentions resolve to names?

Display name resolution is best-effort. The integration caches Slack user names so most mentions show as `@Brian Carpio`, but if a brand-new user joined and hit the cache before it refreshed, you might briefly see the raw `@U01ABCDEF` form. The next sync re-renders the message with the resolved name.

### I deleted a message in Slack. Does it go away in RetrieveIt?

Yes. The next sync notices the deletion and removes the message from the workspace.

### I'm seeing "Slack is throttling requests" — what's going on?

Slack rate-limits API calls per app. The integration retries with backoff, but a very large initial sync (thousands of messages across many channels) can occasionally hit the limit. It self-recovers — just wait, or click **Sync Now** again later.

### Does the integration ever post in Slack?

No. RetrieveIt.AI only requests read scopes (`channels:history`, `channels:read`, `groups:history`, `groups:read`, `files:read`, `users:read`, `team:read`). We never request `chat:write` or any write/admin scope.

### Can I see exactly what's in a synced channel?

The synced messages appear as citations when chat answers a question. To see the full set, search the workspace or filter chat to just the Slack channel.

## Privacy & Security

- Slack content is treated as confidential — encrypted at rest and in transit
- Your Slack bot token is stored encrypted with AWS KMS
- RetrieveIt.AI is read-only; nothing is ever written back to Slack
- DMs and group DMs are never accessed (the scopes that would allow it are deliberately not requested)
- Disconnect anytime to remove all synced Slack data from the workspace
- The bot only sees channels it's been explicitly invited to — that's the consent boundary
