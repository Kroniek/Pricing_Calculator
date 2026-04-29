# Kit Pricing Calculator

A standalone, browser-based pricing tool. Built for STEM kits, bundles, and any product where you need to think through BOM costs, channel margins, MRP positioning, and quotations — all in one place, with no backend.

**Live:** https://<your-username>.github.io/aerolab-pricing/

## What it does

- **BOM with sub-components** — build a 3-level part tree where sub-component costs roll up to the main, and the main rolls into your COGS automatically.
- **Operational costs & amortized assets** — packaging, labour, display stands, tooling. Spread asset costs over N kits sold.
- **Distribution chain pricing** — D2C, retailer, distributor, or full chain. Margin sliders at each level. Live pricing chain visualization.
- **Recommended price + ceiling analysis** — get an MRP recommendation plus a ceiling driven by the lower of (a) 70% margin threshold or (b) 2.5× COGS market psychology cap.
- **Cost split-up by component** — see which parts dominate your cost structure.
- **Quotation mode** — toggle on to add multiple line items, manage them as tabs, and export a customer-facing PDF quotation with a separate internal cost sheet.
- **Inventory database** — load parts and full kit configurations from a Google Sheet (default master sheet built-in, swappable) or upload Excel/CSV files. Type a part name in the BOM and autocomplete fills cost, type, and category.
- **Live market benchmarks** — pull real competitor prices from Indian e-commerce sites (Amazon.in, Flipkart, robu.in, etc.) via Gemini API with Google Search grounding. Free tier, no card required. Auto-retries with model fallback if Google's servers spike.
- **PDF export** — quotation mode produces a professional 2-page PDF (customer quote + internal cost sheet). Single-item mode exports a detailed pricing sheet.

## Setup

No installation. No build step. No backend. Just open `index.html` in a browser, or visit the hosted URL above.

For the live market benchmarks feature, you'll need a free Gemini API key from https://aistudio.google.com/apikey (30 seconds, no credit card). The key is stored in your browser's localStorage — it never leaves your device and is never embedded in this file.

## Tech

- Vanilla HTML, CSS, JavaScript — single file, no dependencies bundled
- SheetJS (CDN) for Excel/CSV parsing
- Gemini 2.5 Flash + Google Search grounding for market data
- Google Fonts: Outfit + JetBrains Mono

## Privacy

Everything runs in your browser. Inventory data, API keys, market cache, and master sheet config are all stored in localStorage on whatever device you're using. Loading the public URL on a new device gives you a blank slate — you re-load your inventory from the Google Sheet (which is the single source of truth) and re-enter your API key.

## License

Internal use by Kroniek.
