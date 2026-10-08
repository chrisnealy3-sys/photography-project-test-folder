# Plan: Three-Temperature Weather Page

## Goal
Show three temperatures for one location on one page: air, water, and surface. Each reading has its source, time, and units, so a viewer can tell measured values from model values.

## Status
- [x] Air temperature forecast for the North Pole (Open-Meteo, lat 90, lon 0), shown in `north-pole-weather.html`. The value needs verification.
- [x] Confirm Open-Meteo field names for the air, surface, and water temperature variables. Air is `temperature_2m`, surface is `soil_temperature_0cm`, water is `sea_surface_temperature` in the marine API.
- [x] Fix the unit error on the page. The earlier "9°C" was a Fahrenheit value labeled as Celsius. The real air reading is −11.5°C.
- [x] Add water temperature and surface temperature to the data. Water returns no value at this point (null), so the page shows "No reading".
- [x] Build the three-temperature display.
- [ ] Check the page in Chrome at phone and desktop widths, light and dark.
- [ ] Confirm the data is current before sharing.

## Steps

### 1. Data
- Air temperature: Open-Meteo forecast API, `temperature_2m`, 2 m above ground.
- Surface temperature: Open-Meteo forecast API. Check whether a skin or ground surface temperature variable is available. If not, use the closest variable and label it as such (for example, `soil_temperature_0cm`).
- Water temperature: Open-Meteo marine API, `sea_surface_temperature`. Check whether this location has ocean coverage. Near the North Pole the sea is usually under sea ice, so the value will be near the freezing point of seawater (about -1.8°C). Label it as a model value, not an observation.
- Units: °C, shown with °F in a secondary line.
- Record the source, the pull date and time (UTC), and the grid point for each variable.

### 2. Calculation
- Derive values from the raw data. Do not hard-code them.
- Show the current hour's value as the headline reading. Keep the daily high and low as secondary values.
- If a value is missing or unrealistic, show "no data" for that reading and do not substitute another value.

### 3. Display
- Three equal cards: Air, Water, Surface. Each card shows the value, the source label, and the time.
- Follow the seasonal and cheerful rules in CLAUDE.md.
- Keep a short warning when a value looks implausible, as the current page does.

### 4. Verification
- Compare the air temperature with a second source for the same time, if one is available.
- Open the page in Chrome through a local server and check the layout at 375 px and desktop widths, with no horizontal scroll.
- Check light and dark mode.

## Open questions
- Is a model value acceptable for water and surface, or does the page need a measured source? Measured ice and sea-surface data for the Arctic may not be available for this exact point.
- Should the page refresh automatically, or stay a snapshot? An automatic refresh would need a fetch call in the page.
- Should the Florence page get the same three-temperature display?

## Next actions
1. Check the Open-Meteo variable names and whether each returns data for lat 90, lon 0.
2. Add the three data fields to `north-pole-weather.html` and build the cards.
