# Rain Prediction

This repository contains a machine learning project aimed at predicting rainfall in Australia using historical weather data. The project leverages a TensorFlow model and label encoders to preprocess categorical data.

## Repository Structure

- **`rain_prediction.ipynb`**: Jupyter Notebook detailing data preprocessing, model training, and evaluation processes.
- **`weatherAUS.csv`**: Dataset containing approximately 10 years of daily weather observations from various locations across Australia, including 145,460 records and 23 attributes. citeturn0search3
- **`model.keras`**: Saved TensorFlow model in Keras format.
- **`encoders.pkl`**: Pickle file storing the label encoders used for categorical data preprocessing.

## Dataset Features

The `weatherAUS.csv` dataset includes the following columns:

1. **Location**: Categorical feature indicating the weather station's location.
2. **MinTemp**: Minimum temperature in degrees Celsius.
3. **MaxTemp**: Maximum temperature in degrees Celsius.
4. **Rainfall**: Amount of rainfall recorded for the day in millimeters.
5. **Evaporation**: Evaporation in millimeters.
6. **Sunshine**: Number of hours of bright sunshine.
7. **WindGustDir**: Direction of the strongest wind gust.
8. **WindGustSpeed**: Speed of the strongest wind gust in km/h.
9. **WindDir9am**: Wind direction at 9 AM.
10. **WindDir3pm**: Wind direction at 3 PM.
11. **WindSpeed9am**: Wind speed at 9 AM in km/h.
12. **WindSpeed3pm**: Wind speed at 3 PM in km/h.
13. **Humidity9am**: Humidity at 9 AM as a percentage.
14. **Humidity3pm**: Humidity at 3 PM as a percentage.
15. **Pressure9am**: Atmospheric pressure at 9 AM in hPa.
16. **Pressure3pm**: Atmospheric pressure at 3 PM in hPa.
17. **Cloud9am**: Cloud cover at 9 AM (measured in oktas).
18. **Cloud3pm**: Cloud cover at 3 PM (measured in oktas).
19. **Temp9am**: Temperature at 9 AM in degrees Celsius.
20. **Temp3pm**: Temperature at 3 PM in degrees Celsius.
21. **RainToday**: Binary indicator (Yes/No) if rainfall was recorded today.
22. **Year**: Year of observation.
23. **Month**: Month of observation.
24. **Day**: Day of observation.

## Data Preprocessing

Categorical features such as `Location`, `WindGustDir`, `WindDir9am`, `WindDir3pm`, and `RainToday` were encoded using label encoders to convert them into numerical format suitable for model training. These encoders are stored in the `encoders.pkl` file.

## Model Training

A TensorFlow neural network was trained using the preprocessed features to predict the likelihood of rainfall the next day (`RainTomorrow`). The model's architecture and training process are detailed in the `rain_prediction.ipynb` notebook.

## Usage

To replicate or build upon this project, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/pq36/Rain_prediction.git
   ```
2. **Navigate to the Project Directory**:
   ```bash
   cd Rain_prediction
   ```
3. **Install Dependencies**:
   Ensure you have Python installed. Install the required packages using:
   ```bash
   pip install -r requirements.txt
   ```
   *Note: The `requirements.txt` file should list all necessary packages. If it's missing, refer to the imports in `rain_prediction.ipynb` to identify required libraries.*

4. **Open the Jupyter Notebook**:
   Launch Jupyter Notebook and open `rain_prediction.ipynb` to explore the data analysis and model development steps:
   ```bash
   jupyter notebook rain_prediction.ipynb
   ```

## Saved Models and Encoders

- **`model.keras`**: Contains the trained TensorFlow model. Load it using:
  ```python
  from tensorflow.keras.models import load_model
  model = load_model('model.keras')
  ```
- **`encoders.pkl`**: Stores the label encoders for categorical features. Load them with:
  ```python
  import pickle
  with open('encoders.pkl', 'rb') as file:
      encoders = pickle.load(file)
  ```
