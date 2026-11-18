# LinkedIn Jobs Scraper: LinkedIn Scraper API for Python & Node.js (2026)

Scrape public LinkedIn job search results by keyword and location: titles, companies, locations, posting dates, salaries, full descriptions, and optional company page details.

**[▶ Try the LinkedIn Jobs Scraper free on Scrapely](https://scrape.ly/store/openrole/linkedin-jobs-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape LinkedIn data with the [LinkedIn Jobs Scraper](https://scrape.ly/store/openrole/linkedin-jobs-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the linkedin scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this LinkedIn scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/openrole/linkedin-jobs-scraper) or from your code with the SDK.
- **Structured linkedin data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $1.70 per 1,000 job results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when LinkedIn changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What LinkedIn data can you extract?

Scrape public LinkedIn job search results by keyword and location: titles, companies, locations, posting dates, salaries, full descriptions, and optional company page details.

| Output field |
|---|
| `title` |
| `companyName` |
| `location` |
| `postedAt` |
| `employmentType` |
| `applicantsCount` |
| `link` |

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('openrole/linkedin-jobs-scraper').call({"urls": ["https://www.linkedin.com/jobs/search/?position=1&pageNum=0"], "limitPerSource": 20});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('openrole/linkedin-jobs-scraper').call(run_input={ "urls": [ "https://www.linkedin.com/jobs/search/?position=1&pageNum=0" ], "limitPerSource": 20 })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/openrole~linkedin-jobs-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "urls": [
    "https://www.linkedin.com/jobs/search/?position=1&pageNum=0"
  ],
  "limitPerSource": 20
}
```

See every input option on the [LinkedIn Jobs Scraper page](https://scrape.ly/store/openrole/linkedin-jobs-scraper).

## Pricing

**$1.70 per 1,000 job results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/openrole/linkedin-jobs-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape LinkedIn with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape LinkedIn with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a linkedin scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/openrole~linkedin-jobs-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping LinkedIn legal?** This scraper collects publicly available data. Check LinkedIn's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Related LinkedIn scrapers

- [LinkedIn Profile Scraper](https://github.com/alexrosuleks/linkedin-profile-scraper): Extract public LinkedIn profile details from profile URLs, public identifiers, or profile IDs: name, headline,…
- [LinkedIn Company Search](https://github.com/alexrosuleks/linkedin-companies-search): Search LinkedIn companies by keyword, industry and location and scrape public profiles: size, industry, HQ and website.…
- [LinkedIn Post Scraper](https://github.com/alexrosuleks/linkedin-post-scraper): Scrape public LinkedIn posts by URL or profile: text, author, date, reactions, comments and media. No login or cookies…
- [LinkedIn People Search](https://github.com/alexrosuleks/linkedin-people-search): Search public LinkedIn profiles by keyword, job title, company and location: name, headline, company, location and URL.…
- [LinkedIn Ad Library Scraper](https://github.com/alexrosuleks/linkedin-ads-scraper): Scrape LinkedIn Ad Library ads by company, keyword or payer: copy, creatives, CTA, payer, run dates, impressions,…

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** linkedin jobs scraper, linkedin scraper, linkedin scraper api, linkedin scraper python, linkedin scraper node.js,
scrape linkedin, linkedin data extraction, linkedin crawler, linkedin api, export linkedin data to csv, linkedin-jobs-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/openrole/linkedin-jobs-scraper).
