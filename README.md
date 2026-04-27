# LinkedIn Saved Posts — Collections UI

A redesigned LinkedIn "Saved Posts" experience that solves the problem of unorganized, hard-to-navigate saved content.

---

## The Problem

LinkedIn's current saved posts feature is a flat, undifferentiated list. Every post you save ends up in the same place — no grouping, no categorization, no way to quickly jump to posts about a specific topic. Over time this becomes a graveyard of good content that's nearly impossible to navigate.

**Pain points with the current experience:**
- No way to separate UX articles from dev tutorials from career advice
- Finding a specific saved post means endlessly scrolling
- No context for why you saved something or where it fits
- The "All / Articles" filter tabs are the only navigation available

---

## The Solution

A **Collections-based saved posts system** that lets users organize saved content into named buckets — similar to how Pinterest boards or Spotify playlists work, but native to LinkedIn's design language.

### Key features

**Collection filter dropdown**
A pill-shaped dropdown at the top of the feed lists all your collections with item counts. Switching collections instantly filters the feed to show only posts saved to that bucket.

**Save to collection prompt**
When saving any post, a modal appears asking which collection to save it to — with a list of existing collections, item counts, and a "Create new collection" option inline.

**Collection tag on each card**
Every saved post card shows a small tag chip below the author line indicating which collection it belongs to. Clicking the chip filters the feed to that collection.

**New collection creation**
A "+ New Collection" button in the header opens a modal with a name input. New collections are immediately available in the dropdown and save modal.

---

## Interactions

| Action | Result |
|---|---|
| Click "All Saved" dropdown | Opens collection picker with counts |
| Select a collection | Filters feed to matching posts only |
| Click bookmark icon on a card | Opens "Save to collection" modal |
| Click collection tag chip | Jumps to that collection |
| Click "+ New Collection" | Opens create modal |
| Create a collection | Added to dropdown and modal lists instantly |

---

## Design

Built to match LinkedIn's design system:
- Colors: `#0A66C2` blue, `#F3F2EF` background, `#057642` green for active states
- Typography: LinkedIn's system font stack
- Components: pill buttons, card layouts, modal overlays — all consistent with LinkedIn's existing patterns

The goal was to feel like a natural extension of LinkedIn, not a redesign — something that could ship as a feature without breaking the existing visual language.

---

## APIs & Services Used

| Service | Purpose | Endpoint |
|---|---|---|
| [unavatar.io](https://unavatar.io) | Fetch LinkedIn profile photos by username | `https://unavatar.io/linkedin/{username}` |

### Profile photos resolved via unavatar.io

| Author | LinkedIn Username |
|---|---|
| Vitaly Friedman | `vitalyfriedman` |
| GK VanPatter | `gkvanpatter` |
| Robin Holesinsky | `rholesinsky` |

> `unavatar.io` proxies public social profile images — no API key required. Falls back to styled initials if the image fails to load.

---

## Live Demo

[View on Vercel →](https://linkedin-saved-collections.vercel.app)
