# AI Dev Pipeline

Automated development workflow: Jira ticket → Figma design → Code → GitHub PR.

## What this project does

1. Read a Jira ticket
2. Generate a Figma design frame from the requirements
3. Read the Figma design and generate a clean HTML/CSS page
4. Commit and open a GitHub PR

## Commands

```bash
# Install deps
npm install

# Open the generated page in browser
open src/pages/dashboard.html
```

## Skills (slash commands)

| Command | What it does |
|---|---|
| `/read-ticket PROJ-1` | Read Jira ticket, print a clear brief |
| `/design-page PROJ-1` | Create a Figma frame from the ticket brief |
| `/code-from-figma <url>` | Read Figma frame, generate HTML/CSS page |
| `/ship-it PROJ-1` | Commit, open PR, update Jira to Done |

## MCPs connected

- **Jira** — read/update tickets
- **Figma** — create and read design frames
- **GitHub** — create branches and PRs

## Rules

- All generated pages go in `src/pages/`
- File names match the Jira ticket key, lowercase: `proj-1.html`
- HTML is semantic, CSS is in a `<style>` block in the same file — no external files
- No frameworks, no build step — pure HTML/CSS only
- Colors and spacing must match what Figma specifies exactly
- Every page must work by just opening the HTML file in a browser
