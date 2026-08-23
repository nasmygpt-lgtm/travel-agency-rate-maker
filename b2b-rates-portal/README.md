# Grand Central Hotel — B2B Agency Rates Portal

A single-page **B2B Hotel Agency Rates Portal** built with **React**, **Tailwind CSS**, and **Lucide React** icons. It features a mock authentication system with role-based dashboards for hotel sales admins and travel agency partners.

Dark, premium theme: `slate-950` background, `slate-900` cards, and `amber-500`/gold accents.

## Running it

This is a **zero-build, self-contained** app. React, Tailwind, Babel (for JSX), and Lucide are loaded from CDNs, so there's nothing to install.

```bash
# Just open the file in a browser:
open index.html            # macOS
# or double-click index.html

# ...or serve it locally (recommended):
python3 -m http.server 8080
# then visit http://localhost:8080
```

> An internet connection is required on first load so the browser can fetch React/Tailwind/Lucide from their CDNs.

## Demo credentials

| Role   | Username | Password   | Sees                                  |
|--------|----------|------------|---------------------------------------|
| Admin  | `admin`  | `admin123` | Admin console (manage agencies)       |
| Agency | `akbar`  | `123`      | Akbar Travels rate sheet              |
| Agency | `rayna`  | `123`      | Rayna Tours rate sheet                |

## Features

### Login screen
- Centered card with username + password (show/hide toggle).
- Inline error handling for invalid credentials.
- Demo credentials help box.

### Admin dashboard (`role === "admin"`)
- Sticky header with **Logout**.
- Summary stats (active contracts, room categories, seasons).
- **Add New Travel Agency** form — Agency Name, Username, Password, Standard Room Base Rate. Seasonal rates are auto-generated from the base rate (High Season +50%, Exhibitions +130%) plus a Deluxe tier (+35%).
- Grid of active agency contracts showing each partner's login details and lead rate.

### Agency dashboard (`role === "agency"`)
- Welcome banner with agency name, contract reference, and a **Print / Download PDF** button (`window.print`, with dedicated print styles).
- Grid of **rate cards**, each showing:
  - Room type, meal plan (e.g. Bed & Breakfast) and occupancy.
  - Three pricing columns: **Low Season (May–Sep)**, **High Season (Oct–Apr)**, **Exhibitions (Major Events)**.
  - Terms: inclusive of 5% VAT & 7% Municipality Fee; 15 AED Tourism Dirham per room/night.
- Contract terms & conditions footer.

## Tech stack
- React 18 (UMD) + Babel Standalone (in-browser JSX)
- Tailwind CSS (CDN, `darkMode: 'class'`)
- Lucide icons — `Building2`, `Lock`, `User`, `ShieldCheck`, `Download`, and more

## Notes
- State is in-memory only (a mock database). Agencies added by the admin persist for the session but reset on reload.
- Fully responsive for desktop and mobile.
