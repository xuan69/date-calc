# Future Dates Generator 🗓️

Made with AI to help me.

A lightweight, single-file web utility that instantly calculates and displays a sequence of future dates based on a custom interval. Built for quick scheduling and planning, it features a responsive multi-column layout, one-click clipboard copying, and a visual checklist tracker.

It was made to prepare scheduled dates to paste into YouTube when scheduling a video.

## ✨ Features

* **Zero Dependencies:** Pure Vanilla HTML, CSS, and JavaScript all contained within a single html file. No build tools, no frameworks, no external libraries.
* **Smart Persistence:** Uses browser Local Storage to remember your last used variables (Start Date, Interval, and Target Count) across sessions.
* **Click-to-Copy:** Click any generated date to instantly copy it to your clipboard in a clean `MMM D, YYYY` format (e.g., Aug 5, 2026).
* **Checklist Highlighting:** Clicked dates turn green and remain highlighted, allowing you to use the interface as a progress tracker while pasting dates into other applications.
* **Desktop-Optimized Grid:** The results automatically flow into a strict 8-column grid on desktop screens for maximum scannability, scaling gracefully down to 2 columns on mobile.
* **Toast Notifications:** Unobtrusive popup alerts confirm when a date has been successfully copied.

## 🚀 Usage

Since this is a standalone utility, there is no installation or server required, just open it in a web browser.

1. Clone or download this repository.
2. Double-click the `date-cal.html` file to open it in your default web browser.
3. Configure your parameters:
   * **Starting Date:** The date you want to begin calculating from (defaults to today).
   * **Days to Skip:** The interval between dates (defaults to 3). *Example: 0 = consecutive days, 1 = every other day.*
   * **Number of Results:** How many dates to generate (defaults to 56).
4. Click **Generate Dates**.
5. Click any date block in the results grid to copy it to your clipboard.

## 🛠️ How it Works

The application calculates the date intervals using standard JavaScript `Date` objects. By adding the interval to the base date iteratively, it safely handles month-end and leap-year rollovers automatically. 

The styling relies on CSS Grid (`grid-template-columns: repeat(8, 1fr)`) to maintain the strict horizontal flow, and the JavaScript makes use of the modern `navigator.clipboard` API for seamless text copying.

## 📝 Customizing Defaults

If you want to change the fallback defaults (for first-time loads or cleared cache), look for these variables near the top of the `<script>` tag:

```javascript
const savedSkipDays = localStorage.getItem('generator_skipDays') || 3;
const savedResultsCount = localStorage.getItem('generator_resultsCount') || 56;
