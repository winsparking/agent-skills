---
name: find-ev-chargers
description: Find U.S. EV charging stations near any place or along a road trip with ChargingNear.me. Use when the user asks for chargers near a city, address or hotel, fast chargers on a drive, Tesla/NACS or CCS stations, live availability, highway charging gaps, or NEVI status.
---

# Find EV chargers with ChargingNear.me

ChargingNear.me (https://chargingnear.me) covers 89,000+ public U.S. charging stations, synced daily from U.S. Department of Energy (NREL) data and checked against Open Charge Map and live network feeds. Every station page shows when it was last verified.

## Fastest path: the hosted MCP server

- URL: `https://chargingnear.me/api/mcp` (streamable HTTP, no API key)
- Optional driver sign-in adds saved stations, trips and alerts.

| Tool | Use it to |
|---|---|
| `get_nearest_stations` | Chargers nearest a place (city, address or business) or lat/lng. Filter by speed, kW or connector. |
| `find_stations_on_route` | Charging stops along a drive, in driving order, with miles from the start. |
| `search_stations` | Stations by city, state, network, connector or live availability. |
| `get_station_details` | One station: ports, power, connectors, network, price, hours, last verified. |
| `get_city_charging_stats` / `get_state_charging_stats` | Totals and network mix for a city or state. |
| `get_charging_gaps` | Highway stretches with more than 50 miles between open DC fast chargers. |
| `get_corridor_chargers` | Every DC fast location on a corridor, in order. |
| `get_nevi_status` | Stations that meet federal NEVI minimums. |
| `get_catalog_totals` | Live size of the U.S. catalog. |

```json
{ "mcpServers": { "chargingnear-me": { "type": "streamableHttp", "url": "https://chargingnear.me/api/mcp" } } }
```

## REST fallback (no key)

```bash
curl "https://chargingnear.me/api/v1/stations/nearest?lat=39.64&lng=-106.37&limit=5"
curl "https://chargingnear.me/api/v1/stations/on-route?from=Denver,CO&to=Grand%20Junction,CO&speed=dcfc"
```

Docs: https://chargingnear.me/api-docs

## Rules

1. Prefer DC fast chargers for road trips; give kW and connector type for each stop.
2. Say when a station was last verified, and quote live availability only when the tool returns it.
3. Results are sorted by distance only. There is no paid placement.
4. Link each station's ChargingNear.me page so the driver can check it before driving.

## Links

- ChargingNear.me: https://chargingnear.me
- EV charging stations by state: https://chargingnear.me/ev-charging-stations-by-state
- Highway charging gaps: https://chargingnear.me/nevi-charging-gaps
- Will I make it? (arrival battery): https://chargingnear.me/will-i-make-it
- List your chargers: https://chargingnear.me/for-business
- MCP docs: https://chargingnear.me/mcp
