# Realtor360

A pixel-matched frontend build of the [Realtor360 Figma prototype](https://www.figma.com/proto/w3ZJn4OeQVLudyC0jOzOYW/Realtor360?node-id=2-6286&t=riEfivcfVBTSxep3-1&scaling=min-zoom&content-scaling=fixed&page-id=0%3A1&starting-point-node-id=2%3A6286), written in React and TypeScript.

## Stack

- React 19, TypeScript, and Vite
- Plain CSS with design tokens in `src/index.css`. There's no UI library.
- Charts are hand-drawn SVG in `src/components/Charts.tsx`. Their coordinates were measured from the 1440px frames, so they map 1:1 onto the cards.
- A hash router (`src/router.ts`), so the build runs as static files, including on GitHub Pages.

## Run it

```bash
npm install
npm run dev      # http://localhost:5173
npm run build    # type-check and build into dist/
```

The design targets 1440px wide, the Figma frame size.

## Screens

| Route | Screen |
| --- | --- |
| `#/` | Home dashboard: KPIs, charts, reminders, calendar, schedule, listings, lead contacts |
| `#/dashboard` | Dashboard panel (the `···` in the navbar) |
| `#/developments`, `#/developments/1` | Development list and detail (the Notes tab shows the notes form) |
| `#/reports/stacking-plan` | Stacking plan (Development detail → Stacking Plan) |
| `#/buildings`, `#/buildings/1` | Building list and detail (click the building name to switch buildings) |
| `#/units`, `#/units/1` | Unit list and detail |
| `#/leads`, `#/leads/1` | Lead card list and detail |
| `#/companies`, `#/companies/1` | Company list and detail |
| `#/contacts`, `#/contacts/1` | Contact list and detail |
| `#/deals`, `#/deals/1` | Deal list and detail |
| `#/deals/offer-form`, `#/deals/deal-sheet` | Offer Form and Deal Sheet (Deal detail → Generate Offer Form) |
| `#/activities` | Activities with the Customers, Open Deals, Leads/Contacts, and Others tabs |
| `#/attorney-firms`, `#/attorney-firms/1` | Attorney firm list and detail |
| `#/reports`, `#/reports/leads-by-source`, `#/reports/create-chart` | Report list, report grid, and chart builder (pick a chart type to see a preview) |
| `#/settings` | Settings (avatar menu → Settings) |

Clicking a list row opens its detail page. The filters, tabs, pagination, calendar month navigation, starred reports, and dropdowns are all interactive. The data is static mock data.

## Structure

```
src/
  components/  Navbar, Icon, Charts, shared UI (filters, tables, detail shell, KV grid)
  pages/       Home, Lists (all list screens), Details (all detail screens), Other
public/img/    Photos and icons cropped at 1x from the Figma exports
```
