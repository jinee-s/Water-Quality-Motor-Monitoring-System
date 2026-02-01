# Water Quality Monitoring and Motor Control System

An intelligent IoT-based monitoring system that combines **water quality analysis** and **motor health monitoring** using Machine Learning and AI. The system provides real-time monitoring, predictive maintenance, and automatic shutdown capabilities to prevent equipment damage and ensure safe water quality.

## 🌟 Features

### Water Quality Monitoring
- **Real-time Water Quality Analysis**: Monitors pH, hardness, solids, chloramines, sulfate, conductivity, organic carbon, trihalomethanes, and turbidity
- **ML-based Potability Prediction**: Uses XGBoost classifier to predict water safety
- **Intelligent Alerts**: Threshold-based alerting for water quality parameters
- **AI-Powered Analysis**: Provides detailed insights using AI models

### Motor Health Monitoring
- **Multi-sensor Monitoring**: Tracks temperature, vibration, voltage, and noise levels
- **Predictive Maintenance**: AI-powered prediction of motor failures before they occur
- **Automatic Shutdown System**: Intelligently shuts down motors when critical conditions are detected
- **Anomaly Detection**: Identifies unusual patterns in motor behavior
- **Real-time Health Status**: Provides instant health assessment with confidence scores

### AI & Machine Learning Capabilities
- **Ensemble Learning**: Combines Random Forest and Neural Network models for better accuracy
- **Anomaly Detection**: Isolation Forest for detecting unusual behavior
- **Adaptive Learning**: Continuous improvement from historical data
- **Failure Probability Calculation**: Risk assessment and maintenance recommendations

## 🏗️ Architecture

The system consists of:
- **Flask Web Application**: Real-time dashboard with live metrics
- **AI Models**: Multiple ML models for predictions and anomaly detection
- **IoT Simulators**: Realistic sensor data generation for testing
- **Alert System**: Multi-level alert management (Warning, Critical)
- **Motor Control**: Automated shutdown with safety protocols

## 📋 Prerequisites

- Python 3.11 or higher
- pip (Python package manager)
- Git (for cloning the repository)

## 🚀 Installation

### Option 1: Local Installation

1. **Clone the repository**
```bash
git clone https://github.com/jinee-s/Water-Quality-Motor-Monitoring-System.git
cd Water-Quality-Motor-Monitoring-System
```

2. **Create a virtual environment** (recommended)
```bash
python -m venv venv

# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Run the application**
```bash
python app.py
```

5. **Access the dashboard**
Open your browser and navigate to: `http://localhost:5000`

### Option 2: Docker Installation

1. **Build the Docker image**
```bash
docker build -t water-motor-monitoring .
```

2. **Run the container**
```bash
docker run -p 7860:7860 water-motor-monitoring
```

3. **Access the application**
Open your browser and navigate to: `http://localhost:7860`

## 🎮 Usage

### Running the Dashboard

1. Start the Flask application:
```bash
python app.py
```

2. The web interface will be available at `http://localhost:5000`

### Using the IoT Simulator

**For Motor Monitoring:**
```bash
python iot_simulator.py
```

**For Water Quality Monitoring:**
```bash
python water_iot_simulator.py
```

**For Combined Demo (Windows):**
```bash
run_iot_demo.bat
```

### Features Available in Dashboard

- **Real-time Metrics**: Live sensor readings with visual indicators
- **ML Predictions**: AI-powered health and quality predictions
- **Alert Management**: View and manage system alerts
- **Motor Control**: Manual start/stop and auto-shutdown configuration
- **Historical Data**: Track trends and patterns over time
- **AI Insights**: Detailed analysis and recommendations

## 📊 System Parameters

### Motor Monitoring Thresholds

| Parameter | Warning | Critical | Shutdown |
|-----------|---------|----------|----------|
| Temperature | 70°C | 80°C | 90°C |
| Vibration | 4.5 mm/s | 6.0 mm/s | 8.0 mm/s |
| Voltage | 200-250V | 180-280V | <180V or >280V |
| Noise | 85 dB | 90 dB | 100 dB |

