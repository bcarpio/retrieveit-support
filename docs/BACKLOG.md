# Support Documentation Backlog

Items that need to be updated when features are implemented.

---

## Microsoft Partner Center Registration - BLOCKED

**Status:** Waiting for Microsoft support (call Monday)

**Issue:** Registration blocked during verification with error:
- Reference: 715-123160
- Transaction ID: 6486895d-7443-4a57-bed5-1465d179f102

**Why it matters:** Publisher verification required for external customers to use SharePoint integration without "unverified" warnings or blocks.

**Call Monday:** 1-800-642-7676
- Have ready: EIN, DUNS (142286615), reference numbers above
- Company: OutcomeOps LLC

**Workaround for demos:** Customer's IT admin can grant admin consent for unverified apps.

---

## Notify Workspace Admins on Connection Failures

**Current behavior:** Only org admins receive notifications when an integration connection fails (auth error, token expired, etc.)

**Requested:** Workspace admins should also be notified since they manage the integrations for their workspace.

**When implemented:**
- [ ] Update `docs/integration-best-practices.md` to reflect that workspace admins are also notified

---

## User Timezone Preferences

**Feature:** Add timezone selection to user profile. Pass timezone to chat and instruct AI to convert UTC times to user's local timezone.

**Implementation notes:**
- Add `timezone` field to user profile in DynamoDB
- Add timezone selector in Settings page (IANA timezones)
- Pass timezone to chat lambda with each request
- Add system prompt: "User's timezone is {timezone}. When returning dates/times without explicit timezone, assume UTC and convert to user's local timezone."

**When implemented:**
- [ ] Delete `docs/timezones.md` (temporary workaround doc)
- [ ] Update `docs/gmail-integration.md` to mention timezone support
