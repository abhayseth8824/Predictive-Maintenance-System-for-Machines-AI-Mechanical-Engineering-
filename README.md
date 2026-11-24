🔧 Predictive Maintenance System for Machines (AI + Mechanical Engineering)

📌 Overview

The Predictive Maintenance System is a Machine Learning-based project designed to predict potential machine failures by analyzing key operational parameters such as temperature, vibration, and pressure.

Instead of waiting for a machine to break down or performing maintenance at fixed intervals, this system uses sensor data and a trained Machine Learning model to identify potential failures in advance. This can help reduce downtime, improve operational efficiency, and support smarter maintenance decisions.

---

🎯 Objectives

- Predict machine failure using Machine Learning.
- Monitor important mechanical parameters such as temperature, vibration, and pressure.
- Identify whether a machine is healthy or likely to fail.
- Reduce unexpected breakdowns and maintenance costs.
- Integrate AI with mechanical and industrial monitoring systems.

---

⚙️ Technologies Used

- Python – Programming language
- Pandas – Data processing and manipulation
- Scikit-learn – Machine Learning model training and prediction
- Random Forest Classifier – Failure prediction algorithm
- Pickle – Model serialization and saving

---

📊 Input Parameters

The model uses three input features:

Parameter| Description
Temperature| Machine operating temperature
Vibration| Vibration level of the machine
Pressure| Operating pressure of the machine

Output

Prediction| Status
"0"| ✅ Machine Healthy
"1"| ⚠️ Machine Failure Expected

---

🧠 Machine Learning Workflow

1. Load the dataset using Pandas.
2. Select temperature, vibration, and pressure as input features.
3. Select the failure column as the target variable.
4. Split the dataset into training and testing data.
5. Train a Random Forest Classifier.
6. Evaluate model performance using accuracy.
7. Save the trained model as "model.pkl".
8. Predict machine condition using new sensor readings.

---

📁 Project Structure

Predictive-Maintenance-System/
│
├── data.csv             # Dataset
├── main.py              # ML training and prediction code
├── model.pkl            # Saved trained model
├── requirements.txt      # Python dependencies
└── README.md            # Project documentation

---

🚀 Installation & Setup

1. Clone the Repository

git clone https://github.com/your-username/Predictive-Maintenance-System.git

2. Navigate to the Project Directory

cd Predictive-Maintenance-System

3. Install Dependencies

pip install -r requirements.txt

---

▶️ How to Run

Execute the Python program:

python main.py

The program will train the Random Forest model, evaluate its accuracy, save the trained model, and predict the condition of the machine using sample sensor data.

---

🔍 Example Prediction

Sample Input

new_data = [[68, 5.2, 44]]

Temperature| Vibration| Pressure
68| 5.2| 44

Predicted Output

✅ Machine Healthy

Note: The actual output depends on the trained model and the dataset.

---

📈 Model Evaluation

The model is evaluated using Accuracy Score, which measures the percentage of correct predictions on the test dataset.

accuracy = accuracy_score(y_test, y_pred)

---

💾 Model Saving

The trained Machine Learning model is saved using Pickle:

pickle.dump(model, open("model.pkl", "wb"))

This allows the model to be loaded and used later without retraining.

---

🔮 Future Improvements

- Real-time sensor monitoring using ESP32 or Arduino.
- Integration of vibration, temperature, and pressure sensors.
- IoT-based data transmission using MQTT or Wi-Fi.
- Live monitoring dashboard using Streamlit.
- Failure probability and anomaly detection.
- Email or mobile notifications for abnormal machine conditions.
- Integration with industrial automation and PLC systems.
- Predictive maintenance using time-series sensor data.
