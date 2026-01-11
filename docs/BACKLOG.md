# Support Documentation Backlog

Items that need to be updated when features are implemented.

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
