<p align="center"><img src="assets/banner.svg" alt="Vendor Performance Reporting" width="100%"></p>

<p align="center">
<img src="https://img.shields.io/badge/stack-Apps_Script_·_Sheets-0F2A44?style=flat-square">
<img src="https://img.shields.io/badge/data-fictional-C0C8D2?style=flat-square">
<a href="https://sider.ai/agents/web-creator/share/695ea81100a621619985fdfb"><img src="https://img.shields.io/badge/Portfolio-Nae_Kitakado-0F2A44?style=flat-square"></a>
</p>

<p align="center"><a href="https://naekitakadoportfolio.github.io/vendor-performance-reporting/"><img src="https://img.shields.io/badge/%E2%96%B6%20Try%20the%20live%20demo-0F2A44?style=for-the-badge" alt="Live demo"></a></p>

# Vendor Performance Reporting

Turns weekly marketplace vendor CSV exports into a clean performance reporting app: validated uploads with duplicate protection, KPI overview, multi-product trend charts, product drill-downs, stock-risk alerts, batch undo, a report builder with CSV export, and configurable thresholds.

> **Portfolio rebuild.** A from-scratch recreation of a custom Apps Script upload pipeline for weekly marketplace vendor reports, a production system I designed. It uses **fictional data**, with no client names, code or branding.

## ✨ Features
- **Overview:** revenue, units, conversion, average in-stock and open alerts, with week-over-week change, a trend chart and top products
- **Upload:** paste or choose a CSV → header check, week-format check, numeric/range validation and duplicate detection against history → append valid rows as a batch
- **Weekly trends:** SVG line chart for any metric, comparing up to 6 products
- **Product drill-down:** `#/product?sku=…` with lifetime KPIs, a chart and a weekly table
- **Stock & risk alerts:** critical/warning in-stock levels and week-over-week revenue drops
- **Upload history:** every batch with an undo for the most recent
- **Report builder:** choose metrics and weeks → summary table → CSV download
- **Settings:** alert thresholds with validation, plus an activity log
- **Light/dark theme**, responsive layout, state saved in your browser, and a one-click demo reset

## 🧭 Try it
1. Go to *Upload* → **Validate** the sample → see 3 valid, 1 rejected and 1 duplicate → append
2. Open *Stock & risk alerts*, then drill into the flagged product
3. In *Settings* raise the warning threshold and watch the alerts change
4. Use *Upload history* to undo the batch

Open the **[live demo](https://naekitakadoportfolio.github.io/vendor-performance-reporting/)**.

## 🏗 Production architecture
| Layer | Production | This demo |
|---|---|---|
| UI | Apps Script upload dialog + Sheets reports | Static SPA (`index.html`) |
| Ingestion | CSV → parse → validate → append to history sheet | Same pipeline in JS |
| Storage | History sheet + pivot tabs | `localStorage` |
| Charts | Sheets charts / dashboard | Inline SVG |

## 📁 Project structure
```
vendor-performance-reporting/
├── index.html        # built app (shell + app code)
├── src/app.js        # views, state and business logic
├── src/app.json      # navigation, theme and build config
├── assets/banner.svg
├── README.md
└── LICENSE
```

## 🚀 Run locally
No build step needed. Open `index.html` in a browser, or serve it:
```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

## 🧩 Key implementation notes
- `validate()` rejects files with missing columns and rows with bad formats, then de-duplicates on week + SKU
- Each upload is tagged with a batch ID so it can be undone safely
- `risks()` combines stock thresholds and WoW revenue drops into one alert list
- The seed data is generated deterministically (8 products × 8 weeks)

## 🗺 Roadmap
- Scheduled email digest
- Forecast of stock-out date
- Category-level rollups

---
<p align="center"><sub>Built by <b>Nae Kitakado</b>, AI Automation Consultant · <a href="https://www.linkedin.com/in/nae-k-203194265">LinkedIn</a> · <a href="https://sider.ai/agents/web-creator/share/695ea81100a621619985fdfb">Portfolio</a> · open to retainer &amp; part-time consulting</sub></p>
