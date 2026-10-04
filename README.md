# Greca House: Greek Property

Search Greca House's current property listings in Greece, open a listing, compare Greca House's dated
asking-price research by area or budget, and estimate the costs of buying a resale property in Greece.
Greca House is an independent real-estate brokerage in central Athens.

## What it connects to

The plugin declares one remote MCP server, `https://grecahouse.com/mcp` (HTTP, read-only, no sign-in).
It runs nothing on your machine and asks for no credentials.

It also includes one skill, `greek-property-search`, a plain-text guide that tells Claude which tool to use for searches, budgets and costs and how to state the scope of every figure. The skill runs no code and fetches nothing itself.

| Tool | What it does |
| --- | --- |
| `search_greece_properties` | Search Greca House's current public listings by area, region, sale or rent, type, price, bedrooms (exact or range), size, media and Golden Visa classification |
| `get_property_details` | One listing by its GH reference: description, facts, features, media links, page URL |
| `compare_budget_by_area` | Greca House's dated asking-price research by area, and what a budget is listed for |
| `get_greece_market_research` | The research reports, method and CSV downloads |
| `estimate_greece_buying_costs` | Transfer tax, municipal surcharge, Cadastre and notary scale fee on a price; professional fees only from your quotes |

## What is sent, and what is kept

When Claude calls a tool, it sends only that tool's arguments (for example an area, a budget, a property
type or a listing reference) to `grecahouse.com`. Your conversation, name and contact details are not
sent. Nothing creates an enquiry or stores your request. Like every request to the website, each call is
recorded in Google Cloud request logs (time, path, result, the calling server's address and software,
response time) and an application log of which tool ran and whether it succeeded, kept for 30 days; a
one-way hash of the calling address is kept for up to 24 hours to prevent abuse. Full notice:
https://grecahouse.com/en/privacy-policy

## Limits

- Results are Greca House's own listings, not every property in Greece. Prices are asking prices.
- Research is a dated snapshot of those listings' asking prices: not a forecast, a trend or a whole-market index.
- A Golden Visa classification is Greca House's office classification of the property route. It does not
  decide an applicant's eligibility and is not legal advice.
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

Support: https://grecahouse.com/en/contact
