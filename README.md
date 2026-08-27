# Fleet Movement Heat Map — Top Fuel Consumer

An anonymized, interactive heat map of the single **highest fuel-consuming vehicle** in a
~4,000-vehicle fleet-telematics operation — a heavy truck running the **Riyadh–Jeddah
corridor**. Every GPS position it reported is aggregated into a presence-density heat layer,
alongside its headline operating stats.

**Live page:** _(after enabling GitHub Pages, paste your link here — e.g._
`https://<your-username>.github.io/<repo>/`_)_

---

## Headline numbers (Apr–Aug 2026)

| Metric | Value |
|--------|------:|
| Riyadh ⇄ Jeddah legs | 24 (≈ 12 round trips) |
| Idling hours (total) | 173 |
| Driving hours (total) | 1,076 |
| Recorded trips | 791 |
| Distance driven | 32,526 km |
| Fuel filled | 3,197.7 L |

The corridor accounts for ~22,800 km of the 32,526 km driven — this truck's main job is
long-haul Riyadh ↔ Jeddah.

## How it was built

- **Top consumer** — the vehicle with the highest total litres filled across the whole fleet
  (sum of fuel entries).
- **Heat map** — ~508,000 GPS points from the telemetry history, aggregated onto a ~110 m
  grid and weighted by dwell density.
- **Riyadh ⇄ Jeddah legs** — each GPS point tagged by city (bounding boxes for Riyadh and
  Jeddah); the timeline is reduced to a sequence of city visits and every crossing counted.
- **Idling / driving hours, trips, distance** — summed from the vehicle's completed trips in
  the analytics store.

## Privacy

This is a **public, anonymized** page:

- No plate number, company name, VIN, or device IMEI.
- Coordinates are coarsened to ~110 m so no exact depot or stop is pinpointed.
- Only aggregate operating figures are shown.

## Notes

- Leaflet and the heat-map plugin are **inlined** in the page, so it renders with no external
  script dependency. The base map **tiles** load from OpenStreetMap at view time, so the page
  needs an internet connection to show streets (the heat layer still draws without them).
- Figures are a point-in-time snapshot and are estimates for operational insight.
