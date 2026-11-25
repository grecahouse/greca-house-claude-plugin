# Greca House: Greek Property

Search Greca House's current property listings in Greece, open a listing, compare Greca House's dated
asking-price research by area or budget, and estimate the costs of buying a resale property in Greece.
Greca House is an independent real-estate brokerage in central Athens.

## Example requests

- "Find 2-bedroom apartments in Athens up to €300,000."
- "Which commercial buildings or hotels does Greca House have for sale in Attica?"
- "Give me the details, photos and 3D tour of GH-108420."
- "Compare asking prices in Kolonaki and Pangrati in Greca House's research."
- "What would buying a €250,000 resale apartment in Greece cost on top of the price?"

The assistant answers from Greca House's own current listings and dated research and says what each
figure covers: which regions, whether a price cap includes the cap, and the snapshot date.

## Use it in Claude (web, desktop, mobile and Cowork)

Adding the plugin gives Claude the Greca House skill. Claude does not add the plugin's connector for you, so there is one more step before it can search Greca House's listings.

1. Open Customize > Plugins, find "Greca House: Greek Property" under Discover, and click Add.
2. Open the plugin, go to its Connectors tab, and add the connector listed there. It points to https://grecahouse.com/mcp.
3. The connector needs no sign-in. Claude may label it Custom and show a notice that custom connectors reach services it has not verified. The label means the connector was added by address. This one is read-only, and what it sends is listed under "What is sent, and what is kept" below.
4. In a new chat, click + then Connectors, and make sure the Greca House connector is switched on.
5. Ask about Greek property. The first time Claude uses a Greca House tool it may ask for approval: choose Allow once or Always allow.

If Claude answers without searching Greca House's listings, check step 4 first.

In Cowork, install the plugin the same way, then connect the connector from the plugin's Connectors tab.

On Team and Enterprise plans an Owner adds the connector once under Organization settings > Connectors, and members then connect it with their own account. Plugins need a paid plan. On the Free plan you can still add the connector yourself: in Customize > Connectors, add a custom connector with the address https://grecahouse.com/mcp and choose no sign-in.

Do steps 1 and 2 on claude.ai or in the desktop app. Once the connector is added, it is available in the mobile app too, where you switch it on under + > Connectors.

## What it connects to

The plugin declares one remote MCP server, `https://grecahouse.com/mcp` (HTTP, read-only, no sign-in).
It runs nothing on your machine and asks for no credentials.

It also includes one skill, `greek-property-search`, a plain-text guide that tells the assistant which tool to use for searches, budgets and costs and how to state the scope of every figure. The skill runs no code and fetches nothing itself.

| Tool | What it does |
| --- | --- |
| `search_greece_properties` | Search Greca House's current public listings by area, region, sale or rent, type, price, bedrooms (exact or range), size, media and Golden Visa classification |
| `get_property_details` | One listing by its GH reference: description, facts, features, media links, page URL |
| `compare_budget_by_area` | Greca House's dated asking-price research by area, and what a budget is listed for |
| `get_greece_market_research` | The research reports, method and CSV downloads |
| `estimate_greece_buying_costs` | Transfer tax, municipal surcharge, Cadastre and notary scale fee on a price; professional fees only from your quotes |

## What is sent, and what is kept

When the assistant calls a tool, it sends only that tool's arguments (for example an area, a budget, a property
type or a listing reference) to `grecahouse.com`. Your conversation, name and contact details are not
sent. Nothing creates an enquiry or stores your request. Like every request to the website, each call is
recorded in Google Cloud request logs (time, path, result, the calling server's address and software,
response time) and an application log of which tool ran and whether it succeeded, kept for 30 days; a
one-way hash of the calling address is kept for up to 24 hours to prevent abuse. Full notice:
https://grecahouse.com/en/privacy-policy

## Limits

- Results are Greca House's own listings, not every property in Greece. Prices are asking prices.
- Research is a dated snapshot of the asking prices on Greca House's own listings.
- The Golden Visa classification is Greca House's own classification of a listing's property route. It is
  not legal advice; confirm your own case with a qualified Greek lawyer.
- Buying-cost estimates are not legal or tax advice; lawyer, engineer and agency fees are never estimated
  as percentages, only added from amounts you give.
- Buying-cost estimates use the rates in force when they were read. A change the government has announced
  but not yet enacted is listed beside the estimate and never applied.

## Install

In Claude Code:

```
/plugin marketplace add grecahouse/greca-house-claude-plugin
/plugin install greca-house@greca-house
```

## Update

```
/plugin marketplace update greca-house
/plugin update greca-house@greca-house
```

Restart Claude Code to load the new version.

## Uninstall

```
/plugin uninstall greca-house@greca-house
/plugin marketplace remove greca-house
```

## Other agents

The same package works in agents that read this plugin layout. Each points at the same read-only server;
nothing else is installed.

- **Cursor:** `.cursor-plugin/plugin.json` and `mcp.json`. Once listed in the Cursor Marketplace, install
  it from there. Until then, add the server yourself in `~/.cursor/mcp.json`:

  ```json
  { "mcpServers": { "greca-house": { "url": "https://grecahouse.com/mcp" } } }
  ```

- **Grok Build:** reads `.claude-plugin/plugin.json` and `.mcp.json`. Once listed in the xAI plugin
  marketplace, type `/marketplace` and install `greca-house`.

Support: https://grecahouse.com/en/contact
