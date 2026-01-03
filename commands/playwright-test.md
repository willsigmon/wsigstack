## Legend
| Symbol | Meaning | | Abbrev | Meaning |
|--------|---------|---|--------|---------|
| → | leads to | | UI | user interface |
| & | and/with | | E2E | end-to-end |
| w/ | with | | snap | snapshot |

Execute immediately. Add --plan flag if user wants to see plan first.

Playwright-based UI verification for $ARGUMENTS. Use this to confirm the UI actually works, not just compiles.

@see shared/mcp-flags.yml ∀ MCP controls

Required inputs (ask if missing):
- URL or app start command
- Key flows to verify (login, create, edit, delete, checkout, etc.)
- Any auth requirements or test accounts

Flags (optional):
- --url <url> → target page
- --flows → exercise critical user paths
- --snapshots → capture snapshots/screenshots at key states
- --console → collect console errors/warnings
- --pause → pause for user input when needed (auth, destructive actions)
- --no-pw → skip Playwright (fallback to Puppeteer or ask)

Playwright workflow:
1. Navigate to target URL
2. Capture initial snapshot
3. Check console for errors/warnings
4. Exercise core interactions (forms, nav, modals, dialogs)
5. Capture snapshots at each key state
6. Pause for user input when decision is required
7. Summarize pass/fail, console issues, and any broken flows

Safety rules:
- Never submit destructive actions without confirmation
- Pause before irreversible actions (delete, publish, payments)
- If auth required, ask for test creds or a test user flow

Report Output:
- Save screenshots → `.claudedocs/playwright/<timestamp>/`
- Console log summary → `.claudedocs/playwright/playwright-console-<timestamp>.md`
- Include report location in output: "📄 Playwright artifacts saved to: [path]"

Examples:
- `/user:playwright-test --url http://localhost:3000 --flows --snapshots --console`
- `/user:playwright-test --url https://staging.example.com --pause --snapshots`
- `/user:test --e2e --pw --think` (Playwright E2E within test workflow)

Deliverables: UI verification notes, console error summary, snapshots, and any blockers.
