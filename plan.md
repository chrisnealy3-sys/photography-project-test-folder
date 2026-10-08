# Plan: Florence 5-Day Weather Page

## Goal
A single-page HTML view of the Florence, Italy forecast for the next five days, with a graphic for each day and a movie-inspired visual.

## Status
- [x] Pull a 5-day forecast for Florence (Open-Meteo, lat 43.77, lon 11.25)
- [x] Scaffold `florence-weather.html`: day cards and movie posters
- [ ] Check the page visually in a browser at phone and desktop widths
- [ ] Confirm the data is current before sharing

## Steps

### 1. Data
- Source: Open-Meteo daily forecast, timezone Europe/Rome, 5 days.
- Fields: weather code, max and min temperature, precipitation probability, max wind.
- The data is hard-coded in the page. To refresh it, re-run the Open-Meteo request and update the `days` array.

### 2. Day graphics
- Each card shows an SVG icon (rain, overcast, fog), high and low temperature, and bars for rain chance and wind.
- Wind bars scale to the five-day maximum so days compare fairly.

### 3. Movie visuals
- One poster per weather type, drawn in SVG.
- Mapping: rain → *Singin' in the Rain*, overcast → *Blade Runner*, fog → *The Fog*.

### 4. Verification
- Open the page in the Browser pane.
- Check layout at 375px (phone) and desktop widths, with no horizontal scroll.
- Check light and dark mode.

## Open questions
- Should the forecast refresh automatically, or stay a snapshot? Automatic refresh would need a fetch call in the page.
- Should the movie picks be tied to Florence (for example, films shot there)?
- Is a single file enough, or should the data move to its own JSON file?

## Next actions
1. Open the page and check the layout.
2. Decide on auto-refresh and the film picks.
