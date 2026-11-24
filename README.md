# Tornado Path Predictability from the Tracks of U.S. Landfalling Hurricanes

Maps tornadoes spawned by landfalling Atlantic hurricanes against the storms' best tracks. For each tornado, the notebook works out where it formed relative to the storm center (quadrant, distance, and storm-relative position) and flags tornado paths that deviate from typical southwest-to-northeast motion.

**Interactive map:** https://kconner-11000.github.io/Tornado_Paths_Map/

Storms currently included: Beulah (1967), Michelle (2001), Frances (2004), and Ivan (2004).

## Data sources

Both datasets download automatically when the notebook runs, so there is nothing to put in the repo by hand.

- **Tornadoes:** NOAA Storm Prediction Center (SPC) tornado database, 1950–2024
- **Hurricane tracks:** NOAA National Hurricane Center HURDAT2 Atlantic best-track data, 1851–2024

## Running it

```bash
git clone https://github.com/KConner-11000/Tornado_Paths_Map.git
cd Tornado_Paths_Map

python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt

jupyter lab
```

Then open `hurricane_tornado_map.ipynb` and run all cells.

## What the notebook does

1. Downloads the SPC tornado data and keeps the tornadoes that fall within each storm's date window
2. Downloads and parses the HURDAT2 tracks for the selected storms
3. Interpolates the storm center to each tornado's time, then computes distance, quadrant (relative to storm motion), and storm-relative x/y in nautical miles
4. Calculates each tornado's compass bearing and flags atypical paths
5. Builds an interactive Plotly map of hurricane tracks, tornado paths, and liftoff points, and saves it as `hurricane_tornado_map.html`

