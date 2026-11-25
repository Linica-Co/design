# Linica accessibility checklist

A short checklist a design-oriented PR can be reviewed against. This is not a full audit of every PNG, and it does not fix implementation bugs or restyle either app.

Type sizes and some colour roles are still `TODO` in [`tokens.json`](tokens.json). Use the published tokens where they exist, and do not invent substitutes to close a check.

## Contrast

- Text on a surface must meet [WCAG 2.2 Success Criterion 1.4.3 Contrast (Minimum)](https://www.w3.org/TR/WCAG22/#contrast-minimum) (AA): 4.5:1 for normal text and 3:1 for large text.
- Measured pairs that already meet AA at the sampled values include `color.text` `#000000` on `color.surface` `#FFFFFF` (21:1) and `color.primary` `#156571` on `color.surface` `#FFFFFF` (about 6.7:1).
- **Known notes contrast failure.** [`booking-app/booking-pre-appointment.png`](booking-app/booking-pre-appointment.png) renders the notes body in light grey on a light field (samples around `#C0C0C0`–`#BBBBBB` on white or `#F4F4F4`, about 1.8:1). That is well below 4.5:1. The same light-on-light treatment appears as the “Add a note…” placeholder on [`booking-app/review-pay.png`](booking-app/review-pay.png). This is visible in the design exports, not only in the booking app implementation. Do not treat a PR as done if implemented notes still use a light colour on a light surface.
- Placeholders, muted labels, and disabled footer actions (for example the grey “$2250 - Review” button on [`booking-app/treatment-time-selected-1.png`](booking-app/treatment-time-selected-1.png)) must be checked against AA when they convey information the user needs to read. Exact muted and disabled colours are not yet tokens; do not guess them in `tokens.json` to pass this check.
- Accent, warning ink, and any other `TODO` colour must be contrast-checked against their surface after the exact hex is confirmed in XD.

## Type size

- Body copy must be no smaller than the `type.body` size in `tokens.json`.
- That size is currently `TODO`. Until it is confirmed in the Adobe XD specs, a PR cannot claim type-size parity with the mockups; it can still avoid shrinking body text below a readable mobile minimum, but that minimum is not a published Linica token.

## Focus

- Buttons, text fields, list rows, calendar days, slot chips, and tab controls need a visible focus state.
- No PNG in this repository shows a focus ring or an equivalent keyboard-focus treatment (generic focus is recorded as `missing` in [`components.md`](components.md)). The absence of a mockup does not waive the requirement. Use a focus indicator that meets [WCAG 2.2 Success Criterion 2.4.7 Focus Visible](https://www.w3.org/TR/WCAG22/#focus-visible) and [2.4.13 Focus Appearance](https://www.w3.org/TR/WCAG22/#focus-appearance) once a design value exists; until then, do not ship controls that have no visible focus at all.

## Status is not colour alone

[WCAG 2.2 Success Criterion 1.4.1 Use of Color](https://www.w3.org/TR/WCAG22/#use-of-color): status must also have a text label (an icon alone is not enough if the icon has no accessible name).

| Status | Text in the mockups | PNG |
| --- | --- | --- |
| Upcoming | “Upcoming” tab label | [`booking-app/current-services-name-4.png`](booking-app/current-services-name-4.png) |
| Completed | “Completed” tab label | [`booking-app/current-services-name-6.png`](booking-app/current-services-name-6.png) |
| Cancelled | No artboard. Any cancelled treatment must still have a text label, not only a colour. | missing |
| Low stock | “LOW UN-ALLOCATED STOCK” on the warning chip; “Running Low on Stock” on the reorder card | [`inventory-app/overview-low-un-allocated-stock.png`](inventory-app/overview-low-un-allocated-stock.png), [`inventory-app/inventory.png`](inventory-app/inventory.png) |
| Outside-range / temperature warning | “WARNING: Product could be severely damaged” and “Outside recommended operating temps” | [`inventory-app/report-outside-temps.png`](inventory-app/report-outside-temps.png) |

Related labelled treatments, not in the required status list: “Next expiry in 1 week”, “In Operating Range”, and “5% increase in usage this week” already include text on [`inventory-app/details.png`](inventory-app/details.png) and [`inventory-app/reports.png`](inventory-app/reports.png). Keep that pattern.

This checklist is the deliverable. A full contrast and type audit of every PNG, and a fix for the notes contrast bug, are out of scope for this issue.
