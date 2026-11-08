# Wins Parking agent skills

Agent skills for finding parking and EV charging in the United States. Works with Claude Code, Cursor, Codex, Gemini CLI and any agent that reads `SKILL.md`.

```bash
npx skills add winsparking/agent-skills
```

| Skill | What it does |
|---|---|
| [find-parking](skills/find-parking/SKILL.md) | Find, price and book parking near any U.S. address, venue or airport with [Park Graph](https://parkgraph.com). 8,000+ public lots, live rates, pay links, truck parking. |
| [find-ev-chargers](skills/find-ev-chargers/SKILL.md) | Find EV chargers near any place or along a road trip with [ChargingNear.me](https://chargingnear.me). 89,000+ stations, live availability, NEVI and highway gaps. |

Both skills use hosted MCP servers that need no API key:

- Park Graph MCP: `https://parkgraph.com/api/mcp` · [docs](https://parkgraph.com/developers/mcp) · [repo](https://github.com/winsparking/parkgraph-mcp)
- ChargingNear.me MCP: `https://chargingnear.me/api/mcp` · [docs](https://chargingnear.me/mcp) · [repo](https://github.com/winsparking/chargingnearme-mcp)

## Links

- Park Graph: [parking by city and venue](https://parkgraph.com/parking) · [truck parking by state](https://parkgraph.com/truck-parking-by-state) · [lot owners: start free](https://parkgraph.com/signup)
- ChargingNear.me: [chargers by state](https://chargingnear.me/ev-charging-stations-by-state) · [highway charging gaps](https://chargingnear.me/nevi-charging-gaps) · [list your chargers](https://chargingnear.me/for-business)
- Built by [Wins Parking, LLC](https://winsparking.com)

MIT License
