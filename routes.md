# Linica route specs

Each booking and inventory route below is listed once, with the PNG it must match or `missing`. States of the same route point at additional artboards but do not add a second route row.

A **design-oriented PR is not done** until a screenshot of the implementation is compared with the named PNG for that route (or with each named state PNG, when several exist). Do not add that check to `fe-fltr-linica` or `fe-fltr-inventory` from this issue.

PNG names are paths in this repository. The typo in `booking-app/nurse-page-seletced.png` is the existing filename. Prototype labels in `prototype/index.html` are not used when the pixels show a different screen.

Implementation notes in italics are the current Flutter route names, observed read-only in `fe-fltr-linica` (`lib/routing.dart`) and `fe-fltr-inventory` (`lib/main.dart`). They are not design requirements.

## Booking

| Route | PNG | Notes |
| --- | --- | --- |
| Sign in | [`booking-app/signin.png`](booking-app/signin.png) | *App: `/signin`.* |
| Sign up | [`booking-app/signup.png`](booking-app/signup.png) | *App: `/signup`.* |
| Dashboard | [`booking-app/current-services-name-4.png`](booking-app/current-services-name-4.png) | Upcoming tab. Completed tab of the same route: [`booking-app/current-services-name-6.png`](booking-app/current-services-name-6.png). *App: `/dashboard`.* |
| Clinic select | [`booking-app/treatment-location.png`](booking-app/treatment-location.png) | Selected state: [`booking-app/treatment-location-selected.png`](booking-app/treatment-location-selected.png). *App: `/clinic/select`.* |
| Clinic details | missing | *The app has `/clinic/details`. No artboard in `booking-app/` shows a dedicated clinic details screen.* |
| Nurse select | [`booking-app/select-nurse.png`](booking-app/select-nurse.png) | Selected state: [`booking-app/nurse-selected.png`](booking-app/nurse-selected.png). *App: `/nurse/select`.* |
| Nurse details | [`booking-app/nurse-page.png`](booking-app/nurse-page.png) | Selected treatment and location: [`booking-app/nurse-page-seletced.png`](booking-app/nurse-page-seletced.png). *App: `/nurse/details`.* |
| Treatment select | [`booking-app/treatments.png`](booking-app/treatments.png) | Selected items in the cart: [`booking-app/treatment-selected.png`](booking-app/treatment-selected.png). *App: `/treatment/select`.* |
| Treatment details | missing | *The app has `/treatment/details`. `treatment-selected.png` is the treatment list with a cart footer, not a single-treatment details screen. `treatment-selected-5.png` is a Book a Time / reschedule calendar and is listed under Booking slot.* |
| Booking slot | [`booking-app/treatment-time-selected-1.png`](booking-app/treatment-time-selected-1.png) | Further states: [`treatment-time-selected-2.png`](booking-app/treatment-time-selected-2.png) (second date outlined, slots still off), [`treatment-time-selected-3.png`](booking-app/treatment-time-selected-3.png) (slot selected). Reschedule journey: [`booking-app/treatment-selected-5.png`](booking-app/treatment-selected-5.png). *App: `/booking`.* |
| Review and pay | [`booking-app/review-pay.png`](booking-app/review-pay.png) | *App: `/payment`.* |
| Confirmation | [`booking-app/review-pay-done.png`](booking-app/review-pay-done.png) | Still uses Review & Pay chrome, plus “Thank you! Payment will be onsite”. *App: `/confirmation`.* |
| Appointments | [`booking-app/booking-pre-appointment.png`](booking-app/booking-pre-appointment.png) | Pre-visit appointment details. *App: `/appointments`.* |
| Profile | missing | *The app has `/profile`. No profile artboard is in `booking-app/`.* |

## Inventory

| Route | PNG | Notes |
| --- | --- | --- |
| Sign in | [`inventory-app/signin.png`](inventory-app/signin.png) | Same layout family as the booking sign-in artboard, but the files are not identical. *App: `SignInScreen` (no named path).* |
| Sign up | [`inventory-app/signup.png`](inventory-app/signup.png) | *App: `SignUpScreen`, pushed from sign-in.* |
| Overview | [`inventory-app/overview.png`](inventory-app/overview.png) | Warning state: [`inventory-app/overview-low-un-allocated-stock.png`](inventory-app/overview-low-un-allocated-stock.png). *App: `OverviewScreen`, first tab, labelled “Inventory” in the current three-tab shell.* |
| Stock detail | [`inventory-app/details.png`](inventory-app/details.png) | *App: pushed from overview or list; no named path.* |
| Reports | [`inventory-app/reports.png`](inventory-app/reports.png) | Warning state: [`inventory-app/report-outside-temps.png`](inventory-app/report-outside-temps.png). *App: `ReportsScreen`.* |
| Profile | missing | *The app has `ProfileScreen` as the third tab. No profile artboard is in `inventory-app/`.* |

## Additional artboards (not in the required route list)

These files exist in the repository and must not be used to invent a new required route.

| Artboard | What the pixels show |
| --- | --- |
| [`inventory-app/inventory.png`](inventory-app/inventory.png) | Inventory list (Group Based / Individual, with a “Recommended Reorder” block). The mockup bottom navigation has four destinations — Overview, Inventory, Reporting, Profile — so this is a separate list screen from Overview. The current Flutter shell does not expose this as its own tab. |
| [`inventory-app/home.png`](inventory-app/home.png) | An icon-cloud placeholder with a three-item bar (Overview, Wallet, Profile). It is not an operations overview. Where this should sit in the product is an existing open question, not something to invent here. |

Building the missing clinic details, treatment details, and profile screens, and deciding the inventory home / list information architecture, belongs to the app issues already filed. This document only records the gaps.
