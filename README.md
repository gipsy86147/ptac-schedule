# PTAC Schedule

A mobile-friendly web app that shows the Princeton Tiger Aquatics Club swim schedule for the next 7 days.

## Live Site

Visit: [https://gipsy86147.github.io/ptac-schedule/](https://gipsy86147.github.io/ptac-schedule/)

## Features

- **Group filter**: Switch between AG1, AG2, AG3, JR, SR, and VAR groups with pill buttons
- **Next 7 days**: Shows upcoming schedule at a glance
- **Location colors**: Each pool location has a distinct color (Denunzio, WAC, MCCC, PMS, Ben Franklin)
- **Google Maps links**: Tap the map icon to navigate to any pool location
- **Meet detection**: Competition/meet days are highlighted with a MEET badge
- **Offline fallback**: Caches the last successful fetch in localStorage
- **Remembers your group**: Selected group persists across sessions
- **Mobile-first**: Designed for phone screens with large tap targets

## How It Works

The app fetches the schedule from [GoMotion](https://www.gomotionapp.com/team/njptac/page/calendar1/all-groups) via a CORS proxy, parses the HTML table structure, and renders it as mobile-friendly cards grouped by day and location. No backend required.

**Data flow**: Fetch via CORS proxy -> Parse HTML tables -> Filter by group + date -> Render cards

## Setup

No build step required. The entire app is a single `index.html` file.

**Local development:**
```bash
# Clone the repo
git clone https://github.com/gipsy86147/ptac-schedule.git
cd ptac-schedule

# Serve locally (any static file server works)
python3 -m http.server 8080
# Then open http://localhost:8080
```

**GitHub Pages deployment:**
The site deploys automatically from the `main` branch. No CI/CD configuration needed.

## Tech Stack

- Vanilla HTML, CSS, and JavaScript (no frameworks, no build tools)
- CORS proxies: corsproxy.io (primary), allorigins.win (fallback)
- localStorage for caching and user preferences
