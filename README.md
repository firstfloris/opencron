# OpenCron

Visual cron job dashboard for [OpenClaw](https://github.com/firstfloris/openclaw). Live countdown timers, run history, and calendar view — all in a single HTML file.

![Dashboard overview](docs/overview.png)

## Features

- **Live countdowns** — next-run timers update every second with smooth color transitions (normal → soon → imminent)
- **Badge fill indicator** — progress bar fills as the next run approaches
- **Braille icon system** — unicode braille characters as semantic icons throughout the UI
- **Run history** — chronological log with duration, model, token usage, and output summaries
- **Calendar view** — month grid showing past runs (ok/error) and upcoming scheduled runs with stagger animations
- **Expandable job cards** — schedule, duration, delivery status, error details, and full prompt
- **Responsive** — works on mobile, respects `prefers-reduced-motion`

### Detail View

Expand any job card to see schedule details, braille-labeled metadata, description, and collapsible prompt.

![Detail view](docs/detail-view.png)

### Run History

Browse recent runs across all jobs, sorted by time. Expand any run for output, errors, and metadata.

![Runs view](docs/runs.png)

### Calendar

Month view with past run statuses and upcoming scheduled runs. Days stagger in on navigation.

![Calendar view](docs/calendar.png)

## Usage

### Standalone

Open `demo.html` in any browser — no server required. Uses mock data.

### With OpenClaw

The dashboard reads live data from the OpenClaw gateway:

```
http://<gateway-host>:18789/__openclaw__/canvas/cron.html?token=<your-token>
```

See [opencron-skill](https://github.com/firstfloris/opencron-skill) for deployment scripts.

## Design

- Dark gradient UI with neon accents (chartreuse, red, yellow, blue)
- Animation as UX feedback (Norman's Principle 6) — every interaction produces immediate visual response
- Braille unicode icons as signifiers — no external icon fonts
- Visual hierarchy via font size, weight, and opacity (labels small+dim, values bright+mono)
- `backdrop-filter: blur(20px)` glass cards

## License

MIT
