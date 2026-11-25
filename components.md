# Linica core components

Inventory of the components implied by the mockups, for issue #2. Token *roles* come from [`tokens.json`](tokens.json). Raw hex values are not repeated here; see [`TOKENS.md`](TOKENS.md) for measurements.

This issue does not restyle either Flutter app and does not add a Storybook or widget catalog in an app repo.

Filename typo: `booking-app/nurse-page-seletced.png` is the existing export name and is cited as-is.

## How to read each entry

- **Tokens:** roles the component uses. Roles still marked `TODO` in `tokens.json` (accent, warning ink, radii, type sizes) are listed by role anyway so implementers know what to ask of XD.
- **States:** only states that apply. A state with no PNG is `missing`, never a guessed screenshot.
- **Default PNG:** one existing artboard that shows the default (or otherwise named) state.

Generic interactive states — focus, loading, empty and error — are `missing` for every component unless a PNG is named under that state. No artboard in this repository shows a visible focus ring, a loading indicator, or an empty-list treatment for these components.

---

## App bar

**Tokens:** `color.surface` or `color.primary` (background, depending on variant), `color.text` or a light title on the primary bar, `type.headline` or `type.label` for the title, `spacing` for inset and action gaps.

Two variants appear in the mockups:

1. **Branded (primary fill).** Teal bar with a light title, optional back or menu action, and sometimes a search field. Proved by the sign-in header and the dashboard header.
2. **Page (surface fill).** White bar with a dark title and optional trailing icon, used on interior inventory screens.

**States**

| State | PNG |
| --- | --- |
| Default, branded | [`booking-app/current-services-name-4.png`](booking-app/current-services-name-4.png) (also [`booking-app/signin.png`](booking-app/signin.png)) |
| Default, page | [`inventory-app/reports.png`](inventory-app/reports.png) |
| Focus / loading / empty / error / success | missing |

---

## Search bar

**Tokens:** `color.primary` or `color.surface` for the field fill (on a branded header the field is a darker or lighter inset on `primary`; on a map screen the field sits on `surface`), `color.text` for entered text, a muted treatment for the placeholder (exact muted token is not in `tokens.json`), `radius.button` or a related field radius (`TODO`), `type.body` or `type.label`, `spacing` for padding and icon gap.

**States**

| State | PNG |
| --- | --- |
| Default, placeholder, on branded header | [`booking-app/current-services-name-4.png`](booking-app/current-services-name-4.png) (“Search by name or service…”) |
| Default, placeholder, over a map | [`booking-app/treatment-location.png`](booking-app/treatment-location.png) (“Search for an address or location…”) |
| Focus (cursor or query entered) | missing |
| Loading / empty / error / success | missing |

---

## Info card

**Tokens:** `color.surface` (or `color.surfaceSubtle`), `color.text`, `color.primary` for supporting metadata where it is used as a brand emphasis, `radius.card` (`TODO`), `elevation.card` (0, hairline border), `spacing`, `type.headline` / `type.body` / `type.label`.

Used for compact grouped facts: upcoming-appointment summary on the dashboard, clinic rows under “Clinics Near You”, and the stacked nurse / clinic / date rows at the top of Review & Pay.

**States**

| State | PNG |
| --- | --- |
| Default | [`booking-app/current-services-name-4.png`](booking-app/current-services-name-4.png) (upcoming appointment card and “Clinics Near You” rows) |
| Focus / loading / empty / error / success | missing |

---

## Clinic or nurse profile card

**Tokens:** `color.surface`, `color.text`, `color.accent` (`TODO`, sky-blue contact or location links), `color.primary` only where a brand-filled control is used, a selected-state treatment described below, `radius.card` (`TODO`), `elevation.card`, `spacing`, `type.headline` / `type.body` / `type.label`.

This covers both the full nurse profile and the clinic or nurse rows in lists.

**States**

| State | PNG |
| --- | --- |
| Default, list | [`booking-app/select-nurse.png`](booking-app/select-nurse.png) |
| Default, profile | [`booking-app/nurse-page.png`](booking-app/nurse-page.png) |
| Selected, list | [`booking-app/nurse-selected.png`](booking-app/nurse-selected.png) (selected name and check use a mustard/gold treatment; the exact hex is antialiased in the export and is not a foundation token) |
| Selected, profile (treatment and location chosen) | [`booking-app/nurse-page-seletced.png`](booking-app/nurse-page-seletced.png) (filename typo is original; the primary CTA is gold rather than the black CTA used on the default profile) |
| Selected, clinic list | [`booking-app/treatment-location-selected.png`](booking-app/treatment-location-selected.png) |
| Focus / loading / empty / error / success | missing |

The default clinic list without a selection is [`booking-app/treatment-location.png`](booking-app/treatment-location.png).

---

## Treatment card

**Tokens:** `color.surface` or `color.surfaceSubtle`, `color.text`, `color.accent` (`TODO`) for the clinic or location line, `radius.card` (`TODO`), `elevation.card`, `spacing`, `type.headline` / `type.body` / `type.label`.

