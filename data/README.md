# Datasets used in CMSC 173 lectures and labs

## `ph_earthquakes.csv`

11,391 earthquakes of magnitude 4.5 and up, 1990-01-01 to 2025-12-31 (UTC), in the box
4°N–21.5°N, 116°E–128°E around the Philippines.

- **Source:** USGS ANSS Comprehensive Catalog (ComCat), via
  `https://earthquake.usgs.gov/fdsnws/event/1/query?format=csv&starttime=1990-01-01&endtime=2025-12-31T23:59:59&minlatitude=4&maxlatitude=21.5&minlongitude=116&maxlongitude=128&minmagnitude=4.5&orderby=time-asc`
- **Downloaded:** 2026-10-04. The catalogue is revised over time; this file is a frozen snapshot so the
  numbers on the slides stay true.
- **Licence:** USGS data are in the U.S. public domain.
- **Columns kept:** `time` (UTC, `YYYY-MM-DD HH:MM:SS`), `latitude`, `longitude`, `depth` (km), `mag`,
  `magType` (the magnitude scale: `mb`, `mww`, …), `place` (USGS's description), `id` (USGS event id).
- **Note:** the box is a rectangle, not a border, so it also holds quakes off Borneo and Indonesia's
  Talaud islands.

```python
import pandas as pd
url = "https://raw.githubusercontent.com/njpinton/cmsc173-labs/main/data/ph_earthquakes.csv"
quakes = pd.read_csv(url, parse_dates=["time"])
```
