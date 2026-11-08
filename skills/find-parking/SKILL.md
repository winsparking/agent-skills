---
name: find-parking
description: Find, price and book parking near any U.S. address, venue, airport or stadium with Park Graph. Use when the user asks where to park, how much parking costs for a number of hours, truck or RV parking, or wants a parking pay link. Covers 8,000+ public lots plus bookable Park Graph lots.
---

# Find parking with Park Graph

Park Graph (https://parkgraph.com) lists 8,000+ public U.S. parking lots and garages, plus lots that take payment through Park Graph with one QR code. Use it to answer "where can I park near X", "how much is 3 hours there" and "give me the pay link".

## Fastest path: the hosted MCP server

- URL: `https://parkgraph.com/api/mcp` (streamable HTTP, no API key)
- Optional driver sign-in (OAuth) adds `my_sessions` and `my_vehicles`.

| Tool | Use it to |
|---|---|
| `search_lots` | List lots near a point, nearest first, with rate and spaces left. Unlisted public lots come back with their parkgraph.com page. |
| `get_lot` | Read one lot's address, hours, rules, rates and spaces left. |
| `quote` | Price a stay for N hours at the lot's current rate, daily max applied. |
| `reserve` | Hold a space (lots that take holds) or get the lot's pay page. Ask the user first. |
| `get_session` | Check a parked car: 6-character code from the receipt + last 3 of the plate. |
| `extend_session` | Price more time and get the pay link. Ask the user first. |

Add it to a client:

```json
{ "mcpServers": { "park-graph": { "type": "streamableHttp", "url": "https://parkgraph.com/api/mcp" } } }
```

## REST fallback (no key)

```bash
curl "https://parkgraph.com/api/v1/lots/search?lat=39.7559&lng=-104.9942&radius_km=2"
```

Docs: https://parkgraph.com/developers/api

## Rules

1. Geocode the place first if the tool needs coordinates, then call `search_lots`.
2. Always quote before giving a total. Never compute the price yourself.
3. Payment always finishes on parkgraph.com with the driver present. Never collect card details in chat.
4. Ask before `reserve` or `extend_session`.
5. If a lot is listed as not bookable, give its page link and say so plainly.

## Links

- Park Graph: https://parkgraph.com
- Parking by city and venue: https://parkgraph.com/parking
- Truck parking by state: https://parkgraph.com/truck-parking-by-state
- Lot owners, take payments with one QR sign: https://parkgraph.com/signup
- MCP docs: https://parkgraph.com/developers/mcp
