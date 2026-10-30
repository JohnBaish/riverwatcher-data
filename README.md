# riverwatcher-data

The data behind Riverwatcher (`riverwatcher.baish.net`; code in
[JohnBaish/riverwatcher](https://github.com/JohnBaish/riverwatcher)): river levels in
England from the Environment Agency, collected and worked out by Riverwatcher's scripts.
Kept apart from the code so the code repo stays small.

This uses Environment Agency flood and river level data from the real-time data API (Beta).
Contains public sector information licensed under the Open Government Licence v3.0.
Contains OS data © Crown Copyright and database rights 2026.

The Environment Agency's recent figures are provisional: it checks them later and sometimes
corrects them.

## What's here

- `data/gauges.json`: the river gauges, with each one's river, its place along the river
  (from OS Open Rivers), its county and region (OS Boundary-Line), and whether its level is
  held by a lock or weir.
- `data/history/<gauge>.json`: each gauge's history from the Environment Agency's archive,
  boiled down to its usual levels for each time of year and its records. `index.json` lists
  how each one went.
- `data/days/<date>.json`: each gauge's usual level for the day, and its hourly averages
  where there are readings.

`.github/workflows/history.yml` ("Run workflow" only) downloads the history and the day
files; it's started by hand.
