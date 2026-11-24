# Predictive Maintenance System for Machines (AI + Mechanical Engineering)

A machine learning prototype that predicts mechanical equipment failure using sensor telemetry (`temperature`, `vibration`, and `pressure`) and a **Random Forest Classifier**, saving the trained model (`model.pkl`) for real-time inference.

---

## Setup & Usage

```bash
pip install pandas scikit-learn
python train_and_predict.py

Files: train_and_predict.py (training & inference script) · data.csv (sensor dataset) · model.pkl (saved model) · README.md
Datasheet (data.csv)
| Column | Type | Unit | Role | Mechanical Significance |
|---|---|---|---|---|
| temperature | float/int | °C | Feature | Friction, lubrication loss, or thermal overload |
| vibration | float/int | mm/s | Feature | Imbalance, misalignment, looseness, or bearing wear |
| pressure | float/int | bar/PSI | Feature | Hydraulic/pneumatic load, leaks, or blockages |
| failure | int (0/1) | Binary | Target | 0 = Healthy, 1 = Failure expected |
Sample data.csv: 55.0,2.1,35.0,0 (Healthy) · 74.5,6.4,48.2,1 (Failure) · 80/20 Train-Test Split (random_state=42)
Results
Accuracy: 0.95
Model Saved Successfully!
⚠️ Machine Failure Expected

 * Healthy Sample ([55.0, 2.1, 35.0]): Outputs 0 → ✅ Machine Healthy
 * Fault Sample ([68.0, 5.2, 44.0]): Outputs 1 → ⚠️ Machine Failure Expected
Future Scope
 * Remaining Useful Life (RUL): Predict remaining operating hours before failure using regression models.
 * Signal & Time-Series Features: Add rolling averages, rate-of-change trends, and FFT vibration spectra.
 * Live IoT & Alerting: Stream MQTT/OPC-UA sensor data to a FastAPI endpoint with a Grafana/Streamlit alert dashboard.
 * Advanced Evaluation: Track Precision, Recall, F1-score, class weights for imbalanced fault logs, and SHAP feature explainability.

