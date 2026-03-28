# 🗾 Japan Trip 2026

**7 May – 20 May 2026 · Sydney → Tokyo → Mt Fuji → Kyoto → Osaka → KIX**

A companion web app for planning and tracking a 14-day Japan trip for 3 travellers from Sydney.

Live at: **https://azchu.github.io/japan-trip-2026/**

---

## ✈️ Trip Overview

| Segment | Dates | Accommodation |
|---------|-------|---------------|
| Tokyo | Days 1–6 (7–12 May) | TBD |
| Mt Fuji | Day 7 (13 May) | Ryokan, Lake Kawaguchiko |
| Paragliding → Kyoto | Day 8 (14 May) | TBD |
| Kyoto | Days 9–10 (15–16 May) | TBD |
| Osaka | Days 11–13 (17–19 May) | TBD |
| Departure | Day 14 (20 May) | KIX 9:25pm ✈ |

**Arriving:** NRT Terminal 3 · 10:10am · 7 May · Ref: SG9M3S  
**Departing:** KIX · 9:25pm · 20 May · *(details TBC)*

---

## 🗂️ App Tabs

### Map
Interactive Leaflet map of all 14 days. Filter by day using the pill buttons at the top. Pins are colour-coded by city (red = Tokyo, green = Fuji, purple = Kyoto, orange = Osaka, blue = transit/departure).

### Days
Collapsible day-by-day itinerary cards for all 14 days with times, locations, notes and tips.

### Timetable
Embeds the Google Sheet timetable grid via `/preview` URL. Paste a new Sheet URL or ID into the input field at the top to update — no code changes needed.

### Bookings
Shared booking checklist synced via **JSONBin** (Bin ID: `69c66e8daa77b81da925f112`). Tick items as you book them — updates sync across all devices in real time. Organised into urgency tiers:
- ⏰ Set alarm — can't book yet (Ghibli Museum lottery)
- 🔴 Book right now
- 📅 Book in April
- 📅 Book 1–2 weeks before

### Booked
Confirmed bookings only — flights with reference numbers, hotels once confirmed, and the emergency info card (Japanese phone numbers, Australian embassy contacts, hotel addresses in Japanese for taxis).

### Checklist
Synced to the same JSONBin as Bookings. Four sections:
- **Food bucket list** — 23 Japanese dishes to try, with progress bar
- **Packing checklist** — practical items to bring
- **Eki-stamps** — log train station stamps collected
- **Goshuin** — log shrine/temple stamps collected
- **Shops** — reference list of iconic shops by city/category

---

## 🔧 Tech Stack

| Thing | Detail |
|-------|--------|
| Hosting | GitHub Pages (`azchu/japan-trip-2026`) |
| Map | Leaflet.js + CartoDB Voyager tiles |
| Shared state | JSONBin REST API (bookings + checklist) |
| Timetable | Google Sheets `/preview` embed |
| Fonts | Playfair Display + DM Sans (Google Fonts) |
| No build step | Pure HTML/CSS/JS, single `index.html` |

---

## 📦 Data & Storage

**JSONBin** stores all shared state as a single JSON object:
```json
{
  "ghibli": false,
  "ryokan": false,
  "...": "...all booking keys...",
  "cl": {
    "food": { "sushi": true, "ramen": false },
    "pack": { "coinpouch": true },
    "eki": ["Shinjuku", "Kyoto"],
    "goshuin": ["Fushimi Inari"]
  }
}
```

**localStorage** is used as an offline fallback for the checklist if JSONBin is unreachable.

**Google Sheet** ID is saved to localStorage so it persists across visits without needing to re-paste.

---

## 🔑 Credentials (keep private)

- **JSONBin Bin ID:** `69c66e8daa77b81da925f112`
- **JSONBin API Key:** stored in `index.html` — do not expose publicly
- **Google Sheet ID:** `1SAdQC3DB7z3wvIgURLaYArF3R9BdLY7C`

---

## 📋 Workflow

1. Edit `index.html` locally
2. Test by opening the file in a browser
3. Commit and push to `main` branch on `azchu/japan-trip-2026`
4. GitHub Pages deploys automatically within ~60 seconds
5. For timetable content changes — edit the Google Sheet directly, no code push needed

---

## 🚨 Emergency Contacts

| | |
|-|-|
| Japan Police | 110 |
| Japan Fire/Ambulance | 119 |
| Australian Embassy Tokyo | +81 3-5232-4111 |
| Australian Consulate Osaka | +81 6-6941-9271 |
| Japan Visitor Hotline (English, 24hr) | 050-3816-2787 |
