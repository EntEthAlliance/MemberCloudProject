# EEA Member Cloud

Interactive bubble visualization displaying Enterprise Ethereum Alliance members. Shows company logos, membership tiers, and contact information in a responsive D3.js interface.

## Quick Start

**Deploy in 3 steps:**
1. Clone repository and add member logos to `/logos/` folder
2. Start local server: `python3 -m http.server 8080`
3. Open `http://localhost:8080/L3Updated_FinalVersion.html`

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
├── L2Updated_FinalVersion.html # Main application file
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


# Member Cloud Visualization – WordPress Integration Guide

This guide explains how to deploy and embed the **Member Cloud visualization** (powered by D3.js) on a WordPress site.  
It uses a **self-contained HTML file (`L3Updated_FinalVersion.html`)** and a set of **SVG logo assets**.

---

## Folder Overview

Your project folder should look like this before upload:

Member_Cloud_Project/
├── L3Updated_FinalVersion.html
├── icons/
│ ├── linkedin.png
│ ├── x.png
├── edited_logos/
│ ├── Accenture.svg
│ ├── Chainlink Labs.svg
│ ├── EY.svg
│ └── ... (other logo files)

## 🚀 Step 1: Create a Folder in WordPress Uploads Directory

1. Connect to your WordPress site via **FTP**, **SFTP**, or your hosting file manager.
2. Navigate to:
/wp-content/uploads/

3. Create a new folder called:
member-cloud

Copy code
4. Upload the following files and folders into it:
/wp-content/uploads/member-cloud/
├── L3Updated_FinalVersion.html
├── icons/
│ ├── linkedin.png
│ ├── x.png
├── edited_logos/
│ ├── Accenture.svg
│ ├── Chainlink Labs.svg
│ ├── ...etc.

After upload, your files will be accessible at:

- HTML file:  
`https://example.com/wp-content/uploads/member-cloud/L2Updated_FinalVersion.html`

- Logo folder:  
`https://example.com/wp-content/uploads/member-cloud/edited_logos/`

---

## Step 2: Verify That File Paths Work

Open one of the logo URLs directly in your browser to confirm it’s public, for example:

https://example.com/wp-content/uploads/member-cloud/edited_logos/Accenture.svg

If the image loads, everything is correctly hosted.

---

##  Step 3: Embed the Cloud Visualization in a WordPress Page

There are **two main options** for integration.  
The recommended and easiest one is the **iframe embed**.

### **Option A: Use an iframe **

1. In your WordPress dashboard, create or edit the page where you want the visualization to appear.
2. Add a **Custom HTML block** (or switch to Code Editor mode).
3. Paste the following snippet:

   ```html
   <iframe
     src="https://example.com/wp-content/uploads/member-cloud/L2Updated_FinalVersion.html"
     style="width:100%; height:90vh; border:none;"
     title="Member Cloud Visualization">
   </iframe>
Save and preview the page — you should see the interactive member cloud load immediately.

Advantages of this method:

No JavaScript conflicts with WordPress themes or plugins.

All assets (HTML, logos, D3.js) remain isolated.

No need for custom plugins or shortcode registration.

---


## Technical Dependencies

- **D3.js v7** (CDN: `https://cdn.jsdelivr.net/npm/d3@7`)
- **Modern browser** with ES6 support
- **Web server** (not file:// protocol)

**Impact:** Showcases 200+ EEA members, drives enterprise engagement, supports business development outreach.




























