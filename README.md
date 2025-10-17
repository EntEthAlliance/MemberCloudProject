# EEA Member Cloud

Interactive bubble visualization displaying Enterprise Ethereum Alliance members. Shows company logos, membership tiers, and contact information in a responsive D3.js interface.

## Quick Start

**Deploy in 3 steps:**
1. Clone repository and add member logos to `/logos/` folder
2. Start local server: `python3 -m http.server 8080`
3. Open `http://localhost:8080/Sep29_MostRecent_Version.html`

**Timeline:** 5 minutes setup, ready for production use.

## Core Features

### Visual Display
- **Responsive design** across desktop, tablet, mobile
- **Tier-coded bubbles** with company logos and tooltips
- **Interactive details panel** showing company info and social links
- **Smart logo fallback** using multiple paths + Clearbit API

### Data Management
- **CSV/JSON upload** via UI or URL parameter (`?data=path/to/file.csv`)
- **Admin mode** with extended member details (`?admin=1`)
- **Keyboard accessible** with ARIA support

### Membership Tiers
- **Tier A:** Premium members (distinct color coding)
- **Tier B1:** Standard members
- **Tier B2+B3:** Associate members
- **Tier D:** Developer members

## File Structure

```
├── logos/                    # Member company logos
├── Sep29_MostRecent_Version.html # Main application file
└── README.md                # This file
```

## Data Requirements

**CSV format with required header:**
- `Company` (required)
- `logo`, `website`, `industry`, `membership_class` (optional)

**Example:**
```csv
Company,website,logo,membership_class
Microsoft,https://microsoft.com,microsoft.png,A
ConsenSys,https://consensys.net,consensys.png,B1
```

## Deployment Options

### Website Integration
```html
<iframe src="https://yourdomain.com/eea-member-cloud.html" 
        width="100%" height="600" style="border:0;">
</iframe>
```

### Auto-load Data
```
https://yourdomain.com/eea-member-cloud.html?data=members.csv
```

## Maintenance Tasks

**Monthly (15 minutes):**
- Update `/logos/` with new member logos
- Refresh member data CSV

**Quarterly (30 minutes):**
- Test responsive display across devices
- Verify all member links and logos load correctly

**Annually (1 hour):**
- Update D3.js library version
- Review and optimize logo loading performance

## Next Phase Enhancements

**Immediate (Q2 2025):**
- Member filtering by industry/tier
- Search functionality
- Animation transitions

**Future (Q3-Q4 2025):**
- Dark mode theming
- Member onboarding integration
- Analytics dashboard

## Technical Dependencies

- **D3.js v7** (CDN: `https://cdn.jsdelivr.net/npm/d3@7`)
- **Modern browser** with ES6 support
- **Web server** (not file:// protocol)

**Impact:** Showcases 200+ EEA members, drives enterprise engagement, supports business development outreach.
