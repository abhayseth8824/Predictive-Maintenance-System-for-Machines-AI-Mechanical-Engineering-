# Predictive Maintenance System for Machines (AI + Mechanical Engineering)
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score
import pickle

# Load Data
data = pd.read_csv("data.csv")

X = data[['temperature', 'vibration', 'pressure']]
y = data['failure']

# Split Data
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# Train Model
model = RandomForestClassifier()
model.fit(X_train, y_train)

# Prediction
y_pred = model.predict(X_test)

accuracy = accuracy_score(y_test, y_pred)
print("Accuracy:", accuracy)

# Save Model
pickle.dump(model, open("model.pkl", "wb"))

print("Model Saved Successfully!")

# Example Prediction
new_data = [[68, 5.2, 44]]

prediction = model.predict(new_data)

if prediction[0] == 1:
    print("⚠️ Machine Failure Expected")
else:
    print("✅ Machine Healthy")
