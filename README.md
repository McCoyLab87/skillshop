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

- **grant-fit-check**: Decide whether a nonprofit should apply for a specific grant before anyone writes a word. Use when someone shares a funding opportunity, RFP, NOFO or foundation guideline and asks whether to apply, or asks which of several grants to pursue.
- **homelab-planning**: Plan a home lab or self-hosting setup from goals, not gear - what to run, on what hardware, with what power, noise, network and budget limits, separating what the person has from what they need. Use when someone wants to start, expand or rebuild a home lab, home server, NAS or self-hosted services.
- **honest-status**: Report work status without overstating it. Use whenever you summarize progress, finish a task, or tell a person something is done, sent, fixed, deployed or verified.

## Paid packs

### agent-ops
- **agent-handoff**: Coordinate work between multiple AI agents and humans without lost writes, double ownership or false "done" claims. Use when more than one agent or person touches the same task list, ledger or deliverable, or when handing work to another agent.
- check `audit_handoff: one owner, revisioned writes, verified delivery`
- check `audit_status_report: completion claims without evidence, hedges, vague blockers`

### grants
- **grant-budget**: Build or review a nonprofit grant budget and budget justification that adds up, follows funder rules, and matches the narrative - personnel and fringe, direct costs, indirect rates, match and cost per participant. Use when preparing, checking or explaining any grant budget.
- **grant-proposal**: Write or revise a nonprofit grant proposal narrative that reviewers can score high - need statement, goals and SMART objectives, program design, logic model, evaluation, organizational capacity and sustainability. Use when drafting, tightening or reviewing any grant narrative, letter of inquiry or foundation application.
- check `audit_grant_proposal: required sections, word limits, unsourced need data, non-SMART objectives, outputs posing as outcomes, request mismatch`
- check `audit_grant_budget: totals, salary x FTE math, fringe, indirect cap and base, match, missing justifications`

### homelab
- **homelab-security**: Secure a home lab - remote access without open ports, network segmentation with VLANs, firewall rules, updates, secrets, and a 3-2-1 backup plan with tested restores. Use when exposing any self-hosted service, setting up remote access, adding IoT devices, planning backups, or reviewing a home network for risk.
- **homelab-services**: Deploy and run self-hosted services reliably with Docker Compose - pinned images, persistent data, secrets, reverse proxy, health checks, restart policies, updates and recovery. Use when writing or reviewing a docker-compose file, adding a service to a home server, or fixing a service that loses data or will not restart.
- check `audit_compose: exposed databases and admin panels, plaintext secrets, Docker socket, privileged containers, unpinned images, missing volumes`
- check `audit_backup_plan: 3-2-1, RAID/sync not counted, offsite encryption, tested restores`

Paid skill text and check code run on the server and are not in this repository. The test checkout issues sandbox licenses after a simulated payment.

## How it works

1. Your AI calls `list_skills` and sees the catalog.
2. When a task matches, it calls `get_skill` and follows the method.
3. Before reporting done, it calls the pack's check. Every check result shows credits used and left.

## License and privacy

The free skills in this repository are licensed CC BY 4.0: share and adapt them with credit. Privacy: https://skillshop.duckdns.org/privacy. Terms: https://skillshop.duckdns.org/terms.
