---
name: homelab-planning
description: Plan a home lab or self-hosting setup from goals, not gear - what to run, on what hardware, with what power, noise, network and budget limits, separating what the person has from what they need. Use when someone wants to start, expand or rebuild a home lab, home server, NAS or self-hosted services.
tier: free
---

# Home lab planning

Most home-lab regret comes from buying hardware before deciding what it is for. Plan from the workloads backward, and keep the person's budget where they set it.

## 1. Goals first

Ask, or infer from the conversation, and write down:

- What they want to run (media server, file storage and backup, home automation, ad blocking/DNS, password manager, VPN, game servers, learning Kubernetes...).
- Why: learning and tinkering is a legitimate goal, not only "cheapest result". Note which parts they want to build themselves.
- Who depends on it. If family relies on it (photos, home automation, DNS), reliability and backups matter more than features.
- Constraints: budget (total, and whether ongoing costs count), space, noise tolerance, electricity cost, internet upload speed, whether they rent.

## 2. Inventory: have vs need vs considering

Make three lists and keep them separate:

| Have (verified) | Need (for stated goals) | Considering (optional) |
|---|---|---|

Reuse first: an old desktop, laptop or mini PC often runs a full starter lab. Mark anything not verified (model, RAM, drive health) as unverified.

## 3. Size the workloads

For each service: CPU, RAM, storage and whether it needs a GPU or hardware video transcoding (Intel Quick Sync on many small PCs handles media transcoding well). Add 30–50% headroom. Storage: current data × growth over 3 years, then plan backups separately (storage is not backup).

## 4. Power, noise, heat

Estimate idle watts (what matters for a 24/7 box) and the yearly cost: watts × 8.76 × price per kWh = dollars per year. Rack servers are cheap to buy and expensive to run and loud; small form-factor PCs usually win for homes. Size a UPS to the total load with margin, and decide what should shut down cleanly on power loss.

## 5. Network basics

Note router capabilities (VLAN support, DNS settings), wired versus Wi-Fi for servers (wire them), and how remote access will work. Default to a VPN such as Tailscale or WireGuard instead of opening ports to the internet.

## 6. Output

1. Goals and constraints summary.
2. Have / need / considering table with full costs, including necessary extras: drives, cables, UPS, adapters, ongoing power.
3. A recommended build with the reason it fits, plus one cheaper and one more capable alternative, with trade-offs.
4. Phased plan: phase 1 runs on what they have; later phases add only what a goal requires.
5. What is unverified (compatibility, prices, specs) and how to check it.

Do not treat discussing an expensive option as a budget increase. For securing and running the services, use `homelab-security` and `homelab-services`.
