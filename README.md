EEA Member Cloud – README

An interactive, responsive bubble cloud visualization of EEA members. Built with D3.js, this module displays member companies as colorful, tier-coded bubbles with logos and tooltips.

Features

Responsive Layout: Scales to desktop, tablet, and mobile automatically.

Dynamic Visualization:
• Hover → tooltip with member name, tier, and logo.
• Click → detailed info panel with optional links to company site, X (Twitter), and LinkedIn.
• Bubbles colored by membership tier (A, B1, B2+B3, D).

Logo + Fallbacks: Smart lookup tries multiple paths and Clearbit API if a logo file is not available.

Accessibility: Keyboard navigation (Enter/Space to open details). ARIA roles and labels included.

Admin Mode: Toggle via ?admin=1 query param or button. Shows extra fields (record ID, country, membership class).

Project Structure

/logos/ – Place member logos here (supports subfolders by tier).

Sep29_MostRecent_Version.html – Main standalone HTML + JS + CSS.

CSV/JSON Input – Upload via UI or pass with ?data=path/to/members.csv.

Usage
Local Setup:

Clone or copy project files.

Place logos in /logos/ folder (organized by membership class if desired).

Open Sep29_MostRecent_Version.html in a local web server (not file://).

Example with Python:
python3 -m http.server 8080
Visit: http://localhost:8080/Sep29_MostRecent_Version.html

Loading Data:

Manual upload: Click “Load CSV / JSON” and select your file.

Auto load: Append ?data=path/to/members.csv to the URL.

CSV requires a header row with at least a Company column. Other fields (logo, website, industry, etc.) are optional.

Embedding on a Website:

Iframe:

<iframe src="https://yourdomain.com/eea-member-cloud.html" width="100%" height="600" style="border:0;"></iframe>

JS Snippet: Inline the <div id="member-cloud-root"> and <script src="..."></script> sections into your site.

Maintenance

Ensure /logos/ stays updated with new member logos.

Keep CSV/JSON schema consistent (company, website, logo, membership class, etc.).

Test on multiple devices for responsiveness.

Update D3.js via CDN if needed (https://cdn.jsdelivr.net/npm/d3@7
).

Future Enhancements

Animate bubble transitions when data changes.

Add filtering/search controls.

Support theming (dark mode, brand colors).
