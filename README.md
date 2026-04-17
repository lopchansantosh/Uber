# SBA Uber Driver P&L Report — iPhone PWA

A mobile-first Progressive Web App (PWA) version of the SBA Uber Driver Income & Expense Report Generator.

## What's the same as the desktop version

- Both IRD Mileage Rate and Actual Costs methods
- All income fields: Uber Income, Taxi Income, GST Flat-rate Credit, custom lines
- All expense fields: mileage mode (Phone, Uber Fees, custom) and actual mode (ACC, Fuel, Insurance, etc.)
- Editable IRD mileage rate table (Petrol/Diesel, Hybrid, Electric)
- Vehicle details, km log, calculated vehicle expense
- Depreciation schedule (Actual Costs mode)
- Prior year column toggle
- DRAFT watermark
- Comments/Notes section
- Editable disclaimer text
- Excel export (SheetJS)
- Print to PDF
- Both SBA branches (New Brighton / Rolleston)
- Same live-preview formatted report with SBA logo

## What's different (iPhone-optimised)

- Tab-based navigation instead of two-panel layout
- 5 tabs: **Client → Income → Expenses → Vehicle/Dep → Report**
- All inputs are 16px font (prevents iOS auto-zoom)
- Safe area padding for iPhone notch/home indicator
- Bottom tab bar with safe area support
- Works offline after first load (service worker)
- Installable as a home screen app

---

## How to deploy to iPhone (4 steps)

### Step 1 — Create a GitHub repository

1. Go to [github.com](https://github.com) and sign in
2. Click **New repository**
3. Name it `uber-pl-report` (or any name)
4. Set to **Public**
5. Click **Create repository**

### Step 2 — Upload all files

Drag and drop ALL 7 files into the repository:

```
index.html
manifest.json
sw.js
icon.svg
icon-192.png
icon-512.png
README.md
```

### Step 3 — Enable GitHub Pages

1. In your repo: **Settings → Pages** (left sidebar)
2. Source: **Deploy from a branch**
3. Branch: **main**, Folder: **/ (root)**
4. Click **Save**
5. Wait ~2 minutes. Your URL will be:
   ```
   https://YOUR-USERNAME.github.io/uber-pl-report/
   ```

### Step 4 — Add to iPhone Home Screen

1. Open **Safari** on iPhone (must be Safari, not Chrome)
2. Go to your GitHub Pages URL
3. Tap the **Share** button (box with upward arrow)
4. Scroll down and tap **"Add to Home Screen"**
5. Name it **"Uber P&L"** → tap **Add**

The app icon appears on your home screen and opens full-screen like a native app.

---

## Updating the app

Edit files in GitHub → changes appear next time the app loads with internet.

To force the service worker to pick up changes, update the cache version in `sw.js`:
```js
const CACHE_NAME = 'sba-uber-pl-v2'; // increment version number
```

---

## Files

| File | Purpose |
|---|---|
| `index.html` | Complete app — all CSS, HTML and JS in one file |
| `manifest.json` | PWA manifest — makes it installable |
| `sw.js` | Service worker — enables offline use |
| `icon.svg` | Vector app icon |
| `icon-192.png` | App icon 192×192 (used by iOS) |
| `icon-512.png` | App icon 512×512 |

---

*SBA Small Business Accounting — New Brighton & Rolleston*
