# Managing Team Members

This guide covers how to invite people to your organization, manage workspace membership, and understand roles.

## Roles Overview

RetrieveIt.AI has two levels of roles:

### Organization Roles
- **Org Admin** - Full control over the organization. Can create workspaces, invite users, manage billing, and has implicit access to all workspaces.
- **Member** - Basic organization membership. Must be explicitly added to workspaces to access them.

### Workspace Roles
- **Workspace Admin** - Can manage workspace members, configure integrations, upload documents, and configure sharing.
- **Member** - Can search and chat with documents in the workspace.

### What Can Each Role Do?

| Action | Org Admin | Workspace Admin | Member |
|--------|-----------|-----------------|--------|
| Create workspaces | Yes | No | No |
| Invite new users | Yes | Yes (to their workspace) | No |
| Manage billing | Yes | No | No |
| Configure integrations | Yes | Yes | No |
| Upload documents | Yes | Yes | Yes |
| Search and chat | Yes | Yes | Yes |
| Remove members | Yes | Yes (from their workspace) | No |

**Note:** Org Admins automatically have access to all workspaces without being explicitly added.

## Inviting Team Members

### Requirements
- You need an active subscription to invite members
- You must be an **Org Admin** or **Workspace Admin**
- The person you invite must have an email address matching your organization's domain (e.g., if your org is @acme.com, you can only invite @acme.com emails)

### Invite from the Team Members Page (Org Admin)

1. Go to **Dashboard** > **Team Members**
2. Click **Invite Member**
3. Enter the person's email address
4. Select which workspace to add them to
5. Choose their workspace role (Member or Workspace Admin)
6. Choose their organization role (Member or Org Admin)
7. Click **Send Invite**

### Invite from a Workspace (Org Admin or Workspace Admin)

1. Go to **Dashboard** > **Workspaces**
2. Click the workspace you want to add someone to
3. Go to the **Team** tab
4. Click **Invite**
5. Enter the person's email address
6. Choose their workspace role
7. Click **Send Invite**

### Adding Existing Org Members to a Workspace

If someone is already in your organization but not in a specific workspace:

1. Go to the workspace's **Team** tab
2. Click **Add Member**
3. Select the person from the list of existing org members
4. Choose their workspace role
5. Click **Add**

## What Happens When Someone Is Invited

1. They receive an email with an invite link
2. They click the link and sign in with their email (magic link)
3. They're automatically added to the organization and workspace
4. They can immediately start searching and chatting

### Invite Expiry
- Invites expire after **24 hours**
- Org Admins and Workspace Admins can resend expired invites from the Team Members page

## Removing Team Members

### Remove from a Workspace
1. Go to the workspace's **Team** tab
2. Find the member you want to remove
3. Click **Remove**

### Remove from the Organization
1. Go to **Dashboard** > **Team Members**
2. Find the member
3. Click **Remove**

Removing someone from the organization removes them from all workspaces and revokes their access entirely.

## Changing Roles

1. Go to **Dashboard** > **Team Members**
2. Find the member
3. Use the role dropdown to change their organization or workspace role

## Frequently Asked Questions

### Can I invite someone with a different email domain?
No. For security, invitations are restricted to email addresses matching your organization's domain. If your org is @acme.com, only @acme.com emails can be invited.

### Does adding a member affect my billing?
Yes. Your subscription is seat-based. Adding a member increases your seat count and your monthly usage limits scale accordingly.

### Can a member be in multiple workspaces?
Yes. A member can belong to as many workspaces as needed, and can have different roles in each workspace.

### What happens when I remove a member?
Their access is revoked immediately and your seat count is reduced. Their previous search history and activity remain in audit logs.
