# Flight Delay Prediction

This project explores the prediction of flight arrival times into Syracuse (SYR) from major airports including Chicago (ORD), New York (JFK), and Orlando (MCO). Using non-neural network models, this project aims to predict whether flights will arrive early, on time, or delayed based on historical data and earlier flights on the same day. The project leverages regression and classification techniques and integrates real-time flight status data along with weather conditions to enhance predictive accuracy.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Data Sources](#data-sources)
- [Usage](#usage)
- [Methodology](#methodology)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Contributing](#contributing)

## Introduction

The aviation industry consistently seeks improvements in operational efficiency and passenger satisfaction, and one critical aspect is the accurate prediction of flight arrival times. This project focuses on predicting flight delays using statistical models. The aim is to provide insights that can enhance airport resource management, improve airline on-time performance, and reduce passenger uncertainty.

### Research Goals:
- Predict flight arrival statuses (early, on time, delayed) based on earlier flights of the same day.
- Analyze the correlation between flight statuses and weather conditions.
- Employ regression and classification methods to predict flight delays.

## Features

- **Flight Delay Prediction:** Predict the arrival status of flights based on previous flights and weather data.
- **Regression and Classification Models:** Use regression and classification techniques to predict flight outcomes.
- **Weather Data Integration:** Incorporates weather conditions such as temperature, precipitation, wind speed, and visibility for more accurate predictions.
- **Real-Time Updates:** Works with real-time flight status updates for accurate and timely predictions.

## Installation

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/yourusername/flight-delay-prediction.git
   cd flight-delay-prediction
   ```

2. Install the required dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Make sure to set up any required APIs for fetching real-time flight data and weather updates.

## Data Sources

- **Flight Data**: Sourced from the [Bureau of Transportation Statistics](https://www.transtats.bts.gov/ontime/), specifically for flights arriving at or departing from the relevant airports.
- **Weather Data**: Historical weather data is obtained from [Visual Crossing Weather](https://www.visualcrossing.com/) for the relevant timeframes and locations (ORD, JFK, MCO).

## Usage

The model predicts whether a flight will arrive early, on time, or delayed based on input data, including previous flight statuses and weather conditions.

### Example: Predicting a Flight Delay

```python
from flight_delay_model import predict_delay

# Example flight data for prediction
flight_info = {
    'flight_number': 'AA3402',
    'departure_airport': 'ORD',
    'scheduled_arrival_time': '2024-09-15 12:30:00',
    'previous_flight_status': 'on-time',
    'weather_data': {'temperature': 75, 'wind_speed': 10, 'precipitation': 0}
}

status = predict_delay(flight_info)
print(f"Predicted Status: {status}")
```

### Exploratory Data Analysis

EDA was conducted to analyze meteorological factors such as temperature, dew point, precipitation, snow, wind speed, cloud cover, and visibility. Insights were drawn regarding how these factors affect flight schedules, with a particular focus on peak delays.

#### Key EDA Insights:
- **Temperature Variations:** The dataset includes a wide range of temperatures, potentially affecting flight operations, especially during extreme conditions.
- **Precipitation Impact:** Heavy precipitation was observed to correlate with significant delays.
- **Visibility Issues:** Low visibility caused by weather conditions, such as fog, can lead to delayed or canceled flights.

## Methodology

The project leverages both regression and classification methods to predict flight delays:

- **Regression Analysis**: Used to estimate how various independent variables (like weather data and earlier flight statuses) influence the dependent variable (flight delay).
- **Classification**: Categorizes flights into 'early', 'on-time', or 'delayed' classes.

Flight data is preprocessed to ensure high-quality input to the predictive models, with features such as:
- **Datetime parsing**: Accurate handling of temporal data.
- **Flight status categorization**: Flight statuses are categorized based on scheduled vs. actual arrival times.
- **Weather data merging**: Flight data is synchronized with weather conditions at the time of departure.

## Contributing

Contributions are welcome! If you'd like to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Create a new Pull Request.


---
