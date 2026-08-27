# Fleet Fuel & Movement Analytics (anonymized)

Interactive, anonymized dashboards for a logistics operator's trucks — built from GPS
telemetry and fuel records. Two pages:

| Page | What it shows |
|------|---------------|
| **`index.html`** | The single **highest fuel-consuming vehicle** in the fleet — a heavy truck on the Riyadh–Jeddah corridor: movement heat map + operating stats (fuel, distance, idling, Riyadh⇄Jeddah trips). |
| **`fleet.html`** | **All trucks** of that operator on one map — combined heat + per-truck trails you can toggle, KPI boxes that filter to the selected truck(s), a weight-class breakdown (heavy شاحنة vs light pickups), a per-truck fuel-economy table, and the fleet's repeating corridors. |

The two pages are cross-linked. Start at `index.html`.

**Live pages**
- Single truck: `https://ameenelzaki96.github.io/fleet-movement-heatmap/`
- Full fleet: `https://ameenelzaki96.github.io/fleet-movement-heatmap/`

---

## Highlights

- **Top consumer:** one heavy truck — 3,197 L, 32,526 km, **24 Riyadh⇄Jeddah legs (≈12 round trips)**, 173 idling hours (Apr–Aug 2026).
- **Fleet corridors:** Riyadh ⇄ Jeddah dominates (37 legs), then Riyadh ⇄ Makkah and Jeddah ⇄ Makkah.
- **Two-tier operation:** the heavy trucks run the long-haul corridor (~9.7 L/100km, low idling); the light pickups do local Riyadh duty (far more idling per km).
- **Efficiency finding:** swapping city trucks onto the corridor would **not** save fuel — the waste is city idling and the roles need different weight classes. The real levers are cutting idling and maximizing corridor load.

## How it was built

- **Top consumer** = highest total litres filled across the fleet.
- **Heat maps** = GPS positions aggregated onto a ~110 m grid, weighted by dwell density.
- **Corridors** = each GPS point tagged by city zone; the timeline reduced to a sequence of city visits and every crossing counted.
- **Fuel economy** = litres filled ÷ GPS trip distance; idling/driving hours summed from completed trips.

## Privacy

Fully anonymized: no plate numbers, company names, VINs, or device IMEIs. Coordinates are
coarsened to ~110 m so no exact depot or stop is pinpointed. Only aggregate figures are shown.

## Notes

- Leaflet and the heat-map plugin are **inlined**, so the pages render with no external script
  dependency. Base-map **tiles** load from OpenStreetMap at view time (needs an internet
  connection to show streets; the heat/points still draw without them).
- Figures are a point-in-time snapshot and are estimates for operational insight.
