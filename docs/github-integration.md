# GitHub Integration

Connect GitHub repositories to RetrieveIt.AI to search your code, documentation, and markdown files.

## Overview

The GitHub integration allows you to:
- Import files from your repositories
- Keep documents synced when you push changes
- Search code and documentation alongside other content

## Setting Up GitHub Integration

### Step 1: Install the GitHub App

1. Go to your **Workspace** in the Dashboard
2. Find the **GitHub Integration** section
3. Click **Install GitHub App**
4. You'll be redirected to GitHub to authorize the app
5. Select which repositories to grant access to
6. Complete the installation

### Step 2: Connect a Repository

After installing the app:

1. Click **Add Repository** in your workspace
2. Select a GitHub installation (organization or personal)
3. Choose the repository to connect
4. Click **Connect**

### Step 3: Initial Sync

After connecting:
1. The repository will automatically start syncing
2. Supported files are extracted and indexed
3. Once complete, content is searchable in Chat

## Managing Repositories

### Manual Sync
Click **Sync** on a repository to pull the latest changes. Syncs also happen automatically when you push to GitHub.

### Disconnect
Click **Disconnect** to remove a repository. This deletes all synced documents from the workspace.

## What Gets Indexed

The integration indexes supported file types from your repository:

- **Markdown** (`.md`) - README, docs, wikis
- **Text** (`.txt`) - Plain text files
- **Code** (`.py`, `.js`, `.ts`, etc.) - Source files
- **Config** (`.yaml`, `.yml`, `.json`) - Configuration files
- **Documentation** (`.pdf`, `.docx`) - Binary docs

## Automatic Syncing

When you push to GitHub:
1. GitHub sends a webhook to RetrieveIt.AI
2. Changed files are automatically re-synced
3. New content becomes searchable within minutes

## Multiple Repositories

You can connect multiple repositories to a single workspace. This is useful for:
- Monorepos with multiple projects
- Related repositories that should be searched together
- Documentation spread across repos

## Tips

- Connect documentation repos for searchable knowledge bases
- Use for internal wikis and runbooks
- Great for searching across microservice codebases
- Combine with other integrations (Gmail, Drive) for unified search

## Permissions

The GitHub App requests:
- **Read access** to repository contents
- **Webhook events** for automatic syncing

We never write to your repositories or access private data beyond the repos you explicitly grant access to.
