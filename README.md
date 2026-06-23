# SteerSense

SteerSense is a machine learning based driver safety prototype designed to detect driver stress and drowsiness using simulated physiological, motion, and camera-derived features.

The project focuses on building lightweight ML pipelines that can later be integrated into a real-time driver monitoring system. It includes mock data generation, feature engineering, model training, model comparison, and serialized model outputs for future deployment.

## Project Overview

Driver stress and drowsiness are two major factors that can reduce road safety. SteerSense analyzes sensor-style data and camera-derived behavioral indicators to classify whether a driver is stressed or drowsy.

The project contains two independent machine learning pipelines:

- Stress detection using physiological and accelerometer-based features
- Drowsiness detection using eye, mouth, and neck movement based features

## Key Features

- Generates realistic mock datasets for stress and drowsiness detection
- Trains multiple supervised machine learning models
- Compares model performance using accuracy and classification reports
- Performs feature engineering on accelerometer data
- Saves the best performing trained models using Joblib
- Stores label encoders for future prediction and deployment workflows

## Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- Joblib
- CSV

## Machine Learning Models

The project trains and compares the following ML algorithms:

- Random Forest Classifier
- Logistic Regression
- Support Vector Machine
- Gradient Boosting Classifier
- K-Nearest Neighbors

The best performing model is selected based on test accuracy and saved as a `.pkl` file.

## Project Structure

```text
steer-sense/
|-- mock_data_script.py              # Generates mock stress sensor data
|-- mock_cam_script.py               # Generates mock drowsiness camera-feature data
|-- model.py                         # Trains the stress detection model
|-- model_cam.py                     # Trains the drowsiness detection model
|-- realistic_stress_mock.csv        # Stress detection dataset
|-- realistic_drowsiness_mock.csv    # Drowsiness detection dataset
|-- stress_detector_model.pkl        # Saved stress detection model
|-- drowsiness_detector.pkl          # Saved drowsiness detection model
|-- label_encoder.pkl                # Label encoder for stress detection
|-- drowsiness_label_encoder.pkl     # Label encoder for drowsiness detection
`-- README.md
```

## Stress Detection

The stress detection pipeline uses physiological and motion-related features to classify driver stress levels.

### Input Features

- GSR
- BPM
- Body temperature
- Accelerometer X-axis
- Accelerometer Y-axis
- Accelerometer Z-axis
- Acceleration magnitude
- XY-axis acceleration standard deviation

### Output Labels

- `stressed`
- `not_stressed`

### Model File

```text
stress_detector_model.pkl
```

## Drowsiness Detection

The drowsiness detection pipeline uses camera-derived behavioral features to classify whether the driver is drowsy.

### Input Features

- Eye Aspect Ratio
- Mouth Opening Ratio
- Neck tilt

### Output Labels

- `drowsy`
- `not_drowsy`

### Model File

```text
drowsiness_detector.pkl
```

## Dataset Details

### Stress Dataset

File:

```text
realistic_stress_mock.csv
```

Columns:

| Column | Description |
| --- | --- |
| `timestamp` | Time of generated reading |
| `subject_id` | Simulated driver identifier |
| `gsr` | Galvanic Skin Response value |
| `bpm` | Heart rate |
| `temperature` | Body temperature |
| `accel_x` | X-axis acceleration |
| `accel_y` | Y-axis acceleration |
| `accel_z` | Z-axis acceleration |
| `label` | Stress classification label |

### Drowsiness Dataset

File:

```text
realistic_drowsiness_mock.csv
```

Columns:

| Column | Description |
| --- | --- |
| `timestamp` | Time of generated reading |
| `EAR` | Eye Aspect Ratio |
| `MOR` | Mouth Opening Ratio |
| `neck_tilt` | Neck tilt angle |
| `label` | Drowsiness classification label |

## Installation

Clone the repository:

```bash
git clone https://github.com/Divanshu710/steer-sense.git
cd steer-sense
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate the virtual environment on Windows:

```bash
.venv\Scripts\activate
```

Activate the virtual environment on macOS/Linux:

```bash
source .venv/bin/activate
```

Install dependencies:

```bash
pip install pandas numpy scikit-learn joblib
```

## Usage

Generate stress detection mock data:

```bash
python mock_data_script.py
```

Train the stress detection model:

```bash
python model.py
```

Generate drowsiness detection mock data:

```bash
python mock_cam_script.py
```

Train the drowsiness detection model:

```bash
python model_cam.py
```

## Model Training Workflow

```text
Mock data generation
|
CSV dataset creation
|
Feature selection and feature engineering
|
Label encoding
|
Train-test split
|
Model training
|
Model evaluation
|
Best model selection
|
Model serialization
```

## Output Files

After training, the project generates or updates the following files:

```text
stress_detector_model.pkl
label_encoder.pkl
drowsiness_detector.pkl
drowsiness_label_encoder.pkl
```

## Future Scope

- Integrate trained models with a real-time backend API
- Add live sensor data support from wearable or vehicle-mounted devices
- Use OpenCV or MediaPipe for real-time facial feature extraction
- Build a dashboard for driver state monitoring
- Add alert mechanisms for unsafe driver states
- Train and validate the models on larger real-world datasets

## Resume Description

**SteerSense - ML-Based Driver Stress and Drowsiness Detection System**

Developed a driver safety machine learning prototype to detect stress and drowsiness using physiological, motion, and camera-derived features. Built mock data generation scripts, engineered accelerometer-based features, trained and compared Random Forest, SVM, Logistic Regression, Gradient Boosting, and KNN classifiers, and serialized the best-performing models using Joblib for future real-time deployment.

## Author

Divanshu
