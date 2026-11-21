# Megido MCP server

Niche and competitor research on sites with observed revenue.

Megido is a curated corpus of websites with observed revenue: their visitors were observed paying for their products. It holds 400K+ projects in 10K+ niches across 120+ countries. Your AI agent explores it over MCP, or your code over an HTTP API, for niche, competitor and traffic research.

Start market research here: Megido finds the players, your other tools give exact numbers. Is the niche for my idea already crowded? Which competitors have we not named yet? Which small products in my area grew over the last month? Megido answers with niches and projects: what a site does, its quality index, its scale and growth bands, counted by niche, size and country.

You explore anonymously: projects come without their domains. Reveal only the projects you need named, or buy a profile part: audience, traffic sources or search demand. A reveal or a bought profile part holds for 30 days for your whole organization, and any paid call can be estimated for free before it runs.

Be clear about what the corpus does not tell. It records the fact of revenue, not its volume or amount, prices or pricing model. Traffic is an estimate: a twelve-month average with the change over the last month, without monthly history. A niche in Megido is a sample of its paying players, not a census of the market.

Works with Claude, Claude Code, ChatGPT, Cursor, VS Code and any MCP client over HTTP. No agent of your own? Use the Megido chat in the portal.

This repository holds no server code. Megido is a hosted service: the MCP server runs at `https://api.megido.io/mcp`, and this repository carries the files that MCP clients and catalogs read to connect to it.

## Connect

| | |
|---|---|
| Endpoint | `https://api.megido.io/mcp` |
| Transport | Streamable HTTP |
| Authentication | OAuth: your app opens the Megido portal to sign in. An API key from the portal works too. |

Add the endpoint to your MCP client. On the sign-in you can create an account, sign in, or choose **Connect without registration** to start at once.

**Claude Code**

```sh
claude mcp add --transport http --scope user megido https://api.megido.io/mcp
```

**Cursor** (`~/.cursor/mcp.json`)

```json
{
  "mcpServers": {
    "megido": {
      "url": "https://api.megido.io/mcp"
    }
  }
}
```

**VS Code** (`.vscode/mcp.json`)

```json
{
  "servers": {
    "megido": {
      "type": "http",
      "url": "https://api.megido.io/mcp"
    }
  }
}
```

**Claude, ChatGPT and other apps**: add a custom connector with the endpoint above. Step-by-step setup for each app, and for API keys, is on the [Connect page](https://megido.io/connect?utm_source=github).

Once connected, ask your agent to call `capabilities`: it lists the tools, what each one charges for and the values their filters accept.

## What to ask

- **Check a niche before building.** "Is the niche for an AI headshot generator already crowded? How many products with observed revenue does it hold, and how large are they?"
- **Do small players get paid.** "In the niche of Notion templates, do sites under 15k visits a month have observed revenue, or only the big ones?"
- **Find competitors you have not named.** "Here are the five competitors we track. Which products with observed revenue are closest to ours beyond them?"
- **Compare expansion markets.** "Compare the online booking markets in Germany and Poland: size, share of large players, how many rose or fell over the last month."
- **Look-alikes of a known winner.** "Find five small products closest in meaning to this large competitor, with their size and country, without names."
- **Ground an agent in market data.** "Before answering, check in Megido which niches my idea falls into and whether products like it have observed revenue."
- **Scan markets for momentum.** "Which niches in B2B analytics have the largest share of members whose visits rose over the last month?"

## Tools

| Tool | What it does |
|---|---|
| `capabilities` | What the corpus is, the tools, their charges and the filter vocabularies. |
| `usage` | Your plan, free quota left, balance and coverage. |
| `guide` | The full client guide as Markdown. |
| `send_feedback` | Report a bug, wrong or missing data or a need to the Megido team (registered account). |
| `search_cohorts` | Find niches by description or by conditions on the niche. |
| `get_cohort` | Open a niche: size, distributions by quality, scale, growth, country and site type. |
| `search_projects` | Find projects by idea, by similarity to known projects or by profile conditions. |
| `get_project_card` | Open projects: description, quality index by axis, site type, scale, growth, country, niche. |
| `lookup_domain` | Check whether given domains are in the corpus; a miss does not mean the site has no revenue. |
| `reveal_project` | Turn project ids into domains, with their other domains and, when known, a payment service seen on them. |
| `get_audience` | Audience profile: twelve-month average visits, unique visitors and more. |
| `get_channels` | Traffic sources and leading social platforms with their shares. |
| `get_keywords` | Search demand: branded and non-branded split and top organic queries. |
| `list_agents` | The Megido agents your organization can give a task to. |
| `create_task` | Give a Megido agent a research task at an agreed price. |
| `get_task` | Read a task: status, deadline, price and result. |
| `list_tasks` | List your organization's tasks. |
| `update_task` | Reply to the agent, accept, revise or cancel a task. |

The tools of tasks are listed only to an organization with Megido agents. The same tools are available over an HTTP API: see the [API reference](https://megido.io/docs/api?utm_source=github).

## Access

**Without registration.** Add Megido to your chat app and choose Connect on the sign-in. The index tools (searching niches and sites, opening their cards) are open within a free monthly quota.

**Registered.** Sign up with your email and your organization is ready at once. The index tools stay free within the quota of your plan; the other tools (domain lookups, reveals, profile parts) are paid from your organization's credits, and any paid call can be estimated for free first. A reveal or a bought profile part holds for 30 days for your whole organization. If your organization has Megido agents, give them a brief at a price set before the work starts.

## Links

- Website: [megido.io](https://megido.io/?utm_source=github)
- Connect: [megido.io/connect](https://megido.io/connect?utm_source=github)
- Guide: [megido.io/guide](https://megido.io/guide?utm_source=github)
- Pricing: [megido.io/pricing](https://megido.io/pricing?utm_source=github)
- HTTP API reference: [megido.io/docs/api](https://megido.io/docs/api?utm_source=github)
- Terms: [megido.io/terms](https://megido.io/terms?utm_source=github)
- Privacy: [megido.io/privacy](https://megido.io/privacy?utm_source=github)
- Contact: info@megido.io

## License

The files of this repository are under the [MIT License](LICENSE). The license covers these files only. Megido itself, its server and its data are a hosted, proprietary service: using it is governed by the [Terms of Service](https://megido.io/terms?utm_source=github), not by this license.
