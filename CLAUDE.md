# Project guidelines

This folder holds small, single-file HTML pages for weather and related projects. Each page is self-contained (inline CSS and JS, no build step).

## Theme rules

- **Cheerful.** Pages should feel warm, friendly, and upbeat. Use a bright, welcoming palette and friendly copy. Avoid gloomy or clinical styling, even for bad weather.
- **Seasonal.** Every page should reflect the current season. For October, that means autumn tones such as pumpkin orange, golden yellow, russet red, and warm brown, with leaf, acorn, or harvest motifs used sparingly. Update the palette and motifs when the season changes.
- Keep both light and dark themes readable. Define colors as CSS custom properties on `:root` so the seasonal palette can be changed in one place.

## Working in this folder

- Keep each page as its own `.html` file. Do not add a build system unless asked.
- `plan.md` tracks the plan and status for a project. Check it before starting work on a page, and update its checkboxes when a step is done.
- Weather data is hard-coded in each page. Note the source and the date it was pulled in the page, and re-pull the data when asked to refresh it.
- Mark any value you could not verify, and do not present model output as observed conditions.

## Preview

- To view a page in Chrome, serve the folder locally, for example `python3 -m http.server 8765` from this folder, then open `http://127.0.0.1:8765/<page>.html`. Opening `file://` URLs is blocked for the Claude in Chrome extension.
