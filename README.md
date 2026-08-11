<<<<<<< HEAD
# Student Mental Health Signal

A full-stack machine learning project that predicts a student's mental health signal based on digital habits, academic lifestyle, and stress indicators. The project combines a trained scikit-learn model, a FastAPI backend, and a responsive front-end dashboard for interactive prediction.

This project is intended for educational, research, and prototype use. It is not a clinical diagnosis tool and should not be used as a substitute for professional mental health assessment.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [How the Model Works](#how-the-model-works)
- [Dataset](#dataset)
- [Setup Instructions](#setup-instructions)
- [Run the Project Locally](#run-the-project-locally)
- [API Endpoints](#api-endpoints)
- [Example Request](#example-request)
- [Example Response](#example-response)
- [Notes and Considerations](#notes-and-considerations)
- [Future Improvements](#future-improvements)

## Overview

The application allows a user to fill in lifestyle and behavioral data such as:

- age
- gender
- country
- academic level
- social media platform usage
- purpose of use
- average daily screen time
- daily phone unlocks
- study hours
- physical activity hours
- sleep hours
- stress level

The system sends this information to a machine learning model and returns a predicted mental health score on a scale from 0 to 10.

The front-end interface is built with HTML, CSS, and JavaScript, while the backend is powered by FastAPI. The model is serialized as a pickle file and loaded at runtime.

## Features

- Interactive web form for student wellness input
- Real-time predicted mental health score from a trained ML model
- FastAPI backend with validation and prediction endpoint
- Responsive UI with a visual score gauge
- Support for common demographic and lifestyle inputs
- CORS-enabled backend for browser communication
- Light-weight deployment-friendly Python stack

## Project Structure

```text
machinelearning/
├── index.html              # Front-end UI
├── style.css               # Styling for the app
├── script.js               # Client-side form validation and API calls
├── main.py                 # FastAPI backend and prediction logic
├── requirements.txt        # Python dependencies
├── Mental_Health_Model.pkl # Trained ML model
├── Student Social Media And Mental Health Impact (1).csv
│                          # Dataset used for model development
├── Untitled0.ipynb         # Notebook for experimentation and analysis
├── .venv/                  # Virtual environment
├── README.md               # Project documentation
└── .gitignore              # Git ignore rules (if present)
```

## Technologies Used

### Frontend
- HTML5
- CSS3
- JavaScript

### Backend
- Python
- FastAPI
- Pydantic
- Uvicorn

### Machine Learning
- pandas
- scikit-learn
- joblib

## How the Model Works

The application loads a pre-trained model from `Mental_Health_Model.pkl` and passes user input as a single-row DataFrame.

Inside the backend:

1. The form data is validated using Pydantic models.
2. A new record is created in the structure expected by the model.
3. A `Grouped_country` feature is derived from the country field.
4. The model predicts a mental health score.
5. The value is rounded and returned to the frontend.

The model is designed as a prediction helper and uses behavioral features as indicators, not medical diagnoses.

## Dataset

The project includes a dataset named:

- `Student Social Media And Mental Health Impact (1).csv`

This dataset contains attributes related to student behavior, social media habits, health patterns, and academic lifestyle. These features are used for training and prediction. The exact original source is not documented in the project files, so the data should be treated as a demo or educational dataset unless you verify and cite its provenance.

## Setup Instructions

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd machinelearning
```

### 2. Create a Virtual Environment

On Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

On macOS/Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

This installs the required packages:

- fastapi
- uvicorn
- pydantic
- joblib
- pandas
- scikit-learn

## Run the Project Locally

### Start the Backend

From the project root, run:

```bash
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

The API will be available at:

```text
http://localhost:8000
```

### Start the Frontend

You can open the app by launching the HTML directly in a browser, or serve it locally with a simple static server.

Example:

```bash
python -m http.server 8080
```

Then open:

```text
http://localhost:8080
```

### Important Note for Local Frontend Use

The current frontend JavaScript points to a deployed Render API:

```javascript
const API_BASE = "https://mansik-santulan-score.onrender.com";
```

If you want to use the local backend instead, update this value in `script.js` to:

```javascript
const API_BASE = "http://localhost:8000";
```

## API Endpoints

### Root Endpoint

```http
GET /
```

Returns a welcome message.

### Prediction Endpoint

```http
POST /predict
```

Accepts JSON input matching the student data schema and returns a mental health score.

## Example Request

```json
{
  "age": 21,
  "gender": "Female",
  "country": "India",
  "academic_level": "Undergraduate",
  "most_used_platform": "Instagram",
  "purpose_of_use": "Education",
  "avg_daily_usage_hours": 5.5,
  "daily_unlocks": 70,
  "study_hours": 3.0,
  "physical_activity_hours": 1.5,
  "sleep_hours_per_night": 6.5,
  "stress_level": "Medium"
}
```

## Example Response

```json
{
  "predicted_mental_health_score": 6.77
}
```

## Notes and Considerations

- This is a demo project and not a medical or psychological assessment tool.
- The model is trained on a dataset that reflects student lifestyle patterns; real-world results can vary.
- The application should be treated as a learning project, proof of concept, or coursework demonstration.
- Data privacy and consent are important if this app is extended for real users.

## Future Improvements

Potential improvements for this project include:

- better data preprocessing and feature engineering
- more robust model evaluation and comparison
- explainability for predictions
- improved UI/UX and chart-based insights
- deployment to a production platform such as Render, Railway, Vercel, or Azure
- adding authentication and user-safe analytics
- storing prediction history for analysis

## License

This project does not currently include a formal license file. If you plan to publish it publicly on GitHub, consider adding one such as MIT or Apache 2.0.

## Acknowledgements

This project was built as an educational machine learning and web integration example for analyzing student wellbeing signals using lifestyle and digital habits.

If you want, I can also create:

1. a more polished GitHub README with badges and screenshots,
2. a LICENSE file,
3. a .gitignore file, or
4. a production-ready deployment version for Render/Azure.
=======
# mentalhealthsignal
It tell the mental health score by ml trained model.
>>>>>>> ccba2c25dc1377cfdf0892437c9f6c8e6dfc48db
