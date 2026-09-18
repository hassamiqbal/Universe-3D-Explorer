# Universe 3D Explorer

An interactive Jupyter notebook for exploring the Solar System, planetary moon systems, the Milky Way, nearby stars, exoplanet hosts, nearby galaxies and a simple Hubble-expansion teaching model in 3D.

The notebook uses explicit coordinate frames and units so that approximate teaching models, measured catalogue quantities and optional online ephemerides stay separate rather than being presented as the same kind of data.

## What is included

- Time-dependent positions for the eight planets using JPL approximate orbital elements.
- Inner and full Solar System Plotly animations.
- An embedded JPL moon catalogue snapshot covering Earth, Mars, Jupiter, Saturn, Uranus, Neptune and Pluto.
- Schematic moon-system views plus optional geometric trajectories from JPL Horizons.
- A Milky Way model with the Sun's Galactic motion.
- A local sky view for the Galactic-centre direction.
- Optional Gaia nearby-star positions and velocity vectors.
- Optional NASA Exoplanet Archive host-star and system views.
- Selected Local Group galaxies with clearly labelled radial-velocity components.
- A separate synthetic Hubble-law expansion model.
- Sanity checks that document the reference frame and interpretation of each speed.

## Run locally

Python 3.11 or 3.12 is recommended. Open `notebooks/Universe_3D_Explorer.ipynb` in Jupyter Notebook or JupyterLab and run the numbered cells in order. The first code cell installs the required packages into the active notebook kernel.

The default workflow uses embedded data and models. Optional online sections are disabled initially. They can be enabled in the controls cell:

```python
RUN_HORIZONS = False
RUN_GAIA = False
RUN_EXOPLANETS = False
```

Set the relevant flag to `True` and rerun that section when live catalogue or ephemeris data are required. Downloaded data are cached in `universe_cache/`.

## Main dependencies

`numpy`, `pandas`, `plotly`, `astropy`, `astroquery`, `requests`, `lxml`, and `nbformat`. The exact supported ranges are listed in `requirements.txt`.

## Scientific scope

The notebook deliberately separates models from measurements. The approximate planetary model is not a replacement for JPL Horizons. Schematic moon animations do not encode every real orbital inclination, phase or retrograde direction. The Milky Way and cosmic-expansion sections are teaching models, not full N-body simulations. Nearby-galaxy arrows show only the measured radial component where stated.

Sources and provenance are documented inside the notebook, including JPL Solar System Dynamics, Astroquery/JPL Horizons, ESA Gaia, the NASA Exoplanet Archive, Astropy coordinate documentation, and the nearby-galaxy compilation used for the selected Local Group values.

## Repository structure

```text
Universe-3D-Explorer/
├── README.md
├── notebooks/
│   └── Universe_3D_Explorer.ipynb
├── requirements.txt
└── .gitignore
```

## Notes

Interactive Plotly outputs are generated when the notebook is run. Standalone HTML exports can be enabled from the final export cell; generated exports and cache files are intentionally excluded from version control.
