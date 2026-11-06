# FireSim — public documentation and data

Public companion to **FireSim**, a wildfire spread simulator for Alberta built on the Canadian
Forest Fire Danger Rating System (CFFDRS) Fire Behaviour Prediction (FBP) System.

- **App:** https://wildfire-simulator.vercel.app
- **Feedback and bug reports:** [open an issue](https://github.com/Tphambolio/firesim-docs-data/issues/new?labels=feedback)

FireSim's source code is kept in a separate, private repository. This repository holds what users,
reviewers and the app itself need in public: the validation record, pre-registrations, privacy notice
and the open data files the app's server downloads at build time.

## Documents (`docs/`)

| File | What it is |
|---|---|
| `docs/validation.md` | Validation methods and results |
| `docs/validation-scorecard.md`, `docs/scorecard/` | Dated validation scorecard (JSON) and how it is built |
| `docs/PREREG_*.md` | Pre-registrations of validation tests, written before scoring |
| `docs/privacy.md` | What the app collects and sends (telemetry, feedback) |
| `docs/data-sources.md` | Data sources, licences and refresh notes |
| `docs/fbp-reference.md` | FBP System reference used by the engine |
| `docs/ics-canada-209.md` | ICS Canada 209 form mapping |
| `docs/building-exposure.md` | Building exposure method |
| `docs/PROVENANCE.md` | Original git dates and commits of every document here |

The documents are verbatim copies from the code repository (see `docs/PROVENANCE.md` for the original
commit dates). **No licence is granted for the documents yet**; all rights reserved by the author
pending the owner's licence decision. Quoting with attribution for review and research is welcome.

### Documents not published here

Some documents the app refers to (the model card, the project record and decisions log, the
verification notes, the structure-spread specification and the frontend README) are not yet in
this repository. Ask through an issue if you need one of them.

## Data releases

The FireSim API image downloads these files at build time and checks each against its SHA-256.
Each release keeps **its own source licence**; nothing here is relicensed. Derived databases of
ODbL sources remain under the ODbL.

| Release tag | Files | Source | Licence |
|---|---|---|---|
| [`data-ab-fbp-2025`](https://github.com/Tphambolio/firesim-docs-data/releases/tag/data-ab-fbp-2025) | `ab_wildfire_fbp_fueltype_2025_100m_3400_cog.tif` (+ `.json`) | Government of Alberta, Alberta Wildfire FBP Fuel Type raster (2025-07-16) | Open Government Licence – Alberta |
| [`data-ab-prefire-v1`](https://github.com/Tphambolio/firesim-docs-data/releases/tag/data-ab-prefire-v1) | `ab_prefire_backcast_v1.tar` | NRCan NBAC 1985-2025 and SCANFI v2 (2010/2015/2020), typed to FBP | Open Government Licence – Canada |
| [`data-ab-buildings-2026-10`](https://github.com/Tphambolio/firesim-docs-data/releases/tag/data-ab-buildings-2026-10) | `ab_buildings_2026_10.fgb` (+ `.json`, `SHA256SUMS`) | Microsoft Canadian Building Footprints 2019; Statistics Canada Open Database of Buildings v3 (nine municipalities) | ODbL 1.0 (Microsoft; derived database); municipal open licences via ODB v3, listed in the release notes |
| [`data-ab-buildings-ms2019`](https://github.com/Tphambolio/firesim-docs-data/releases/tag/data-ab-buildings-ms2019) | `ab_buildings_ms2019.fgb` | Microsoft Canadian Building Footprints 2019 | ODbL 1.0 |
| [`data-ab-infra-2026-10`](https://github.com/Tphambolio/firesim-docs-data/releases/tag/data-ab-infra-2026-10) | `ab_terrain_mrdem30_100m.tif`, `ab_assets_2026.fgb`, `ab_major_roads_osm.fgb` (+ `.json`, `SHA256SUMS`) | NRCan MRDEM-30; Statistics Canada ODHF; OpenStreetMap | Terrain: Open Government Licence – Canada. Assets: OGL – Canada (ODHF) and ODbL (© OpenStreetMap contributors). Roads: ODbL (© OpenStreetMap contributors) |

Each release's notes carry the full attribution text and SHA-256 sums. These files were first
published on 2026-10 releases of the code repository and were moved here unchanged (same tags, file
names and checksums) on 2026-11-06.

No City of Edmonton LiDAR-derived fuel grid, canopy product or other non-open City data is published here.

## Disclaimer

FireSim is a planning and training tool. Its outputs are simulated projections, not observations;
verify with ground or air observation before any operational or public-protection decision. Data
are provided as is, under their sources' disclaimers.
