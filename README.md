# Hotel Price Watch — Google Hotels Rate Alerts — MCP Server

Watch Google Hotels rates from your AI agent or MCP client and get an alert only when a rate drops — give a destination and dates once, and each check compares against the baseline and reports only the drops, as clean structured records. A one-shot search of the same destination and dates is also available when an agent just needs the current hotel rates now: property name, nightly rate, total for the stay, guest rating, review count, star class and amenities where Google shows them.

This repo is the MCP listing for the [Hotel Price Watch — Google Hotels Rate Alerts](https://apify.com/magnova/hotel-price-watch) Actor by Magnova on Apify. The server is hosted by Apify at the pinned endpoint below — there is nothing to install or run from this repository; you just point your MCP client at the URL.

## Tools

The pinned connection loads a focused tool set:

- **magnova--hotel-price-watch** — Watch Google Hotels rates for price drops against a baseline, or search a destination and dates in one shot. Returns structured records: property name, nightly rate, total for the stay, guest rating, review count, star class, amenities and a Google Hotels link.
- **fetch-actor-details** — Fetch the Actor's full input schema, pricing, and documentation, so an agent can check parameters and cost before running it.
- **get-actor-run / get-dataset-items** — Run and storage helpers, loaded automatically, used to fetch the results a run produced.

## Connect

Pinned endpoint (Streamable HTTP):

```
https://mcp.apify.com?tools=fetch-actor-details,magnova/hotel-price-watch
```

On first connect, your client will ask you to sign in with your Apify account (OAuth). If your client cannot do OAuth, pass your Apify API token as an `Authorization: Bearer <YOUR_APIFY_TOKEN>` header instead.

### Cursor / VS Code / other Streamable HTTP clients

```json
{
  "mcpServers": {
    "hotel-price-watch": {
      "url": "https://mcp.apify.com?tools=fetch-actor-details,magnova/hotel-price-watch"
    }
  }
}
```

### Claude Desktop

Claude Desktop's config file only runs local commands, so use the `mcp-remote` bridge:

```json
{
  "mcpServers": {
    "hotel-price-watch": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://mcp.apify.com?tools=fetch-actor-details,magnova/hotel-price-watch"
      ]
    }
  }
}
```

The same pinned URL also lives in this repo's `.mcp.json`, and `server.json` is the listing for the Official MCP Registry, published as `io.github.memeanalyst/hotel-price-watch-mcp`.

## Pricing

Pay per event, billed to your own Apify account: **$0.002 per hotel record + $0.02 per price-drop alert**. No start fee, no subscription, and you are only charged for records actually delivered.

## Links

- Actor on Apify Store: https://apify.com/magnova/hotel-price-watch
- MCP endpoint: https://mcp.apify.com?tools=fetch-actor-details,magnova/hotel-price-watch

*Rate records come from Google Hotels' public search results.*
