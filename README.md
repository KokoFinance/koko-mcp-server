# KoKo Finance MCP Server

A hosted MCP server for AI-powered credit card advice. Search 100+ US credit cards, compare options side by side, analyze portfolio health, and get personalized recommendations — all through the Model Context Protocol.

**Server URL:** `https://kokofinance.net/mcp/`

No API key required. No local installation needed. Just connect your MCP client.

## Quick Setup

### Claude Desktop

Add to `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS) or `%APPDATA%\Claude\claude_desktop_config.json` (Windows):

```json
{
  "mcpServers": {
    "koko-finance": {
      "type": "http",
      "url": "https://kokofinance.net/mcp/"
    }
  }
}
```

### Claude Code

```bash
claude mcp add koko-finance --transport http https://kokofinance.net/mcp/
```

Or copy the `.mcp.json` from this repo into your project.

### Cursor

Go to **Settings > MCP** and add a new server:
- **Name:** koko-finance
- **Type:** HTTP
- **URL:** `https://kokofinance.net/mcp/`

### Cline / Windsurf

Add to your MCP settings file:

```json
{
  "mcpServers": {
    "koko-finance": {
      "type": "http",
      "url": "https://kokofinance.net/mcp/"
    }
  }
}
```

## Tools (7)

| Tool | Description |
|------|-------------|
| `search_credit_cards` | Natural language search across 100+ US credit cards |
| `compare_cards` | Side-by-side comparison of 2-3 cards with fees, rewards, net value, and break-even (<100ms) |
| `get_card_details` | Full details for a specific card (fees, rewards, benefits) |
| `calculate_card_value` | Annual fee break-even analysis with first-year and ongoing value |
| `optimize_portfolio` | Portfolio health score, per-card KEEP/OPTIMIZE/CANCEL verdicts (<100ms) |
| `recommend_card_for_category` | Best card to use for a specific spending category, ranked by reward value (<100ms) |
| `create_mcp_session` | Session tracking for multi-query conversations |

## Prompts (3)

Pre-built conversation starters that guide the AI through structured workflows:

| Prompt | Description | Parameters |
|--------|-------------|------------|
| `portfolio-review` | Full portfolio analysis with health score and verdicts | `card_names`, `monthly_spending` (optional) |
| `which-card` | Find the best card for a specific purchase | `card_names`, `category`, `amount` (optional) |
| `new-card-finder` | Search for a new card matching your criteria | `spending_focus`, `annual_fee_limit` (optional), `credit_score` (optional) |

## Example Conversations

**"Review my portfolio"**
> I have a Chase Sapphire Reserve, Amex Gold, and Citi Double Cash. Analyze my portfolio and tell me which cards are worth keeping.

**"Which card should I use?"**
> I'm buying $200 in groceries. I have an Amex Gold, Chase Freedom Unlimited, and Citi Custom Cash. Which card should I use?

**"Find me a new card"**
> I spend a lot on travel and dining. I want a card under $300 annual fee with a good sign-up bonus. What do you recommend?

## Links

- [KoKo Finance](https://kokofinance.net) — Main site
- [Developer Documentation](https://kokofinance.net/developers.html) — Full API and tool reference
- [MCP Endpoint](https://kokofinance.net/mcp/) — Direct server URL

## Also Available

- **[Claude Code Plugin](https://github.com/madanc/koko-credit-card-plugin)** — Adds the MCP server connection plus an Agent Skill that teaches Claude structured credit card workflows

## License

MIT
