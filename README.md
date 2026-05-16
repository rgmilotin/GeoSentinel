# GeoSentinel

**Early Warning Intelligence for Critical Infrastructure**

GeoSentinel is a decision-support platform for detecting early risk indicators in underground and near-underground critical infrastructure, with a focus on active mines, salt mines, coal mines, and highway tunnels. The project was developed during **HackTM 2026** as a technical and entrepreneurial prototype for infrastructure risk monitoring in Romania and the surrounding region.

The system combines satellite deformation data, seismic activity, hydrological indicators, air-quality signals, structural-health measurements, machine learning anomaly detection, and AI-generated operational reports into a single monitoring workflow.

GeoSentinel does not replace authorized inspectors, geotechnical engineers, mine operators, tunnel designers, or public authorities. It is designed as a complementary early-warning and decision-support layer that helps correlate weak signals before they become critical incidents.

---

## Table of Contents

- [Project Context](#project-context)
- [Problem Identified During HackTM 2026](#problem-identified-during-hacktm-2026)
- [Solution Overview](#solution-overview)
- [Why GeoSentinel Stands Out](#why-geosentinel-stands-out)
- [Core Capabilities](#core-capabilities)
- [Monitored Infrastructure](#monitored-infrastructure)
- [Data Sources](#data-sources)
- [Detection and Risk Scoring](#detection-and-risk-scoring)
- [AI Briefing Agent](#ai-briefing-agent)
- [Technical Architecture](#technical-architecture)
- [Technology Stack](#technology-stack)
- [Repository Structure](#repository-structure)
- [Quickstart](#quickstart)
- [Useful Commands](#useful-commands)
- [API Endpoints](#api-endpoints)
- [Example Workflow](#example-workflow)
- [Project Status](#project-status)
- [Roadmap](#roadmap)
- [Disclaimer](#disclaimer)

---

## Project Context

GeoSentinel was created as part of **HackTM 2026**, where the team focused on a high-impact infrastructure safety challenge: the lack of an integrated, affordable, and explainable early-warning system for underground infrastructure.

The starting point was the observation that major underground infrastructure incidents rarely happen without precursors. In many cases, warning signals may already exist across satellite measurements, seismic activity, infiltration data, structural deformation, environmental sensors, public reports, and technical inspections. The core issue is that these signals are usually fragmented across different systems, institutions, time scales, and data formats.

For Romania, this problem is especially relevant in two critical verticals:

1. **Mines and salt mines**, where subsidence, freshwater infiltration, microseismicity, gas concentration, and underground-air quality can indicate increasing operational risk.
2. **Highway tunnels**, where lining convergence, surface subsidence, vibration, humidity, water inflow, and crack evolution are essential indicators for structural-health monitoring during both construction and operation.

GeoSentinel was designed to connect these signals into one monitoring platform and generate practical, explainable, and audit-friendly alerts.

---

## Problem Identified During HackTM 2026

During the hackathon research phase, the team identified a structural problem in the way critical underground infrastructure is monitored:

- **Risk signals are fragmented.** Satellite, seismic, hydrological, environmental, and structural data are often analyzed separately.
- **Monitoring is reactive rather than predictive.** Many systems are designed to document an issue after it becomes visible, not to detect correlated weak signals early.
- **Existing enterprise solutions are expensive and deployment-heavy.** Large monitoring projects can require custom instrumentation, specialized contractors, and high upfront costs.
- **Local operational context is often missing.** Generic monitoring tools do not automatically translate signals into reports that are useful for local authorities, inspectors, operators, or infrastructure contractors.
- **Technical reports are not always actionable.** Raw measurements must be converted into a clear operational interpretation: what changed, why it matters, what precedent it resembles, and what action should be taken.

The Praid reference scenario strongly influenced the project direction. The project treats the combination of **InSAR subsidence, infiltration growth, and microseismicity** as a high-value pattern for salt-mine risk analysis. GeoSentinel was built to demonstrate how a platform could correlate such signals and generate earlier operational awareness.

---

## Solution Overview

GeoSentinel provides a multi-source early-warning workflow for mines and tunnels:

1. **Data ingestion**
   - Collects or simulates infrastructure-relevant signals from public APIs, open data, and sensor-ready interfaces.
   - Supports real data where available and synthetic fallback where live data is unavailable.

2. **Signal processing**
   - Normalizes each site into time-series datasets.
   - Computes recent trends, baseline deviations, rolling averages, cumulative displacement, and signal severity.

3. **Risk detection**
   - Applies interpretable physical thresholds for each monitored signal.
   - Computes an anomaly score using machine learning.
   - Combines deterministic thresholds with multivariate anomaly detection.

4. **AI-based operational interpretation**
   - Converts alerts into structured operational briefs.
   - Adds historical context from similar incidents.
   - Produces recommendations for monitoring escalation, inspection, restriction, or emergency action.

5. **Interactive dashboard**
   - Displays monitored sites, risk levels, signal details, and time-series charts.
   - Uses a modern web UI for demos, operators, and stakeholders.

---

## Why GeoSentinel Stands Out

GeoSentinel is not just a dashboard. It is a complete early-warning prototype that connects data engineering, geotechnical reasoning, structural-health monitoring, machine learning, and AI-generated reporting.

| Area | Conventional Monitoring | GeoSentinel Approach |
|---|---|---|
| Data integration | Separate tools for satellite, seismic, hydro, and sensors | Unified multi-source fusion across mines and tunnels |
| Cost model | Often based on expensive custom deployments | Open-data-first architecture with modular sensor integration |
| Risk detection | Manual interpretation or fixed dashboards | Physical thresholds plus ML anomaly scoring |
| Reporting | Technical reports requiring expert interpretation | AI-generated operational briefs with recommendations |
| Local context | Often generic or vendor-specific | Designed around Romanian infrastructure actors and site types |
| Deployment target | Usually one infrastructure category | Same engine supports both mines and highway tunnels |
| Explainability | May be limited to raw measurements | Every alert contains signal values, thresholds, and reasoning |
| Hackathon readiness | Usually a concept or isolated demo | End-to-end pipeline with ingestion, detection, API, UI, and reports |

The main differentiator is the **dual-use monitoring engine**: the same platform can analyze both underground mining risk and tunnel structural-health monitoring by changing the signal set and threshold profile.

---

## Core Capabilities

### Multi-source data fusion

GeoSentinel combines multiple signal families:

- Satellite-based surface deformation through InSAR-compatible datasets.
- Seismic and microseismic activity.
- Weather and hydrological indicators.
- Water infiltration and water inflow indicators.
- Underground and tunnel air-quality indicators.
- Tunnel lining convergence.
- Peak ground velocity vibration measurements.
- Wall humidity and LiDAR-based crack evolution.

### Explainable alerting

Each alert includes:

- The affected site.
- Overall severity level.
- Individual signal severity levels.
- Signal value and unit.
- Threshold that was exceeded.
- Short technical explanation.
- Machine learning anomaly score.
- Summary metrics for the monitored site.

### Offline and LLM-based reporting

The project supports two briefing modes:

- **Offline brief generator:** deterministic, template-based, does not require an API key.
- **LLM brief generator:** uses an Anthropic-compatible API key to generate more natural operational reports.

### Web-based dashboard

The UI provides:

- Monitored-site overview.
- Mine and tunnel sector views.
- Interactive time-series charts.
- Risk indicators.
- Site-level technical details.
- Operational alert sections.
- Business/demo-oriented presentation pages.

---

## Monitored Infrastructure

The prototype includes 12 monitored sites: 7 mines and 5 highway tunnel assets.

### Mines and Salt Mines

| Site | Type | Operator / Context |
|---|---|---|
| Praid Salt Mine | Salt mine | Reference event used for backtesting |
| Ocna Dej Salt Mine | Salt mine | Active Salrom site |
| Cacica Salt Mine | Salt mine | Active Salrom site |
| Slanic Prahova Salt Mine | Salt mine | Active Salrom site |
| Targu Ocna Salt Mine | Salt mine | Active Salrom site |
| Lupeni Mine | Coal mine | Jiu Valley mining context |
| Livezeni Mine | Coal mine | Jiu Valley mining context |

### Highway Tunnels

| Site | Road Corridor | Context |
|---|---|---|
| Margina-Holdea T1 Tunnel | A1 | Construction / monitoring scenario |
| Margina-Holdea T2 Tunnel | A1 | Long tunnel construction scenario |
| Poiana Tunnel | A1 Sibiu-Pitesti | TBM excavation scenario |
| Curtea de Arges Tunnel | A1 | NATM excavation scenario |
| Meses Tunnel | A3 | Design / baseline monitoring scenario |

---

## Data Sources

GeoSentinel uses a hybrid data model: real public data where available, sensor-ready hooks where production integrations would be required, and synthetic fallback for demo continuity.

| Data Source | Role | Current Status |
|---|---|---|
| Open-Meteo Weather | Precipitation, weather-driven infiltration modeling | Real API integration |
| Open-Meteo Air Quality | Surface PM10, CO, NO2 used for air-quality modeling | Real API integration |
| EMSC / USGS seismic catalog | Regional seismicity and seismic-event context | Real API integration |
| EGMS / Sentinel-1 InSAR | Surface deformation and subsidence | Hook prepared; manual data download required |
| Underground air-quality model | CO, NO2, PM10, CH4 estimates | Modeled from surface air and operational activity |
| Tunnel convergence sensors | Lining deformation | Synthetic demo data; production sensor hook planned |
| PGV / vibration sensors | Dynamic loads from traffic, excavation, blasting, seismicity | Synthetic demo data; production sensor hook planned |
| LiDAR crack scanning | Crack count and surface geometry evolution | Synthetic demo data; production sensor hook planned |
| Water inflow sensors | Tunnel water ingress | Synthetic demo data; production sensor hook planned |

All real-data ingestion modules include fallback behavior so that the demo remains functional even when an external API does not respond.

---

## Detection and Risk Scoring

The detection engine combines interpretable engineering thresholds with a machine learning anomaly score.

### 1. Deterministic physical thresholds

The thresholding system classifies each signal into one of four severity levels:

- `info`
- `watch`
- `warning`
- `alarm`

Thresholds are defined by infrastructure type. For example:

- Salt mines use lower subsidence thresholds than coal mines.
- Coal mines include methane-specific risk logic.
- Tunnels include lining convergence, PGV, humidity, LiDAR cracks, and water inflow thresholds.

### 2. Signal-specific checks

For mines, the system evaluates:

- InSAR displacement and velocity.
- Microseismicity rate over a recent time window.
- Water infiltration increase versus baseline.
- CO concentration.
- PM10 dust concentration.
- CH4 methane concentration for coal mines.

For tunnels, the system evaluates:

- Surface subsidence above the tunnel alignment.
- Regional seismicity.
- Lining convergence in mm/day.
- Peak ground velocity in mm/s.
- Wall humidity.
- New LiDAR-detected cracks.
- Tunnel water inflow versus baseline.
- CO and PM10 concentration.

### 3. Machine learning anomaly score

GeoSentinel uses an `IsolationForest` model over rolling multivariate windows. The model considers multiple correlated variables, including:

- Precipitation.
- Infiltration.
- Groundwater level.
- Seismic event count.
- Maximum seismic magnitude.
- InSAR velocity.

The output is normalized into a score between 0 and 1, where higher values indicate more abnormal behavior.

### 4. Overall severity

The final severity is computed from the maximum severity of all active signals, with additional escalation logic based on the machine learning anomaly score.

This design keeps the system explainable while still allowing it to detect unusual combinations that may not be captured by single-threshold rules.

---

## AI Briefing Agent

GeoSentinel includes an AI briefing layer that transforms numerical alerts into operational reports.

Each generated brief contains:

1. **Situation summary**
   - Site, operator, severity, key metrics, and ML anomaly score.

2. **Physical interpretation**
   - A plausible mechanism explaining why the current signal combination matters.

3. **Historical precedents**
   - Similar events from the internal case database.

4. **Operational recommendations**
   - Concrete actions depending on the severity level.

5. **Confidence level**
   - A transparent explanation of how reliable the current alert interpretation is.

The offline agent uses templates and the internal case database. The LLM-based agent can use an Anthropic-compatible API configuration for more natural-language reporting.

---

## Technical Architecture

GeoSentinel follows a modular pipeline:

```text
Public data / sensor inputs
        |
        v
Ingestion modules
        |
        v
Normalized site time series
        |
        v
Threshold checks + Isolation Forest anomaly detection
        |
        v
alerts.json
        |
        +--> Flask API
        |       |
        |       v
        |   HTML dashboard
        |
        +--> Offline / LLM operational brief generator
```

### Main modules

- `config.py` defines monitored sites, operators, coordinates, infrastructure type, status, tunnel length, and other metadata.
- `ingestion/` collects or generates data from weather, air-quality, seismic, InSAR-compatible, hydrological, and tunnel-specific sources.
- `detection/` classifies signals, computes alert severity, and generates `alerts.json`.
- `agent/` generates operational briefs from alert data and historical case references.
- `api/` exposes the Flask backend and JSON endpoints used by the frontend.
- `frontend/` contains the interactive HTML/CSS/JavaScript UI.
- `dashboard/` contains an additional Streamlit-based dashboard module.
- `data/` stores generated CSV time series, alerts, and generated briefs.

---

## Technology Stack

### Backend and data processing

- Python
- Pandas
- NumPy
- scikit-learn
- Requests
- Pydantic
- Flask
- python-dotenv

### Machine learning and analytics

- Isolation Forest for anomaly detection.
- Rolling-window feature extraction.
- Physical threshold classification.
- Historical-case matching for contextual reporting.

### AI layer

- Anthropic-compatible API client for LLM-generated briefs.
- Offline fallback report generator for demos without external API access.
- Retrieval-inspired case matching using a structured historical case database.

### Frontend and visualization

- HTML, CSS, JavaScript.
- Plotly.js for charts.
- Leaflet-compatible map logic and site visualization.
- Dark, technical UI designed for demo and stakeholder presentation.

### Optional dashboard

- Streamlit.
- Plotly.
- Folium / streamlit-folium.

---

## Repository Structure

```text
GeoSentinel/
├── agent/
│   ├── brief.py              # LLM-based operational brief generator
│   ├── brief_offline.py      # Offline deterministic brief generator
│   └── case_database.py      # Historical precedent database
├── api/
│   └── server.py             # Flask backend and JSON API
├── dashboard/
│   └── app.py                # Optional Streamlit dashboard
├── data/                     # Generated CSV data, alerts and briefs
├── detection/
│   ├── detect.py             # Main anomaly detection engine
│   └── thresholds.py         # Physical thresholds by site type
├── frontend/
│   └── index.html            # Interactive web UI
├── ingestion/
│   ├── air_quality.py        # Air-quality ingestion and modeling
│   ├── hydro_weather_real.py # Open-Meteo weather and infiltration modeling
│   ├── insar.py              # InSAR-compatible subsidence ingestion
│   ├── real_data.py          # Main ingestion orchestrator
│   ├── seismic_real.py       # EMSC / USGS seismic ingestion
│   └── tunnel_signals.py     # Tunnel-specific synthetic/sensor-ready signals
├── config.py                 # Monitored site configuration
├── requirements.txt          # Python dependencies
├── .env.example              # Environment variable template
└── README.md                 # Project documentation
```

---

## Quickstart

### 1. Create and activate a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate
```

For Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

For Windows Command Prompt:

```cmd
.venv\Scripts\activate.bat
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Generate or refresh data

```bash
python -m ingestion.real_data
```

This creates or updates the CSV files inside `data/` for all monitored mines and tunnels.

### 4. Run anomaly detection

```bash
python -m detection.detect
```

This generates `data/alerts.json`, which is consumed by the API and frontend.

### 5. Start the Flask web application

```bash
python -m api.server
```

Open the local application at:

```text
http://localhost:5000
```

---

## Useful Commands

Generate data only for mines:

```bash
python -m ingestion.real_data --only mines
```

Generate data only for tunnels:

```bash
python -m ingestion.real_data --only tunnels
```

Run a Praid-oriented backtest ending on a specific date:

```bash
python -m ingestion.real_data --end 2025-06-01
```

Run detection for all configured sites:

```bash
python -m detection.detect
```

Generate an offline operational brief:

```bash
python -m agent.brief_offline praid
```

Generate an LLM-based operational brief:

```bash
python -m agent.brief praid
```

Start the web UI and API:

```bash
python -m api.server
```

---

## API Endpoints

When the Flask server is running, the following endpoints are available:

| Endpoint | Method | Description |
|---|---|---|
| `/` | GET | Serves the interactive HTML dashboard |
| `/api/sites` | GET | Returns all monitored sites with metadata, risk status, signals and data sources |
| `/api/timeseries/<site_id>` | GET | Returns site-specific time-series data for charts |
| `/api/alerts` | GET | Returns the raw alert output from the detection engine |
| `/api/health` | GET | Returns backend health, site count, alert count and timestamp |

Example:

```bash
curl http://localhost:5000/api/health
```

---

## Example Workflow

A typical end-to-end run looks like this:

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Ingest data for all monitored sites
python -m ingestion.real_data

# 3. Generate alerts
python -m detection.detect

# 4. Generate an operational report for Praid
python -m agent.brief_offline praid

# 5. Start the API and dashboard
python -m api.server
```

After this sequence, the frontend can display current risk states, signal values, and time-series charts for each monitored site.

---

## Configuration

The main project configuration is located in `config.py`.

Each monitored site includes:

- Site ID.
- Site name.
- Operator.
- Infrastructure type.
- Latitude and longitude.
- Operational status.
- Depth or tunnel cover.
- Tunnel length, where applicable.
- Excavation progress, where applicable.
- Notes for contextual interpretation.

To add a new site, add a new `MineSite` entry to either `MINES` or `TUNNELS`, then run the ingestion and detection commands again.

---

## Environment Variables

The project can run without an LLM API key by using the offline briefing generator.

For LLM-based brief generation, create a `.env` file based on `.env.example`:

```env
ANTHROPIC_API_KEY=your_key_here
ANTHROPIC_MODEL=your_model_here
```

Then run:

```bash
python -m agent.brief praid
```

---

## Project Status

GeoSentinel is currently a **HackTM 2026 prototype**. It demonstrates the feasibility of an integrated early-warning system, but it is not a certified safety product.

Implemented:

- Multi-site infrastructure configuration.
- Data ingestion pipeline.
- Real API integrations for weather, air quality and seismic data.
- Synthetic fallback for unavailable or production-only data sources.
- Mine-specific and tunnel-specific signal processing.
- Threshold-based severity classification.
- Isolation Forest anomaly scoring.
- JSON alert generation.
- Offline operational brief generation.
- LLM-ready brief generation.
- Flask API.
- Interactive frontend dashboard.

Partially implemented or planned:

- Production integration with live InSAR downloads.
- Real-time tunnel sensor ingestion.
- Real LiDAR point-cloud processing.
- Inspector-facing report export in PDF format.
- Authentication and user roles.
- Persistent database instead of local CSV and JSON files.
- Deployment pipeline for cloud or edge infrastructure.

---

## Roadmap

Potential next steps:

1. **Real InSAR ingestion**
   - Connect the EGMS / Sentinel-1 workflow to automated data retrieval and preprocessing.

2. **Sensor gateway integration**
   - Add MQTT, LoRaWAN or HTTP ingestion for field sensors.

3. **Database migration**
   - Replace local CSV and JSON storage with PostgreSQL, PostGIS or a time-series database.

4. **PDF report generation**
   - Export inspector-ready operational reports with charts, metadata and audit trail.

5. **Geospatial analytics**
   - Add risk polygons, sensor-placement recommendations and map overlays.

6. **Role-based dashboard**
   - Separate views for operators, inspectors, contractors and emergency-response teams.

7. **Model calibration**
   - Calibrate thresholds per concession, tunnel section and historical baseline.

8. **Production deployment**
   - Package the system for containerized deployment and secure remote access.

---

## Disclaimer

GeoSentinel is a decision-support prototype developed during HackTM 2026. It is not a certified monitoring system, regulatory tool, emergency-management system, or replacement for authorized technical inspection.

All generated alerts, reports, recommendations and anomaly scores must be reviewed by qualified professionals before any operational or safety-critical decision is made.

---

## Suggested Repository Description

Early-warning intelligence platform for mines and highway tunnels, combining InSAR, seismic, hydrological, environmental and structural-health signals with ML anomaly detection and AI-generated operational briefs.