### Water Quality Parameters

| Parameter | Min Safe | Max Safe | Unit |
|-----------|----------|----------|------|
| pH | 6.5 | 8.5 | - |
| Hardness | - | 500 | mg/L |
| Sulfate | - | 500 | mg/L |
| Turbidity | - | 10 | NTU |

## 🧠 AI Models

The system uses advanced machine learning models:

### Motor Health Models
- **Random Forest Classifier**: 200 estimators with optimized hyperparameters
- **Multi-Layer Perceptron**: Neural network with 3 hidden layers (100, 50, 25 neurons)
- **Isolation Forest**: Anomaly detection with contamination factor 0.1
- **Ensemble Voting**: Combines multiple models for robust predictions

### Water Quality Models
- **XGBoost Classifier**: Gradient boosting for potability prediction
- **KNN Imputer**: Handles missing sensor data intelligently
- **Standard Scaler**: Normalizes features for better model performance

## 📁 Project Structure

```
Water-Quality-Motor-Monitoring-System/
├── app.py                      # Main Flask application
├── ai_models.py                # AI/ML model implementations
├── iot_simulator.py            # Motor IoT data simulator
├── water_iot_simulator.py      # Water quality data simulator
├── compare_logic.py            # Logic comparison utilities
├── requirements.txt            # Python dependencies
├── Dockerfile                  # Docker configuration
├── water_potability.csv        # Training dataset
├── run_iot_demo.bat           # Windows demo script
├── static/
│   └── style.css              # Dashboard styling
├── templates/
│   └── index.html             # Dashboard HTML
└── test files...              # Testing utilities
```

## 🔧 Configuration

### Alert Thresholds
Edit the `alert_thresholds` dictionary in `app.py`:

```python
alert_thresholds = {
    'temp_critical': 80,
    'temp_warning': 70,
    'vibration_critical': 6.0,
    'vibration_warning': 4.5,
    # ... customize as needed
}
```

### Auto-Shutdown Settings
Configure motor shutdown behavior in `motor_state`:

```python
motor_state = {
    'auto_shutdown_enabled': True,  # Enable/disable auto-shutdown
    # ... other settings
}
```

## 🧪 Testing

Run the test files to verify functionality:

```bash
# Test motor shutdown logic
python test_motor_shutdown.py

# Test fixed shutdown implementation
python demo_fixed_shutdown.py

# General system tests
python test_fix.py
```

## 🛠️ Technologies Used

- **Backend**: Flask, Python 3.11
- **Machine Learning**: scikit-learn, XGBoost, TensorFlow
- **Data Processing**: pandas, numpy
- **Frontend**: HTML5, CSS3, JavaScript
- **Deployment**: Docker, Gunicorn
- **AI Integration**: OpenAI, Google Generative AI

## 📈 Performance

- **Motor Health Prediction Accuracy**: ~95%
- **Water Quality Classification**: XGBoost-based prediction
- **Real-time Processing**: <100ms response time
- **Anomaly Detection**: 99% confidence threshold

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the MIT License.

## 👥 Authors

- **Jinee S** - [GitHub Profile](https://github.com/jinee-s)

## 🙏 Acknowledgments

- Water potability dataset for ML model training
- Flask framework for web application
- scikit-learn and XGBoost for machine learning capabilities
- Docker for containerization support

## 📧 Contact

For questions or support, please open an issue on the [GitHub repository](https://github.com/jinee-s/Water-Quality-Motor-Monitoring-System/issues).

## 🔮 Future Enhancements

- [ ] Mobile application for remote monitoring
- [ ] Cloud-based data storage and analytics
- [ ] Multi-motor management dashboard
- [ ] Advanced predictive maintenance algorithms
- [ ] Integration with industrial IoT platforms
- [ ] SMS/Email alert notifications
- [ ] Historical data visualization and reporting

---

**Made with ❤️ for Industrial IoT and Environmental Monitoring**
