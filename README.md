# Taste by Sight

A swipe-based crossmodal taste test by Living Room Labs. People swipe through 16 abstract texture plates and get one of four coffee flavour profiles, with matching coffees from Hermanos Coffee Roasters. Built to promote the Living Room Labs coffee tasting in November.

**Live:** https://bgolumbeanu01-cell.github.io/taste-by-sight/

## How it works

Each plate combines colour, shape and texture cues that published research links to taste (sources are listed on the page under "The science"). A right swipe adds the plate's scores on five dimensions (sweet, bright, floral, intense, cocoa/body) and a left swipe subtracts half. The nearest of four profiles wins, by cosine similarity. Plates are shown in random order.

## Editing

Everything lives in `index.html`. The block marked `EDIT HERE` near the top of the script holds:

- `EVENT_URL`: the Luma waitlist for the tasting. The same link is also written into the two "Join the waitlist" buttons in the HTML, so change it in all three places.
- `COFFEES`: the two coffee picks per profile.

Commit to `main` and GitHub Pages redeploys in about a minute.

## Link preview image

`og-image.png` is the 1200×630 preview shown on WhatsApp, LinkedIn and X. To regenerate it, open `index.html?og` in Chrome at 1200×630 and screenshot it:

```sh
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless=new --hide-scrollbars \
  --window-size=1200,630 --virtual-time-budget=10000 \
  --screenshot="$PWD/og-image.png" "file://$PWD/index.html?og"
```

If the site moves to a custom domain, update the `og:url` and `og:image` addresses in the `<head>`.
