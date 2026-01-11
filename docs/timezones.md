# Timezones in RetrieveIt.AI

## Why do dates and times seem off?

When you search for emails or documents that contain timestamps, you may notice the times appear different from what you expected. This is because all timestamps are currently stored and displayed in **UTC (Coordinated Universal Time)**.

For example, if you received an email at 9:00 AM Pacific Time, it may show as 5:00 PM when you query for it (since Pacific Time is 8 hours behind UTC).

## How to interpret times

When RetrieveIt.AI returns a date or time from your documents:
- Assume the time is in **UTC** unless a timezone is explicitly mentioned
- To convert to your local time, adjust for your timezone offset:
  - Pacific Time (PST): UTC - 8 hours
  - Mountain Time (MST): UTC - 7 hours
  - Central Time (CST): UTC - 6 hours
  - Eastern Time (EST): UTC - 5 hours

## Tip

You can ask follow-up questions like:
- "What time was that in Pacific Time?"
- "Convert that to my local timezone (PST)"

The AI will convert the time for you.

## Future improvement

We're working on adding timezone preferences to user profiles so times will automatically display in your local timezone.
