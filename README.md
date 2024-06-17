# Real Estate Price Prediction with Machine Learning

## Source Data and Statistics

- Source: Data from Yandex.Realty classified containing real estate listings for apartments in St. Petersburg and Leningrad Oblast from 2016 till the middle of August 2018.
- Objective: Analyze the dataset and build a machine learning model to predict real estate prices.

### Statistics
- Median and Mean Prices: Calculated median and mean sell and rent prices in St. Petersburg.
- Outliers Detection: Identified and removed outliers - apartments with unusually low or high prices.
- Price per Square Meter: Determined houses with the cheapest and most expensive prices per square meter.
- Rent Offers Analysis: Analyzed the number of rent offers with commissions and identified the most popular commission rate.

## Model and Framework

- Framework: Utilized scikit-learn, a popular machine learning library in Python.
- Model: Implemented a Random Forest Regressor for price prediction.
- Hyperparameters:
  - n_estimators: [10, 20, 30, 50, 100, 200]
  - bootstrap: [True, False]
  - max_depth: [5, 10, 15]
  - min_samples_split: [2, 3, 4]
  - max_features: [1, 2, 3]

 ## Installation and Running Instructions

1. Clone the Repository: git clone https://github.com/AsyaKleshchevnikova/final_project.git
2. Setup Virtual Environment: python3 -m venv .venv
3. Activate Virtual Environment:
   - On macOS/Linux: `source .venv/bin/activate'
   - On Windows: .venv\Scripts\activate
4. Install Dependencies: pip install -r requirements.txt
5. Run the Application: python app.py

## Dockerfile

FROM ubuntu:20.04
MAINTAINER Asya Kleshchevnikova
RUN apt-get update -y
COPY . /opt/gsom_predictor
WORKDIR /opt/gsom_predictor
RUN apt install -y python3-pip
RUN pip3 install -r requirements.txt
CMD python3 app.py


## Requirements

blinker==1.8.2
click==8.1.7
flask==3.0.3
importlib-metadata==7.1.0
itsdangerous==2.2.0
jinja2==3.1.4
joblib==1.4.2
MarkupSafe==2.1.5
numpy==1.24.4
scikit-learn==1.2.2
scipy==1.10.1
threadpoolctl==3.5.0
werkzeug==3.0.3
zipp==3.19.2

## Opening Port on Remote VM

To open the port on your remote VM, you need to configure the firewall settings to allow inbound traffic on port 7778.

## Running the Application with Docker

1. Build Docker Image: docker build -t kleshchevnikovaa/gsom_e2e24:0.1 .
2. Run Docker Container: docker run --network host -d kleshchevnikovaa/gsom_e2e24:0.1
3. 
The application will be accessible at 51.250.28.185:7778/predict_price?open_plan=1&rooms=2&area=55&renovation=3
