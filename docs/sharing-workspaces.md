# How to Share Workspaces

Workspace sharing lets members of one workspace search documents in another workspace, without needing direct membership. This is called **cross-workspace search access**.

## Understanding Cross-Workspace Access

### The Concept
- Workspace A can grant search access to Workspace B
- Members of Workspace B can then search Workspace A's documents
- They don't become members of Workspace A
- They can only **search**, not upload or manage

### Example
Your company has:
- **Engineering** workspace (technical docs)
- **Product** workspace (PRDs, specs)
- **Support** workspace (help articles)

The Support team needs to search Engineering and Product docs to answer customer questions. Instead of adding every support person to those workspaces, you grant the Support workspace search access to Engineering and Product.

## How to Configure Sharing

### Requirements
- You must be a **Workspace Admin** of the workspace you want to share

### Steps
1. Go to **Dashboard** > **Workspaces**
2. Click the workspace you want to share (the source)
3. Go to **Settings** > **Search Access**
4. Select which workspaces can search this workspace's documents
5. Click **Save**

### What Users See
- Shared workspaces appear as **blue chips** in Chat (labeled "shared")
- Users can select them just like their own workspaces
- Search results show which workspace each result came from

## Best Practices

1. **Share thoughtfully** - Only grant access when there's a clear need
2. **Document your sharing** - Keep track of which workspaces share with which
3. **Review periodically** - Remove access when no longer needed
4. **Consider sensitivity** - Don't share workspaces containing confidential data

## Limitations

- Sharing is one-way: granting A access to B doesn't give B access to A
- Shared access is read-only (search only)
- Users can't see the workspace in Dashboard, only in Chat search
- Maximum 50 workspaces can be granted access to a single workspace
