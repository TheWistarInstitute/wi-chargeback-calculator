# Wistar Storage Chargeback Calculator

Calculator for the Wistar Data Storage Policy: `index.html` plus the logo in
`assets/`. Hosted on GitHub Pages; pushing to `main` updates the live site.

## Change prices or allowances

In `index.html`, search for `PRICES!`:

```js
const ACTIVE = { allowance: 50, tiers: [
  { id: "fast",   name: "Fast",            rate: 36.50, ... },
  ...
]};
const ARCHIVE = { allowance: 200, tiers: [ ... ]};
const RETRIEVAL = [ ... ];
```

- `allowance`: included TB per lab or core.
- `rate` in `ACTIVE` and `ARCHIVE`: $ per TB per month above the allowance.
- `rate` in `RETRIEVAL`: approximate $ per TB retrieved.

Use plain numbers (no `$` or commas). Don't change `id` values.

The "about $92 per TB" transfer note is hard-coded; search for `$92` to
update it.

## Test

Open `index.html` in a browser and click **Example 1**. At current rates it
shows **$298.10/month**.

## Publish

```bash
git add index.html
git commit -m "Update storage prices"
git push
```

Also update the policy article in Confluence.
