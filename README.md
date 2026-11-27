# SharehouseHub for Claude

[![Listed on mcpservers.org](https://mcpservers.org/badge.svg)](https://mcpservers.org/servers/red-center-studio/sharehousehub-claude-plugin)

A plugin that connects Claude to SharehouseHub's remote MCP connector, so you can find share house rooms in Australia, check a room ad for scam signals, get tenancy rules with sources, plan inspections and split costs. SharehouseHub members can also manage a house: housemates, rent, bills, chores, repairs and applicants.

- Connector (remote MCP, streamable HTTP): `https://mcp.sharehousehub.com.au/mcp`
- Website: https://sharehousehub.com.au
- Sharehouse Manager: https://www.sharehousehub.com.au/sharehouse-manager
- Built and run by [Red Center Studio](https://redcenterstudio.com/work/sharehousehub/)

## What works without signing in

Room search, scam check for an ad, official tenancy basics with sources, inspection checklists, cost splitting and room cost estimates.

## What needs a SharehouseHub Pro membership

Saved searches and alerts, messaging, host listing tools and the Sharehouse Manager tools (houses, housemates, rent, bills, chores and applicants). Plans and prices are on sharehousehub.com.au.

## Add it to Claude

Add the connector URL above as a custom connector, or install this plugin package. The skills in `skills/` (find a safe room, fill my room, manage my sharehouse, split a house bill) give Claude ready-made workflows.

## Security and privacy

Sign-in uses OAuth on sharehousehub.com.au. The connector never asks you to paste a password or key into chat. Report a security problem to admin@sharehousehub.com.au.

## License

MIT for this plugin package (see `LICENSE`). The connector server and the SharehouseHub platform are proprietary.
