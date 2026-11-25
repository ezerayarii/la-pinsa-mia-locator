# La Pinsa Mia: Market Locator

A one-page web app that helps customers find the farmers' market where La Pinsa Mia is selling: type a ZIP code and
it shows the nearest market, its day and time, a map pin and a Google Maps link. Built as a single HTML file with no
build step (course project, IT 599).

**Live demo:** https://ezerayarii.github.io/la-pinsa-mia-locator/

<!-- TODO: add a screenshot (docs/screenshot.png) -->

## Features

- **ZIP search**: exact match first, then the nearest market by distance; results show the market, schedule, drive
  directions and a share button.
- **Interactive map** (Leaflet + CARTO tiles): every market is a pin; the matched one is highlighted.
- **Admin tab**: add, edit, delete, sort and filter markets; export the data as JSON; reset to the defaults.
- **Search analytics**: every search is logged (matched / nearest / AI) with a county breakdown.
- **Optional AI fallback**: for ZIP codes far from any market, it can ask OpenAI (gpt-4o-mini, JSON mode) for the
  best market and a drive-time estimate. It's **off in the public demo**: a browser page can't keep an API key secret,
  so this needs a small server-side proxy.
- Data is saved in the browser's `localStorage` (no backend).

## Tech

HTML, Tailwind CSS (CDN), vanilla JavaScript, Leaflet, `localStorage`, OpenAI Chat Completions API (optional).

## Run it

Open `index.html` in a browser, or serve the folder:

```bash
python -m http.server 8000   # http://localhost:8000
```

## Status

Working as a static demo. Next steps: move the market data and the AI call to a small backend (so the key stays on
the server and edits are shared between devices).

## License

MIT, see [LICENSE](LICENSE).
