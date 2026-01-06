# How to Configure Gmail for RetrieveIt.AI

RetrieveIt.AI uses **magic links** for passwordless authentication. Here's how to ensure you receive login emails reliably in Gmail.

## Receiving Magic Link Emails

### Check Your Spam Folder
Magic link emails come from `noreply@retrieveit.ai`. If you don't see them in your inbox:
1. Check your **Spam** folder
2. If found there, mark as "Not spam"
3. Add `noreply@retrieveit.ai` to your contacts

### Add to Safe Senders
To prevent magic links from going to spam:

1. Open Gmail Settings (gear icon)
2. Go to **Filters and Blocked Addresses**
3. Click **Create a new filter**
4. In the "From" field, enter: `noreply@retrieveit.ai`
5. Click **Create filter**
6. Check **Never send it to Spam**
7. Click **Create filter**

## Google Workspace Admins

If your organization uses Google Workspace, admins may need to:

### Allowlist the Sender
1. Go to Google Admin Console
2. Navigate to **Apps** > **Google Workspace** > **Gmail** > **Spam, Phishing, and Malware**
3. Add `retrieveit.ai` to the approved senders list

### Check Email Routing
Ensure emails from `retrieveit.ai` aren't being blocked by:
- Email security gateways
- Third-party spam filters
- Custom routing rules

## Troubleshooting

### Magic Link Not Arriving
1. Wait 2-3 minutes (emails can be delayed)
2. Check Spam/Junk folders
3. Check any email filters you've created
4. Try requesting a new magic link
5. Contact your IT admin if using Google Workspace

### Magic Link Expired
Magic links expire after 15 minutes for security. If yours expired:
1. Go back to the login page
2. Enter your email again
3. Request a fresh magic link

### Wrong Email Address
Make sure you're using the email associated with your RetrieveIt.AI account. The email domain determines your organization membership.

## Tips

- Magic links are single-use - once clicked, they can't be reused
- Don't forward magic link emails - they're tied to your session
- Keep your email secure - anyone with access to your email can log in
