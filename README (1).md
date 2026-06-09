# B2B Multi-Touch Attribution Calculator

A single-file, zero-dependency tool for modeling pipeline revenue across five attribution frameworks. Built for B2B demand gen marketers who want to understand how channel credit shifts depending on which model their organization uses.

**[Live demo →](https://jessicacarin.github.io/b2b-attribution-calculator/)**

---

## What it does

Enter your pipeline value, deal count, and the number of touchpoints per channel for a typical buyer journey. The calculator instantly shows how each of five attribution models distributes credit across those channels — and where the numbers diverge.

### Five attribution models

| Model | Logic | Best for |
|-------|-------|----------|
| **First touch** | 100% credit to the first channel engaged | Measuring pipeline source, top-of-funnel reach |
| **Last touch** | 100% credit to the channel before opportunity creation | Simple CRM reporting, bottom-funnel conversion |
| **Linear** | Equal credit across all touchpoints | Baseline channel coverage analysis |
| **Time decay** | Higher credit to touchpoints closer to conversion (7-day half-life) | Recency-weighted influence analysis |
| **U-shaped** | 40% first touch, 40% last touch, 20% distributed across middle touches | Balancing acquisition and conversion in B2B |

### Six channels tracked

- Paid search
- Content / SEO
- Email
- Events / webinars
- Paid social
- Direct / referral

---

## Why this matters

Attribution is one of the most contested conversations in B2B marketing. The same pipeline number looks completely different depending on which model your org uses:

- A **paid search team** will look like a pipeline driver under first touch, but nearly invisible under time decay if deals take 90+ days to close.
- An **email nurture program** with 4–5 touches will show meaningful credit under linear or U-shaped, but get buried under first and last touch models.
- **Events and webinars** often appear mid-journey — they rarely show up in first or last touch reports, which is why event ROI is chronically undercounted.

This tool makes those tradeoffs visible before you walk into a budget conversation.

---

## How to use it

1. Open `index.html` in any browser — no install, no dependencies, no server required
2. Set your pipeline value and number of deals
3. Adjust touchpoint counts to reflect your actual channel mix
4. Switch between models using the tab bar to see how credit shifts
5. Use the comparison chart and full table to build your attribution narrative

---

## Use cases

- **QBR prep:** Show leadership why your channel mix looks different depending on which attribution model the data team uses
- **Budget defense:** Quantify the pipeline influence of nurture programs and content that get buried under last-touch reporting
- **MarTech evaluation:** Demonstrate attribution modeling capability to stakeholders evaluating MAP or CRM configurations
- **Team alignment:** Facilitate the model-selection conversation with sales, finance, and marketing ops before committing to a reporting standard
- **Training:** Walk new demand gen hires through why attribution methodology matters before they touch the dashboards

---

## Technical notes

- Pure HTML, CSS, and vanilla JavaScript — no frameworks, no build step
- Chart.js loaded via CDN for the comparison visualization
- Fully responsive down to mobile
- Dark mode support via `prefers-color-scheme`
- All attribution math is in the browser; no data is sent anywhere

### Attribution math reference

**Time decay** uses a half-life formula:

```
weight(i) = touches(i) × 0.5^((n - 1 - i) / half_life)
```

Where `i` is the touchpoint position (0 = first), `n` is the total number of channels, and `half_life = 7`. Weights are normalized to sum to 1.

**U-shaped** logic:

```
if 2 active channels:  50% first, 50% last
if 3+ active channels: 40% first, 40% last, 20% ÷ middle touches
```

---

## Customization

The channel list, default touchpoint values, and model set are all defined in the `<script>` block near the bottom of `index.html`. To add a channel:

```javascript
const CHANNELS = [
  // existing channels...
  { id: 'partner', label: 'Partner / channel', color: '#D85A30', badge: 'badge-coral' },
];

const DEFAULTS = {
  // existing defaults...
  partner: 1,
};
```

To modify the time decay half-life (default is 7 days), update:

```javascript
const HALF_LIFE = 7; // inside the 'timedecay' case
```

---

## About

Built by [Jessica Johnson](https://jessicacarin.github.io) — senior digital marketing professional specializing in demand generation, lifecycle marketing, and marketing operations. This tool grew out of recurring attribution debates in budget cycles and QBRs where the same pipeline data told completely different stories depending on the reporting model.

More at [jessicacarin.github.io](https://jessicacarin.github.io) and the [AI Marketing Prompt Library](https://github.com/jessicacarin/ai-marketing-prompt-library).

---

## License

MIT — use it, fork it, adapt it.
