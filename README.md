# Skillshop

Expert skills your AI loads on demand, plus server-side checks that catch costly mistakes before you ship. Works with Claude Code, Claude Desktop, Cursor, VS Code and any MCP client.

**Test storefront and pricing:** https://skillshop.duckdns.org

The storefront uses Stripe test mode. Real purchases are currently unavailable.

## Connect (free, no signup)

```bash
claude mcp add --transport http skillshop https://skillshop.duckdns.org/mcp
```

Or install as a Claude Code plugin (free skills + server connection):

```
/plugin marketplace add McCoyLab87/skillshop
/plugin install skillshop@skillshop
```

Other MCP clients: add a server with URL `https://skillshop.duckdns.org/mcp`. With a paid key, send header `X-Skillshop-Key: <key>` (or `Authorization: Bearer <key>`).

## Free skills (in this repo)

- **Make the Call** — Compare your options and see which trade-offs matter before you decide.
- **Is This Grant Worth Applying For?** — Check the rules and odds of a good fit before spending hours on an application.
- **Plan Your First Home Server** — Figure out what to host, what gear you need, and what you can skip.
- **Tell Me What's Actually Done** — Turn messy progress notes into a clear update with proof, blockers, and next steps.
- **Clean Up Your Markdown File Details** — Make the titles, tags, and other details at the top of your files consistent.
- **Move Your Docs Without Breaking Links** — Move Markdown notes and guides while keeping links, images, and headings working.
- **Why Won't My AI Tool Connect?** — Find out whether the connection fails at setup, sign-in, or tool discovery.
- **Turn Meeting Notes Into Next Steps** — Pull out decisions, who owns each task, and what's due when.
- **Turn "Build Me an App" Into a Plan** — Turn a rough idea into a clear list of behaviors you can test.
- **Show Me the Receipts** — Track the source behind each claim so readers can verify it.
- **Find What Doesn't Match** — Compare two spreadsheets and explain missing rows, duplicates, and differences.

## Paid packs

### agent-ops
- **Build Your First AI Agent** — Turn a repeatable task into an AI helper with tools, clear stopping points, and a test run.
- **Make Sure Your AI Still Works** — Build repeatable tests that catch when a prompt, model, or tool change breaks something.
- **Hand Off Without Losing the Plot** — Give the next person or AI the context it needs to pick up the work without repeating it.
- **Figure Out What Went Wrong** — Use the AI's activity log to explain a failure and decide what to fix.
- **Ship Your AI Update Safely** — Decide what to test before people use the update and when to roll it back.
- **Find the First Thing That Broke** — Follow the AI's tool calls to find the earliest confirmed failure.
- **Keep Private Files Private** — Check that people can only find files through AI that they already have permission to open.
- **Sync Without Missing Files** — Build a connection that picks up where it left off without losing or duplicating records.
- **Help Your AI Pick Up Where It Left Off** — Save enough progress to recover after a crash without repeating completed actions.
- **Replay an AI Run Without Calling Live Tools** — Rerun recorded tool calls with test data and see where the new run behaves differently.
- **Will My AI Tool Work in Other Apps?** — Test whether your tool connects and behaves consistently across AI apps.
- **Make Your AI Tools Easier to Use** — Check whether a tool's instructions and inputs match what it actually does.
- **Will My Plugin Install Cleanly?** — Try installation, updates, and removal from a fresh profile before shipping.
- **Check That Your AI's Sources Back It Up** — Test whether the AI finds the right passages and whether they support its answers.
- **Make Your AI Find Answers in Your Files** — Prepare PDFs, notes, and other documents for search while keeping track of where each passage came from.
- check `audit_handoff: one owner, revisioned writes, verified delivery`
- check `audit_status_report: completion claims without evidence, hedges, vague blockers`

### grants
- **Make Your Grant Budget Add Up** — Build or review a grant budget and explain where every dollar goes.
- **Rewrite the Budget Without Losing Track** — Show what changed, why it changed, and what the funder needs to approve.
- **Catch Missing Grant Requirements** — Turn the funder's instructions into a checklist with proof and owners.
- **Prove Your Program Is Working** — Decide what to measure, how to collect it, and when to report it.
- **Show How Your Program Helps** — Connect what your program does to the changes you expect to see.
- **Write a Grant Proposal That Holds Up** — Turn your project notes and the funder's requirements into a proposal reviewers can follow.
- **Never Miss a Grant Deadline** — Turn an award agreement into a calendar of reports and deadlines.
- check `audit_grant_proposal: required sections, word limits, unsourced need data, non-SMART objectives, outputs posing as outcomes, request mismatch`
- check `audit_grant_budget: totals, salary x FTE math, fringe, indirect cap and base, match, missing justifications`

### homelab
- **Update Your Server Without Guesswork** — Plan updates in a safe order and verify that your apps and data still work.
- **Know When Your App Goes Down** — Set up checks that catch real outages and tell you what to inspect first.
- **Can You Actually Restore That Backup?** — Bring back a copy in a test space and see if it still works.
- **Lock Down Your Home Server** — Review who can reach your server and fix risky settings before you share access.
- **Move Your App Without Losing Data** — Plan the switch to a new server, test it, and keep a way back.
- **Get Your Apps Running at Home** — Set up apps on your own server and make sure they restart cleanly.
- **Know When You'll Run Out of Space** — Use real storage measurements to estimate when you'll need more room.
- check `audit_compose: exposed databases and admin panels, plaintext secrets, Docker socket, privileged containers, unpinned images, missing volumes`
- check `audit_backup_plan: 3-2-1, RAID/sync not counted, offsite encryption, tested restores`

Paid skill text and check code run on the server and are not in this repository. The test checkout issues sandbox licenses after a simulated payment.

## How it works

1. Your AI calls `list_skills` and sees the catalog.
2. When a task matches, it calls `get_skill` and follows the method.
3. Before reporting done, it calls the pack's check. Every check result shows credits used and left.

## License and privacy

The free skills in this repository are licensed CC BY 4.0: share and adapt them with credit. Privacy: https://skillshop.duckdns.org/privacy. Terms: https://skillshop.duckdns.org/terms.
