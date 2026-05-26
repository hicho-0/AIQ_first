# Indoor Air Quality (IAQ) Analysis & Prediction

A comprehensive data science project for monitoring, analyzing, and predicting indoor air quality using advanced machine learning techniques, including Graph Neural Networks (GNNs) and regression analysis.

## 📋 Project Overview

This project analyzes air quality measurements from indoor sensors across different environments (laboratory and residential settings). It leverages sensor networks represented as graphs and applies various machine learning models to predict air quality metrics and detect anomalies.

### Key Features
- **Sensor Network Analysis**: Graph-based representation of sensor relationships
- **Air Quality Prediction**: Regression models for multi-variable forecasting
- **Graph Neural Networks**: Implementation of GCN, GIN, and GraphSAT architectures
- **Knowledge Representation**: Ontology-based semantic modeling of IAQ concepts
- **Interactive Dashboard**: HTML-based visualization of air quality metrics

## 📊 Dataset

The project uses air quality measurements including:

### Environmental Measurements
- **Particulate Matter**: PM1, PM2.5, PM10, particle counts (cnt0.3, cnt0.5, cnt1, cnt2.5, cnt5, cnt10)
- **Gases**: CO, CO₂, NO₂, SO₂, O₃
- **Volatile Compounds**: TVOC (Total Volatile Organic Compounds)
- **Climate Data**: Temperature, humidity (relative & absolute), dew point, pressure
- **Acoustic Data**: Sound levels (current & max)

### Derived Metrics
- **Health Index**: Indicator of indoor air safety (0-1000 normal, -200 gas alarm, -800 fire alarm)
- **Performance Index**: Overall environmental performance indicator
- **Measurement Rate**: Cycle time in milliseconds

### Data Sources
- `laboratory.csv`: Professional laboratory environment measurements
- `one_room_apartement.csv`: Residential apartment measurements
- `DataDescription.txt`: Detailed variable definitions and anomalies

### Known Anomalies
- **09 July 2023**: Measurement error in fine dust values due to humidity spike
- **17 April 2023**: Lab power outage (possible short circuit)
- **21 May 2023**: Large fire in Herzogenrath (9-10 km away) affected readings

## 🏗️ Project Structure

```
.
├── data/                          # Dataset files
│   ├── laboratory.csv            # Lab measurements
│   ├── one_room_apartement.csv   # Residential measurements
│   └── DataDescription.txt       # Variable definitions
│
├── notebooks/                     # Jupyter analysis notebooks
│   ├── Air_Quality_Regression_Metrics.ipynb
│   ├── GNN_Sensor_Graph_Visualization.ipynb
│   ├── indoor_pollution_graph_pipeline.ipynb
│   ├── ontology_v2_builder.ipynb
│   └── outputs/                  # Notebook-generated outputs
│       ├── figures/
│       ├── graphs/
│       └── models/
│
├── ontology/                      # Semantic knowledge representation
│   └── iaq_ontology_v2.ttl       # RDF/OWL ontology for IAQ concepts
│
├── outputs/                       # Project outputs
│   ├── figures/                  # Generated visualizations
│   ├── graphs/                   # Network graphs
│   │   ├── clean_graph.graphml
│   │   ├── fire_graph.graphml
│   │   └── sample_graph.graphml
│   └── models/                   # Trained neural networks
│       ├── gcn_best.pt          # Graph Convolutional Network
│       ├── gin_best.pt          # Graph Isomorphism Network
│       └── graphsat_best.pt     # GraphSAT model
│
├── dashboard.html                 # Interactive visualization dashboard
└── README.md                      # This file
```

## 🔬 Methodology

### Graph Neural Networks
Three different GNN architectures are trained and evaluated:
- **GCN** (Graph Convolutional Network): Direct sensor relationships
- **GIN** (Graph Isomorphism Network): Enhanced expressiveness for complex sensor patterns
- **GraphSAT**: State-of-the-art graph architecture

### Regression Analysis
Predicts air quality metrics using historical sensor data and environmental variables.

### Ontology
RDF/OWL-based semantic representation enabling:
- Knowledge querying and reasoning
- Relationship mapping between air quality factors
- Inference of unobserved metrics

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Jupyter Notebook
- PyTorch
- RDFlib (for ontology processing)
- Pandas, NumPy, Scikit-learn

### Running the Analysis

1. **Explore the Data**
   ```bash
   jupyter notebook notebooks/
   ```

2. **Train GNN Models**
   - Run `notebooks/GNN_Sensor_Graph_Visualization.ipynb`
   - Run `notebooks/indoor_pollution_graph_pipeline.ipynb`

3. **Analyze Regression Metrics**
   - Run `notebooks/Air_Quality_Regression_Metrics.ipynb`

4. **View Results**
   - Open `dashboard.html` in a web browser for interactive visualization
   - Check `outputs/figures/` for static plots
   - Inspect trained models in `outputs/models/`

## 📈 Notebooks

| Notebook | Purpose |
|----------|---------|
| **Air_Quality_Regression_Metrics.ipynb** | Evaluate regression model performance and metrics |
| **GNN_Sensor_Graph_Visualization.ipynb** | Visualize sensor networks and GNN architectures |
| **indoor_pollution_graph_pipeline.ipynb** | Complete pipeline for graph-based pollution analysis |
| **ontology_v2_builder.ipynb** | Build and validate IAQ knowledge graph |

## 📊 Key Outputs

- **Trained Models**: Best-performing GCN, GIN, and GraphSAT models
- **Network Graphs**: GraphML files representing sensor relationships
- **Visualizations**: Figures and plots saved in `outputs/figures/`
- **Dashboard**: Interactive HTML interface for exploring results

## 🔗 Knowledge Representation

The `iaq_ontology_v2.ttl` file contains:
- Sensor and measurement definitions
- Air quality factor relationships
- Health and performance index semantics
- Inference rules for IAQ assessment

## 📝 Applications

- Indoor air quality monitoring and alerts
- Predictive maintenance for HVAC systems
- Health impact assessment
- Environmental anomaly detection
- Sensor network optimization

## ⚠️ Data Quality Considerations

- Anomalies in historical data (see DataDescription.txt)
- Missing values in specific time periods
- Environmental events (fire, power outage) may affect readings
- Humidity-related measurement errors in certain conditions

## 🤝 Contributing

For improvements or bug reports, please review the data anomalies section and retrain models with cleaned data as needed.

## 📄 License

[Specify your project license]

## 📧 Contact

[Add your contact information if applicable]

---

**Last Updated**: May 2026

**Status**: Active Development
