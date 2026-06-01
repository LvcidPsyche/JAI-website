# JAI-Assay — website

Public marketing site for **JAI-Assay**, the judging-as-a-service product from
JAI Studios: _"You generate the data. We assay its quality."_ A blind 3-judge
panel scores synthetic training data against a published rubric, reports
inter-judge agreement, and issues a reproducible certification mark.

Served at [jaistudios.app](https://jaistudios.app). Static HTML/CSS — no build step.

## Structure

- `index.html` — product landing page
- `privacy.html` — privacy summary (transient-by-default data handling)
- `terms.html` — preliminary private-beta terms
- `style.css` — design system (Fraunces + IBM Plex Sans/Mono; deep ink + assayed gold)

## Local preview

Open `index.html` directly, or serve the directory:

```sh
python -m http.server 8000   # then open http://localhost:8000
```

Fonts load from Google Fonts; everything else is self-contained.

## Notes

- Pre-launch posture: CTAs route to `hello@jaistudios.app` for early access
  (no live billing yet). Pricing shown is launch pricing.
- Product facts (marks, dimensions, pricing) mirror the engine spec; keep them
  in sync with `jai-engine/plans/2026-05-26-jai-assay-spec.md`.

## License

MIT. See `LICENSE`.
