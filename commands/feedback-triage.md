# Feedback Triage Command

Run the iOS feedback triage system to analyze pending user feedback.

## Instructions

1. Check for pending feedback in the Supabase database at `https://bizbeoygypkkkgkceapf.supabase.co`
2. Run the triage script: `deno run --allow-net --allow-env --allow-read ~/ios-feedback-aggregator/claude-feedback-triage.ts`
3. Summarize the results showing:
   - Total feedback processed
   - Critical items requiring immediate attention
   - Common patterns or themes
   - Suggested fixes for high-priority items

If there are critical issues, offer to help fix them by:
- Reading the related code files identified
- Proposing specific code changes
- Creating a todo list for the fixes

Environment variables needed:
- SUPABASE_SERVICE_ROLE_KEY (ask user if not set)
- PROJECT_ROOT (default to current working directory)
