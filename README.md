# JAI-Assay — website

Public marketing site for **JAI-Assay**, the judging-as-a-service product from
JAI Studios: _"You generate the data. We assay its quality."_ A blind 3-judge
panel scores synthetic training data against a published rubric, reports
inter-judge agreement, and issues a reproducible certification mark.

Served at [jaistudios.app](https://jaistudios.app). Static HTML/CSS — no build step.

## Structure

- `index.html` — product landing page
- `rubric.html` — the published scoring rubric (dimensions, 1–5 scale, calibration examples)
- `privacy.html` — privacy summary (transient-by-default data handling)
- `terms.html` — preliminary private-beta terms
- `style.css` — design system (Fraunces + IBM Plex Sans/Mono; deep ink + assayed gold)
- `og.png` — social share card (1200×630)
- `og-image.html` — source for `og.png`; render at 1200×630 and screenshot to regenerate (not served)

## Email capture

The early-access form in `index.html` (`#access`) posts an `email` field. Set the
form `action` to your form-backend endpoint to activate it:

```html
<form id="access-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

Until a real endpoint is set, the form gracefully falls back to a `mailto:` so the
page is never a dead end. With JS it submits via `fetch` and shows an inline
confirmation; without JS it does a normal POST.

## Confidential

The site never names the judge models, providers, or panel/consensus internals —
only "three independent model lineages." Keep it that way: backend execution
details stay private. The rubric (what we measure) is public; the rig (how we run
it) is not.

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
