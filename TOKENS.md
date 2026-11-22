# Linica foundation tokens

This document maps the roles in [`tokens.json`](tokens.json) to the screens that prove them. It does not restyle either Flutter app.

Export scale: every PNG in `booking-app/` and `inventory-app/` is 188px wide. The Adobe XD artboards are 375px wide (scale 375/188 ≈ 1.9947). Values below are either exact samples from those PNGs, the 4/8 spacing rule from the historical README, or an explicit `TODO`.

The historical README (commit `f1e3b92`, the text issues #1–#3 refer to) recommended a soft rose/coral primary, teal or graphite accents, off-white surfaces, charcoal text, and an 8px spacing base. The current README dropped that section when the clickable prototype was added on 18 November 2026. Where the mockups and that written direction disagree, the mockups win and the disagreement is called out. Rose/coral is **not** published as a token: it does not appear in the product PNGs.

The HTML prototype viewer in `prototype/index.html` uses rose `#BD7779` and canvas `#F7F5F2`. Those colours style the viewer chrome only. Do not implement them as product tokens.

## Colour

| Role | Value | Screen that proves it | PNG |
| --- | --- | --- | --- |
| `primary` | `#156571` (teal) | Sign-in header and the SIGN IN footer action | [`booking-app/signin.png`](booking-app/signin.png), [`inventory-app/signin.png`](inventory-app/signin.png) |
| `primary` | `#156571` | Un-allocated segment and selected “Overview” navigation | [`inventory-app/overview.png`](inventory-app/overview.png), [`inventory-app/reports.png`](inventory-app/reports.png) |
| `accent` | `TODO` — sky blue, antialiased only | Clinic/location labels (“KPA - HQ @ Parkdale”) | [`booking-app/select-nurse.png`](booking-app/select-nurse.png), [`booking-app/review-pay.png`](booking-app/review-pay.png), [`booking-app/treatments.png`](booking-app/treatments.png) |
| `surface` | `#FFFFFF` | Page fill on interior booking and inventory screens | [`booking-app/treatments.png`](booking-app/treatments.png), [`booking-app/review-pay.png`](booking-app/review-pay.png), [`inventory-app/overview.png`](inventory-app/overview.png) |
| `text` | `#000000` | Headlines and body (“Treatments”, “Review & Pay”, “Inventory Levels”) | [`booking-app/treatments.png`](booking-app/treatments.png), [`booking-app/review-pay.png`](booking-app/review-pay.png), [`inventory-app/overview.png`](inventory-app/overview.png) |
| `error` | `#E33C3C` | Temperature warning icon and out-of-range bar | [`inventory-app/reports.png`](inventory-app/reports.png), [`inventory-app/report-outside-temps.png`](inventory-app/report-outside-temps.png) |
| `error` | `#E33C3C` (Cancel samples `#E33F3F`) | Cancel control on an upcoming appointment | [`booking-app/current-services-name-4.png`](booking-app/current-services-name-4.png) |
| `success` | `#00CC99` | “5% increase in usage this week” and in-range temperature | [`inventory-app/reports.png`](inventory-app/reports.png) |
| `warning` (ink) | `TODO` — mustard/gold, antialiased only | “LOW UN-ALLOCATED STOCK” chip label and icon | [`inventory-app/overview-low-un-allocated-stock.png`](inventory-app/overview-low-un-allocated-stock.png) |
| `warningSurface` | `#EFECD9` | Fill of that low-stock chip | [`inventory-app/overview-low-un-allocated-stock.png`](inventory-app/overview-low-un-allocated-stock.png) |

Supporting fills, not substitutes for the required roles: `errorSurface` `#FAD8D8` on [`inventory-app/report-outside-temps.png`](inventory-app/report-outside-temps.png); `successSurface` `#CCF5EB` on [`inventory-app/reports.png`](inventory-app/reports.png); `surfaceSubtle` `#FAFAFA` on treatment cards in [`booking-app/treatments.png`](booking-app/treatments.png).

Open questions:

- **Accent:** what is the exact sky-blue hex for location labels in the Adobe XD specs? PNG samples include `#228CFF` and `#278EFF` plus mid-blues from antialiasing. `#027BFF` has been mentioned in app design-parity notes but was not a solid sample in these exports and is not used here.
- **Warning ink:** what is the exact mustard/gold hex for the low-stock chip text in the Adobe XD specs?

## Spacing, radius, elevation, type

| Token | Value | Proving screen / rule | PNG or source |
| --- | --- | --- | --- |
| Spacing scale | 4px increments, 8px base | Historical README foundation rule | Commit `f1e3b92` |
| `radius.card` | `TODO` | Card corners are hairline-bordered and antialiased at this export size | [`booking-app/review-pay.png`](booking-app/review-pay.png), [`booking-app/treatments.png`](booking-app/treatments.png) |
| `radius.button` | `TODO` | See the slot-chip observation in `tokens.json`; primary CTAs were not a clean count | [`booking-app/treatment-time-selected-1.png`](booking-app/treatment-time-selected-1.png), [`booking-app/review-pay.png`](booking-app/review-pay.png) |
| `elevation.card` | `0` | Cards use a light hairline border, not a drop shadow | [`booking-app/review-pay.png`](booking-app/review-pay.png), [`inventory-app/reports.png`](inventory-app/reports.png) |
| Type `headline`, `body`, `label` | Roles only; sizes `TODO` | Confirm size, weight and line height in XD. Licensed font files are not in this repo. | Adobe XD specs |

A developer can use `color.surface` `#FFFFFF` and `elevation.card` `0` with a hairline border without guessing those values. Do not guess `radius.card`; confirm it in XD before implementing a card.

## Current app themes are not canonical

Do not copy the following into `tokens.json` as brand tokens. Some values happen to match the mockups because the apps have already started adopting measured colours; that does not make the app themes the source of truth.

### Booking app (`fe-fltr-linica`)

Shared theme, `lib/theme.dart` `LinicaColors` on `main`:

- surface `#FFFFFF`
- ink `#000000`
- brand `#156571`
- border `#DBDBDB`
- subtle `#EFEFF2`

The issue text described a black app bar and a cyan accent. That is no longer the shared theme. Cyan remnants remain in `lib/screens/booking/booking_calendar.dart` (`Colors.cyan.shade700`), `lib/helpers/dialog.dart` (`Colors.cyan`), and `lib/components/photo_component.dart` (`Colors.cyan.shade900`). Those leftovers are not brand tokens.

### Inventory app (`fe-fltr-inventory`)

Shared theme, `lib/theme/inventory_theme.dart` `InventoryTheme` on `main`:

- brand `#156571`
- ink `#12131A`
- muted `#59616A`
- border `#DBDBDB`
- subtle `#EFEFF2`
- warning `#8B3700` and warning surface `#FFF3DF`
- danger `#AE2424`
- scaffold white, primary actions black

The issue text cited background `0xFF0B232F` and accent `0xFF1E8B7E`. Those hex values are no longer in the shared theme. The current warning and danger hexes also do not match the PNG solids `#EFECD9` / `#E33C3C` and must not be copied forward as brand tokens.

Neither app is restyled in this issue.
