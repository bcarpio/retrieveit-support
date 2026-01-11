# Integration Best Practices

Guidelines for setting up and maintaining your third-party integrations.

## Use Service Accounts, Not Personal Accounts

When connecting integrations like SharePoint, Google Drive, Gmail, Confluence, or Jira, we strongly recommend using a **service account** or **shared IT account** rather than an individual employee's personal account.

### Why This Matters

When you connect an integration, the connection is tied to that user's account credentials. If that employee:
- Leaves the company
- Has their account disabled
- Changes roles and loses access

**The integration will stop working.** All syncs will fail until a workspace admin reconnects with different credentials.

### Recommended Approach

1. **Create a dedicated service account** in your identity provider (Microsoft 365, Google Workspace, Atlassian)

2. **Grant appropriate permissions** to the service account for the resources you want to sync:
   - SharePoint: Add to relevant sites as a member
   - Google Drive: Share folders with the service account
   - Confluence/Jira: Add to appropriate spaces and projects

3. **Use the service account** when setting up the integration in RetrieveIt.AI

4. **Document the service account** so your IT team knows it exists and why

### Platform-Specific Notes

#### Microsoft 365 (SharePoint, OneDrive)
- Create a dedicated user account (e.g., `retrieveit-sync@yourcompany.com`)
- Add this account to SharePoint sites you want to sync
- Consider using a Microsoft 365 license type appropriate for service accounts

#### Google Workspace (Gmail, Drive)
- Create a dedicated user account (e.g., `retrieveit-sync@yourcompany.com`)
- Share relevant Drive folders with this account
- For Gmail, the service account's mailbox will be synced

#### Atlassian (Confluence, Jira)
- Create a dedicated Atlassian account
- Add to relevant Confluence spaces and Jira projects
- Use an API token for authentication where applicable

## Connection Monitoring

If an integration connection fails (due to expired credentials, revoked access, or account issues):
- The connection status will show an error in your workspace
- Organization admins receive a notification
- Workspace admins should reconnect with valid credentials

## Regular Review

Periodically review your integrations to ensure:
- Service account access is still appropriate
- No unnecessary data is being synced
- Connections are healthy and syncing successfully
