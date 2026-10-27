# 🌦️ SkyGuard AI
### Intelligent Real-Time Anomaly Detection for Automatic Weather Stations

SkyGuard AI is a weather-station monitoring platform designed to detect abnormal sensor readings, monitor sensor health, and support reliable weather data quality analysis.

The system analyzes temperature, atmospheric pressure, and relative humidity to identify unusual readings, highlight potential sensor faults, and help distinguish suspicious sensor behavior from plausible meteorological variations.

## 🚀 Key Features

- **Multi-Station Monitoring:** Monitor weather telemetry across 10 configured weather stations in India.
- **Real-Time Anomaly Analysis:** Evaluate sensor readings and flag potentially abnormal observations.
- **Multi-Layer Detection Engine:** Combines physical limits, temporal changes, statistical deviation, thermodynamic consistency, and machine-learning-based scoring.
- **Sensor Health Monitoring:** Review station health information and detected anomalies.
- **Weather Analytics:** Explore hourly, monthly, seasonal, and diurnal patterns.
- **Station Comparison:** Compare telemetry across multiple stations.
- **Anomaly Simulation:** Generate simulated anomalies to test detection behavior.
- **Model Testing & Benchmarking:** Evaluate custom sensor readings and run predefined benchmark scenarios.
- **Alert Management:** Review, update, and remediate alerts.
- **CSV Export:** Export weather telemetry for further analysis.
- **Interactive Dashboard:** Visualize station information, telemetry charts, comparisons, and anomaly results.

## 🧠 Detection Approach

SkyGuard AI uses a layered approach to assess the quality of weather sensor readings:

1. **Physical and Sensor Bounds:** Checks readings against configured physical and sensor limits.
2. **Temporal Change Detection:** Identifies unusual jumps and rates of change.
3. **Statistical Deviation:** Uses dynamic statistical deviation checks, including 3-sigma analysis.
4. **Meteorological Consistency:** Evaluates relationships between temperature, humidity, and related thermodynamic quantities.
5. **Machine Learning:** Uses Isolation Forest scoring when the required machine-learning dependencies are available.

The combined analysis helps identify suspicious observations while providing context for investigating potential sensor faults.

*Note: Detection results depend on the configured thresholds, available data, and model assumptions. Simulated or historical results should not be interpreted as verified live weather observations.*

## 🛠️ Technology Stack

**Frontend**
- React
- TypeScript
- Vite
- Tailwind CSS
- Lucide React

**Main Application Server**
- Node.js
- Express.js
- TypeScript

**Python Anomaly Detection API**
- Python
- FastAPI
- NumPy
- scikit-learn
- SciPy
- Pydantic
- Uvicorn

**Data**
- CSV-based weather dataset
- Configured weather-station metadata
- Sensor telemetry and anomaly analysis

## 📁 Project Structure

```text
SkyGuard-AI/
├── src/                    # React frontend and UI components
├── server/                 # Main anomaly detection engine
├── python_backend/         # Python FastAPI anomaly engine
│   ├── app.py
│   └── skyguard_engine.py
├── clean_weather_dataset.csv
├── index.html
├── metadata.json
├── package.json
├── package-lock.json
├── server.ts               # Express server and API routes
├── tsconfig.json
├── vite.config.ts
├── .env.example
└── README.md
```

## ⚙️ Installation and Setup

### Prerequisites

Install the following tools:

- [Node.js (LTS)](https://nodejs.org/)
- [Python](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads/)
- [Visual Studio Code](https://code.visualstudio.com/)

### 1. Clone the Repository

```bash
git clone https://github.com/khushee-15/SkyGuard-AI.git
cd SkyGuard-AI
```

### 2. Install JavaScript Dependencies

```bash
npm install
```

### 3. Start the Main Application

```bash
npm run dev
```

Open the following URL in your browser:

**http://localhost:3000**

Keep the terminal running while using the application.

## 🐍 Running the Python API (Optional)

The repository also contains a separate FastAPI anomaly detection service.

Open a second terminal from the project root.

### 1. Create a Virtual Environment

```bash
cd python_backend
python -m venv .venv
```

### 2. Activate the Environment

**Windows PowerShell:**

```powershell
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, use Command Prompt:

```bat
.venv\Scripts\activate.bat
```

### 3. Install Dependencies

```bash
python -m pip install fastapi "uvicorn[standard]" scikit-learn numpy scipy pydantic
```

### 4. Start the API

```bash
python -m uvicorn app:app --reload --port 8000
```

Access the interactive API documentation:

**http://localhost:8000/docs**

The main Express application and the Python API are separate services. Starting both does not automatically connect them; the relevant API integration must be configured where needed.

## 🔌 Main API Endpoints

The main application exposes endpoints for monitoring and analysis.

| Endpoint | Purpose |
|---|---|
| `GET /health` | Check application health |
| `GET /stations` | Retrieve configured stations |
| `GET /weather` | Retrieve weather telemetry |
| `GET /alerts` | Retrieve anomaly alerts |
| `GET /detect` | Evaluate a station sample |
| `GET /sensor-health` | Retrieve station health information |
| `GET /api/diurnal` | Retrieve diurnal analytics |
| `GET /api/seasonal` | Retrieve monthly analytics |
| `GET /api/compare` | Compare stations |
| `POST /simulate-anomaly` | Simulate a standard anomaly |
| `POST /api/test-model` | Evaluate custom sensor readings |
| `GET /api/test-benchmark` | Run benchmark scenarios |
| `GET /api/export-csv` | Export telemetry as CSV |

The main application API runs on port `3000` by default. The separate Python API runs on port `8000` when started using the instructions above.

## 🧪 Testing

You can explore the following capabilities after starting the relevant service:

- Inspect configured weather stations.
- Review available telemetry and analytics.
- Run anomaly simulations.
- Test custom sensor readings.
- Run predefined benchmark scenarios.
- Review alerts and station health.
- Export telemetry to CSV.

## 🎯 Project Objective

The goal of SkyGuard AI is to improve the reliability of automatic weather station data by detecting suspicious sensor readings and supporting systematic weather-data quality monitoring.

Reliable sensor data is important for weather analysis, environmental monitoring, forecasting workflows, and other applications that depend on accurate meteorological observations.

## 🔮 Future Scope

- Integrate verified live weather data sources.
- Improve anomaly detection using station-specific historical patterns.
- Add stronger alert explainability and sensor diagnostics.
- Deploy the dashboard and API services to a cloud platform.
- Add automated testing, monitoring, and model evaluation workflows.

## 👩‍💻 Author

**Khushi**

GitHub: [@khushee-15](https://github.com/khushee-15)

---

*SkyGuard AI — Building more reliable weather data through intelligent anomaly detection.*