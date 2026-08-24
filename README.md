# Argorant plugins

Verified B2B contact data for agents. One plugin, which connects your assistant
to Argorant's hosted MCP server.

## Install

Add the marketplace, then install the plugin.

**Claude Code**

```
/plugin marketplace add argorant/argorant-plugins
/plugin install argorant@argorant
```

**Grok CLI**

```
grok plugin marketplace add argorant/argorant-plugins
grok plugin install argorant
```

Grok also reads Claude Code marketplaces directly, so if you already added it
there, it is available without doing anything else.

**Any MCP client, without the plugin**

Point it at the server URL and complete the sign-in:

```
https://mcp.argorant.com/mcp
```

Step-by-step guides with screenshots:
[Claude](https://argorant.com/docs/mcp/claude) ·
[ChatGPT](https://argorant.com/docs/mcp/openai)

## What you get

Ask for a market in plain language. Your assistant works out the filters,
counts the population and returns a masked preview before anything costs
money.

```
How many CFOs are there at software companies in Germany?
Show me a masked preview of those people
Who works in sales at stripe.com?
Reveal five of them
Export the whole segment as a CSV
```

The first three are free. The last two spend credits from your own Argorant
account, and those tools are marked as actions, so you are asked first.

Also included: a `find-buyers` skill that keeps the assistant working in the
cheap-first order, and a `/buyers` command that takes a website or a
description and walks the whole flow.

## Coverage

565 million business professionals across 184 countries. Addresses are checked
at the moment of export rather than at collection time, which is what keeps
bounce rates low and sending domains healthy.

## Account

You need an Argorant account, free to create at
[argorant.com](https://argorant.com). Counts and previews work on the free tier
with no payment details, so you can test the whole connection before spending
anything.

## Support

[support@argorant.com](mailto:support@argorant.com) ·
[Docs](https://argorant.com/docs/mcp) ·
[Privacy](https://argorant.com/privacy) ·
[Terms](https://argorant.com/terms)
