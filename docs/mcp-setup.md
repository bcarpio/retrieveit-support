# MCP (Model Context Protocol) Setup

Connect RetrieveIt.AI to AI assistants like Claude Desktop, Claude Code, Claude.ai, and ChatGPT using the Model Context Protocol. MCP lets AI tools search your documents, list workspaces, and query your knowledge base directly.

## What Is MCP?

MCP is an open protocol that allows AI assistants to access external tools and data sources. When you connect RetrieveIt.AI via MCP, your AI assistant can:

- **List your workspaces** and see what's available
- **Browse documents** within a workspace
- **Search your knowledge base** using natural language queries

## Authentication Methods

RetrieveIt.AI supports two ways to authenticate with the MCP server:

| Method | Best For | Setup |
|--------|----------|-------|
| **API Key (Bearer)** | Claude Desktop, Claude Code, custom MCP clients | Generate a key, paste into config |
| **OAuth** | Claude.ai (web), ChatGPT | Click "Connect" and authorize in-browser |

## Option 1: API Key (Bearer Token)

Use this method for desktop and CLI tools where you configure the MCP server manually.

### Step 1: Generate an API Key

1. Log in to [RetrieveIt.AI](https://app.retrieveit.ai)
2. Navigate to the **MCP** tab in your dashboard
3. Click **Generate API Key**
4. Copy the key immediately — it is only shown once

API keys use the format `rai_` followed by 40 characters (e.g., `rai_a1b2c3d4e5...`).

### Step 2: Configure Your AI Tool

Add the following MCP server configuration to your AI tool:

```json
{
  "mcpServers": {
    "retrieveit": {
      "url": "https://api.app.retrieveit.ai/mcp/v1",
      "headers": {
        "Authorization": "Bearer rai_your_api_key_here"
      }
    }
  }
}
```

Replace `rai_your_api_key_here` with the key you generated. Refer to your AI tool's documentation for where to add MCP server configurations (e.g., Claude Desktop, Claude Code, Cursor, Windsurf).

### API Key Notes

- API keys have **full access** to all MCP tools — no scope restrictions
- Keys are tied to your user account and respect your workspace memberships
- You can generate multiple keys and revoke them individually from the MCP tab
- If you lose a key, generate a new one (lost keys cannot be recovered)

## Option 2: OAuth (Web AI Platforms)

Use this method when connecting through AI platforms that support OAuth, such as Claude.ai or ChatGPT. No manual configuration is needed — the platform handles the connection flow.

### Claude.ai

1. In Claude.ai, look for the option to connect integrations
2. Select **RetrieveIt.AI** from the available connectors
3. You'll be redirected to RetrieveIt.AI to log in (if not already)
4. Review the permissions being requested and click **Allow**
5. You're redirected back to Claude.ai — the connection is active

### ChatGPT (GPT Actions)

ChatGPT can connect via a GPT Action using RetrieveIt.AI's OpenAPI spec. Contact your administrator or refer to the ChatGPT GPT Actions documentation for setup.

### OAuth Scopes

When authorizing via OAuth, the AI platform requests specific permissions:

| Scope | What It Allows |
|-------|----------------|
| `read:workspaces` | View your list of workspaces |
| `read:documents` | List documents within workspaces |
| `search` | Query the knowledge base with semantic search |

### Managing Connected Apps

You can review and revoke OAuth connections at any time:

1. Go to **Settings** in RetrieveIt.AI
2. Find **Connected Apps**
3. Click **Revoke** next to any app you want to disconnect

Revoking an app immediately invalidates all its tokens. The AI platform will need to go through the authorization flow again to reconnect.

### OAuth Token Details

- Access tokens expire after **1 hour** and are refreshed automatically by the AI platform
- Refresh tokens are valid for **90 days**
- Tokens are rotated on each refresh for security

## Available MCP Tools

Once connected, your AI assistant has access to three tools:

### list_workspaces

Lists all workspaces you have access to, returning each workspace's name, description, and status.

### list_workspace_documents

Lists documents in a specific workspace. Supports pagination for large document sets.

### query_knowledge_base

Performs semantic search across your documents. You can search across all workspaces or limit to specific ones. Returns the most relevant content with source references.

## Troubleshooting

### "Unauthorized" or "403" errors

- **API Key**: Verify the key is correct and hasn't been revoked. Generate a new key if needed.
- **OAuth**: Try disconnecting and reconnecting the app from Settings > Connected Apps.

### No workspaces or documents showing

- Confirm your user account has access to at least one workspace
- Check that the workspace has documents ingested and indexed

### Connection timeout

- The MCP server has a 30-second timeout. If your query is broad, try narrowing it to specific workspaces.

### Tool not appearing in AI assistant

- **Claude Desktop / Claude Code**: Restart the application after updating the MCP config
- **Claude.ai / ChatGPT**: Ensure the connection is active and hasn't expired
