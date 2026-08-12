# Linica Design System

This module is the shared product and UX source for the Linica platform. It provides the visual and interaction reference for both the consumer booking app and the inventory management app.

## Design links

- [Linica Booking App](https://xd.adobe.com/view/4e6c66a5-7d83-449f-84a2-e2997acd2607-1b3f/)
- [Linica Inventory App](https://xd.adobe.com/view/f8860247-986a-4ade-b765-bd8913df201d-add5/)

## Design system goals

The design folder should evolve from a simple asset collection into a reusable design system with:

- consistent tokens for color, spacing, typography, and elevation
- reusable UI components and patterns
- flows and states across key user journeys
- handoff guidance for front-end implementation

## Foundation tokens

The current mockups suggest a healthcare / premium aesthetics brand. Recommended starting tokens:

### Color

- Primary brand: soft rose / coral / warm neutral palette for trust and warmth
- Accent: teal, sky, or graphite for CTAs and state information
- Surface: off-white and cool grey backgrounds
- Text: charcoal dark grey for readability and contrast
- Error: red for alerts and invalid states
- Success: green for confirmed or completed states

### Typography

- Headlines: modern sans-serif, high contrast, strong hierarchy
- Body: legible sans-serif optimized for mobile screens
- Labels: compact and consistent for metadata, forms, and tags

### Spacing and radius

- Use an 8px spacing base with 4px increments for tight adjustments
- Cards and forms should lean toward generous spacing and clear hierarchy
- Corner radius should stay soft and consistent for mobile cards and buttons

## Core components

The product screens imply a reusable set of components:

- Top app bar with title and contextual actions
- Search/filter bars
- Info cards and service tiles
- Clinic and nurse profile cards
- Booking calendar / slot selectors
- Summary cards for confirmation and payment
- Sign-in and sign-up form states
- Status chips for upcoming, completed, and cancelled appointments
- Report cards and overview metrics for inventory flows

## User-flow specs

### Consumer booking flow

1. Sign in or create account
2. Browse clinics and practitioners
3. View treatment details and pricing
4. Select a preferred clinic / nurse / treatment
5. Choose date and time slot
6. Review booking summary
7. Confirm booking and payment
8. View appointment status and details

### Inventory flow

1. Sign in to operational dashboard
2. Review stock overview and alert levels
3. Inspect inventory detail and allocation status
4. Review reports and outside-temperature checks
5. Manage operational insights and actions

## Design-to-development handoff

To keep the implementation aligned with design intent:

- Each screen should map to a route or page component in the frontend app.
- Each component should have a clear state model: default, hover/focus, loading, error, empty, success.
- Backend payloads should align with the data the UI needs, not the other way around.
- Use screenshot review as part of PR acceptance for UX parity.

## Quality bar

Before closing a design-oriented task, check that the work addresses:

- visual consistency with the Linica brand direction
- accessible contrast and readable typography
- mobile-first layout quality
- clear user flow continuity across screens
- support for loading, empty, and error states

## Evolution plan

The current assets are a good starting point, but the design system still needs a formal library to scale with the product. Future improvements should include:

- a shared token document in code or JSON
- a components inventory with examples and states
- route-level design specs for each screen
- accessibility requirements and QA notes