**States**

| State | PNG |
| --- | --- |
| Default | [`booking-app/treatments.png`](booking-app/treatments.png) |
| Selected (quantity in cart, footer summary visible) | [`booking-app/treatment-selected.png`](booking-app/treatment-selected.png) |
| Focus / loading / empty / error / success | missing |

---

## Calendar and slot selector

**Tokens:** `color.surface`, `color.text`, a solid inverse treatment for the month header and the selected day or slot (the mockups use a black fill with light type, not `color.primary`), `color.accent` (`TODO`) on the booking-summary location line, `radius.button` (`TODO`) for slot chips, `spacing`, `type.headline` / `type.body` / `type.label`.

**States**

| State | PNG |
| --- | --- |
| Default, one date selected, slots unselected, footer action disabled | [`booking-app/treatment-time-selected-1.png`](booking-app/treatment-time-selected-1.png) |
| A second date outlined in addition to the selected date, slots still unselected, footer still disabled | [`booking-app/treatment-time-selected-2.png`](booking-app/treatment-time-selected-2.png) |
| Slot selected, summary shows the chosen time, footer action enabled | [`booking-app/treatment-time-selected-3.png`](booking-app/treatment-time-selected-3.png) |
| Same selector in a reschedule journey | [`booking-app/treatment-selected-5.png`](booking-app/treatment-selected-5.png) (filename says “treatment-selected”; the artboard is a Book a Time calendar with “Confirm Reschedule”) |
| Focus / loading / empty (no slots) / error / success | missing |

---

## Payment summary

**Tokens:** `color.surface`, `color.text`, `color.accent` (`TODO`) for the location line, `color.primary` is not the payment CTA (the enabled CTA is a solid black fill with light type), `radius.card` and `radius.button` (`TODO`), `elevation.card`, `spacing`, `type.headline` / `type.body` / `type.label`.

Notes on this component use a light placeholder or light body on a light field; that contrast failure is recorded in the accessibility follow-up, not “fixed” here.

**States** (issue #2 required set)

| State | PNG |
| --- | --- |
| Review | [`booking-app/review-pay.png`](booking-app/review-pay.png) |
| Payment unavailable | missing |
| Paid | missing as a distinct “paid” artboard. [`booking-app/review-pay-done.png`](booking-app/review-pay-done.png) is the closest related screen: it still uses the Review & Pay chrome and adds “Thank you! Payment will be onsite” with a “$2250 - Confirm” action, which is an onsite-payment confirmation rather than a completed card payment. |
| Failed | missing |
| Focus / loading / empty / error | missing |

---

## Status chip

**Tokens:** `type.label`, `spacing`, a compact radius (`TODO`; not necessarily `radius.card`). Colour roles depend on the status:

- Booking upcoming / completed tabs on the dashboard use `color.text` for the active tab and a muted treatment for the inactive tab. These are tabs, not small chips, but they are the only booking artboards that name upcoming and completed.
- Inventory low-stock uses `color.warning` (`TODO`) on `color.warningSurface`.
- Inventory “in operating range” and usage-up chips use `color.success` on `color.successSurface`.
- The outside-temperature banner uses `color.error` on `color.errorSurface` and is a banner rather than a compact chip; it is listed here because it is a status treatment with a text label.

**States** (issue #2 required set)

| State | PNG |
| --- | --- |
| Upcoming | [`booking-app/current-services-name-4.png`](booking-app/current-services-name-4.png) (Upcoming tab selected) |
| Completed | [`booking-app/current-services-name-6.png`](booking-app/current-services-name-6.png) (Completed tab selected) |
| Cancelled | missing |
| Related: low-stock warning chip | [`inventory-app/overview-low-un-allocated-stock.png`](inventory-app/overview-low-un-allocated-stock.png) |
| Related: expiry warning chip | [`inventory-app/details.png`](inventory-app/details.png), [`inventory-app/inventory.png`](inventory-app/inventory.png) (“Next expiry in 1 week”) |
| Focus / loading / empty / error / success | missing as generic chip states (see success/error-related chips above) |

---

## Report card

**Tokens:** `color.surface`, `color.text`, `color.primary` for selected navigation or brand-tinted decoration, `color.error` / `color.errorSurface` in the warning state, `color.success` / `color.successSurface` for in-range or usage-up treatments, `radius.card` (`TODO`), `elevation.card`, `spacing`, `type.headline` / `type.body` / `type.label`.

**States** (issue #2 required set)

| State | PNG |
| --- | --- |
| Normal | [`inventory-app/reports.png`](inventory-app/reports.png) |
| Warning | [`inventory-app/report-outside-temps.png`](inventory-app/report-outside-temps.png) |
| Focus / loading / empty / error / success | missing as generic card states. The normal artboard already includes a success usage chip; the warning artboard includes both the error banner and that success chip. |

A developer can build the payment summary and the report card from the state names and token roles above without opening the Adobe file for those names. Spacing and radius still follow `tokens.json` (spacing scale published; radii `TODO` pending XD).

No Flutter theme is changed in this issue.
