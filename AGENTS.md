# everydeck docs: instructions for writing pages

This repository is the public user documentation of everydeck (app.everydeck.ai), built with Mintlify.

- Pages are MDX files with YAML frontmatter.
- Navigation, colors, logo and links live in `docs.json`. Every page must be listed there, and every page listed there must exist.
- Folders: `get-started/`, `connect/`, `using/`, `reference/`. The introduction is `index.mdx`, the quickstart `quickstart.mdx`.

## Who we write for

Someone who built an app with an AI coding agent and "understands nothing" about backends. Write so they can follow without help.

## Writing rules (strict)

- English only. Plain words, short sentences, one idea per sentence.
- No em dashes and no en dashes anywhere. Use commas, periods or colons.
- Second person ("you"), active voice, sentence case for headings.
- Bold for UI elements, with the exact label from the product: click **Approve**, **Copy fix for Claude Code**, **Mark as fixed**.
- Code formatting for commands, file names and paths.
- Every page has `title` and `description` in the frontmatter. The description is one or two sentences for search engines.
- Use Mintlify components where they help: `Steps`, `Note`, `Warning`, `Info`, `Tabs`, `Accordion`, `Card`. No badges or pills.
- Use the neutral example app "Acme" (case addresses like `ACME-14`, people like `P-7`).

## Content rules (strict)

- Only state what the product really does. Every number, deadline and limit exactly as the product has it. If you are not sure, leave it out and ask.
- Do not invent features, prices or plans. everydeck is free in this first version; Free is the only plan.
- Say known gaps honestly where they matter, for example:
  - Lovable Cloud cannot be connected yet. Reading and changing data needs the app's own Supabase project.
  - Setting up in Lovable needs more than Lovable's free daily credits. Do not quote Lovable's prices.
  - Clerk and Auth0 are recognized but not connected: no sign-in links or password reset there. Those need Supabase Auth.
  - Native iPhone and Android crashes are not captured.
- The only email address is support@everydeck.ai.
- Positioning: everydeck is a real backend for everything in your app, like the admin of a Shopify store. Your team sees records and edits them where the owner allowed it. Never describe the app's data as "read only" to the user. The read bridge is only the technical way everydeck reads; editing goes through the change door.
- There is no separate email when a case is fixed. Emails come when a case comes back (**Came back**).

## Never include

- Internal code paths, file names of everydeck's own code, migration numbers, internal environment variable names, internal order or ticket names.
- Names of pilot, customer or test apps, names of people, internal decisions.
- German text.
- UUIDs. Short addresses like `ACME-14` are fine.

## Checking your work

- `docs.json` must be valid JSON.
- Every page in the navigation must exist.
- Search for em dashes (U+2014) and en dashes (U+2013) before you finish: there must be none.
- If available, run `npx mint broken-links` and `npx mint validate`.
