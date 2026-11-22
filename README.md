# Linica Design System

## Clickable prototype

[Open the booking and inventory prototype](prototype/index.html). It includes 19 booking screens and 9 inventory screens, product switching, screen search, keyboard navigation, flow progress and enlarged image viewing.

### Download and present offline

[Download the repository ZIP](https://github.com/Linica-Co/design/archive/refs/heads/main.zip). Extract it, then open `prototype/index.html` in a browser. Keep the extracted `booking-app/` and `inventory-app/` folders alongside the `prototype/` folder so the screen images load. The prototype can also be opened from a local server:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000/prototype/`.

The repository is private, so downloading the ZIP requires repository access. GitHub Pages sharing is likewise subject to this repository's visibility and organization settings; the design screens should not be made publicly accessible without approval.

## Design tokens

Foundation tokens for colour, spacing, radius, elevation and type live in [`tokens.json`](tokens.json). [`TOKENS.md`](TOKENS.md) maps each token to the screen that proves it and records where the current Flutter themes are not canonical. Open questions are marked `TODO` rather than filled with guessed values.

## Design assets

- [`booking-app/`](booking-app/) contains the customer booking screens.
- [`inventory-app/`](inventory-app/) contains the inventory management screens.
- [`Linica Process User Flow.pdf`](Linica%20Process%20User%20Flow.pdf) describes the overall process journey.

## Hosted Adobe XD prototypes

- [Linica Booking App](https://xd.adobe.com/view/4e6c66a5-7d83-449f-84a2-e2997acd2607-1b3f/)
- [Linica Inventory App](https://xd.adobe.com/view/f8860247-986a-4ade-b765-bd8913df201d-add5/)
