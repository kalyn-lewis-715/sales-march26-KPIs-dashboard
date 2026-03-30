# Visme — Sales KPI Dashboard

A self-contained HTML dashboard pulling live HubSpot data, styled to match the Visme Enterprise Retention Analysis. Embeds directly into Notion via GitHub Pages.

## Setup

### 1. HubSpot Private App token
- HubSpot → Settings → Integrations → Private Apps
- Create app with read-only scopes: `crm.objects.contacts.read`, `crm.objects.deals.read`
- Copy the token (starts with `pat-`)

### 2. Add token to the file
Open `index.html`, find this line near the bottom:
```js
const HS_TOKEN = (new URLSearchParams(...).get('token')) || 'YOUR_HUBSPOT_PRIVATE_APP_TOKEN_HERE';
```
**Option A** — Replace the placeholder with your token (keep repo private).
**Option B** — Leave as-is and append `?token=YOUR_TOKEN` to the embed URL in Notion.

## Deploy to GitHub Pages
```bash
git init
git add index.html README.md
git commit -m "Initial dashboard"
git remote add origin https://github.com/YOUR_USERNAME/visme-sales-dashboard.git
git push -u origin main
```
Then: Repo Settings → Pages → Source: main / root → Save.
Your URL: `https://YOUR_USERNAME.github.io/visme-sales-dashboard/`

## Embed in Notion
1. On the Sales Dashboards page, type `/embed`
2. Paste your GitHub Pages URL
3. Resize to 1000–1200px tall

Changes pushed to GitHub are reflected in Notion automatically on next load.

## Tabs
| Tab | Contents |
|---|---|
| Overview | Won ARR YTD (YoY), deal volume, close rate, inbound lead volume |
| Leads → Deals | Won/Lost/Open ARR, conversion rate, stage breakdowns, funnel table |
| Funnel: Inbound Leads | Lead volume by month, geo/form/DQ breakdowns, nonSQL pie, 2025 vs 2026 |
| Won Analysis | Why buying, persona/dept, deal type, velocity, fast/slow closer patterns |
| Lost Analysis | Lost count/ARR YoY, top reasons, stacked chart, free-text notes by category |

## Aug 2025 annotation
CTA change "Get a Demo" → "Contact Sales" is marked on Funnel and Lost Analysis charts.
