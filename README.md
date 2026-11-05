<p align="center"><img src="assets/banner.svg" alt="Vendor Performance Reporting" width="100%"></p>

<p align="center">
<img src="https://img.shields.io/badge/stack-Apps_Script_·_Sheets-0F2A44?style=flat-square">
<img src="https://img.shields.io/badge/data-fictional-C0C8D2?style=flat-square">
<a href="https://sider.ai/agents/web-creator/share/695ea81100a621619985fdfb"><img src="https://img.shields.io/badge/Portfolio-Nae_Kitakado-0F2A44?style=flat-square"></a>
</p>

<p align="center"><a href="https://naekitakadoportfolio.github.io/vendor-performance-reporting/"><img src="https://img.shields.io/badge/%E2%96%B6%20Try%20the%20live%20demo-0F2A44?style=for-the-badge" alt="Live demo"></a></p>

# Vendor Performance Reporting

Turns raw weekly marketplace vendor exports into a clean performance report. Edit the CSV or upload your own file to see validation, week-over-week changes and stock-risk flags.

> **Portfolio rebuild.** This is a from-scratch recreation of a production system I designed and run, rebuilt with **fictional data** and no client names, code or branding. The live demo runs entirely in the browser.

## The problem
Weekly marketplace vendor reports arrived as raw CSV exports. Analysts copy-pasted them into spreadsheets by hand, which caused duplicate weeks, broken columns and slow reporting.

## Impact in production
A custom upload pipeline validates and appends each week's data automatically, so reporting shows week-over-week performance, conversion and stock risk without manual cleanup.

## What it demonstrates
| Capability | How |
|---|---|
| File ingestion | CSV upload with header validation |
| Data quality | Duplicate-week and bad-row rejection |
| KPI computation | Revenue, units, conversion and week-over-week change |
| Risk flags | Low in-stock alerts |
| Visualization | Trend chart from appended history |

## Production architecture
Apps Script upload dialog → parse + validate → append to history sheet → pivot/report tabs → dashboard

## Try it
Open the **[live demo](https://naekitakadoportfolio.github.io/vendor-performance-reporting/)** or run `index.html` locally. No install needed.

---
<p align="center"><sub>Built by <b>Nae Kitakado</b>, AI Automation Consultant · <a href="https://www.linkedin.com/in/nae-k-203194265">LinkedIn</a> · <a href="https://sider.ai/agents/web-creator/share/695ea81100a621619985fdfb">Portfolio</a> · open to retainer &amp; part-time consulting</sub></p>
