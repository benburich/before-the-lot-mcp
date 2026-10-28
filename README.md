# Before the Lot MCP connector

[![Before the Lot MCP connector](https://glama.ai/mcp/connectors/com.beforethelot/before-the-lot/badges/score.svg)](https://glama.ai/mcp/connectors/com.beforethelot/before-the-lot)

**Flip the script on the dealership's four-square.** The salesperson's worksheet puts price, trade-in, down payment and monthly payment on one sheet, so a give in one box can be taken back in another. Before the Lot pulls them apart. Three squares get settled at home with documents in hand (written trade-in offers, the down payment, a loan pre-approval), which leaves one number to negotiate: the out-the-door price.

With this connector, your AI assistant does the math. Ask what a car will cost out the door in your state or city, paste a dealer's quote to have it checked line by line, or compare a lease with buying. The tools use each state's own rules: sales tax with local rates for 7,000+ US cities and counties, doc-fee caps, trade-in tax credits, rebate treatment and lease tax, with sources and dates. When the talk turns to monthly payments, a trade-in before the price is set, or add-ons, `desk_script` gives a short line to say.

**Connector URL:** `https://beforethelot.com/mcp`

- Hosted, Streamable HTTP, no sign-in
- 16 read-only tools, 4 prompts, and the Before the Lot method's guides as resources
- Free; made by [Volocent Labs LLC](https://beforethelot.com/about)

This repository holds the connector's documentation and its [MCP Registry entry](server.json) (`com.beforethelot/before-the-lot`). The service itself runs at [beforethelot.com](https://beforethelot.com); its code isn't published here.

## Connect

**Claude** (claude.ai and the desktop app): Settings, Connectors, Add custom connector, then paste `https://beforethelot.com/mcp`. Or use the one-tap link on [beforethelot.com/connect](https://beforethelot.com/connect).

**Claude Code:**

```sh
claude mcp add --transport http before-the-lot https://beforethelot.com/mcp
```

**Cursor** (`~/.cursor/mcp.json`):

```json
{
  "mcpServers": {
    "before-the-lot": { "url": "https://beforethelot.com/mcp" }
  }
}
```

**VS Code** (`.vscode/mcp.json`):

```json
{
  "servers": {
    "before-the-lot": { "type": "http", "url": "https://beforethelot.com/mcp" }
  }
}
```

**ChatGPT:** custom connectors need a Business, Enterprise or Edu workspace (or developer mode). On other plans, see [beforethelot.com/connect](https://beforethelot.com/connect) for a starter message that works without one.

Step-by-step setup for each assistant: [beforethelot.com/connect](https://beforethelot.com/connect). Technical details: [beforethelot.com/ai](https://beforethelot.com/ai).

## Tools

| Tool | What it does |
| --- | --- |
| `out_the_door` | Itemizes an out-the-door price: rebates, doc fee, add-ons, state and local tax, title, trade-in credit and an optional loan payment |
| `check_quote` | Checks a dealer's quote line by line: total, doc fee against the state cap, tax, add-ons |
| `compare_quotes` | Ranks 2 to 10 dealer quotes by out-the-door price |
| `what_can_i_afford` | The highest out-the-door price a monthly payment carries |
| `state_rules` | A state's doc-fee rule, sales tax, trade-in credit, rebate treatment and cancellation rights |
| `lease_check` | Works a lease quote, including tax, and compares it with buying |
| `rebate_vs_apr` | Cash rebate with your own loan against the maker's special APR |
| `loan_payment` | Payment, total interest and the cost of a term over 60 months |
| `refinance_check` | A current car loan against a quoted refinance |
| `trade_in_position` | Best open trade-in offer, equity and the tax a trade saves |
| `payoff_plan` | Months and interest saved by paying extra each month |
| `dealer_email` | Drafts one of six emails to a dealer or lender |
| `desk_script` | A line to say at the dealership for a common moment |
| `offers_page` | A maker's official current-offers page |
| `get_method` | The Before the Lot method and its seven stages |
| `plan_link` | A link that opens the Before the Lot planner with the numbers filled in |

## Try it

- What would a $36,000 car cost out the door in Pittsburgh, PA?
- Here's the quote my dealer emailed me. Can you check it line by line?
- How does this lease work out? MSRP $40,000, price $38,000, 58% residual, money factor 0.0025, 36 months, Texas.

## Privacy

- No accounts, no sign-in, no tokens.
- All tools are read-only; nothing a tool receives is stored.
- Each call adds one usage count with the tool's name; the arguments are never logged.
- Pasted quote lines that look like contact details are dropped before reading.
- Tools take a city or county name, never a street address.

Full policy: [beforethelot.com/privacy](https://beforethelot.com/privacy). Terms: [beforethelot.com/terms](https://beforethelot.com/terms).

Every result is an educational estimate, not financial, legal or tax advice. The dealer's own figures and your state's documents are what count.

## Contact

contact@beforethelot.com, or open an issue here.

© 2026 Volocent Labs LLC.
