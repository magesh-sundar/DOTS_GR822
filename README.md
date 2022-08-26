# Consensus of hourly visibility forecast for airports using NWP model and observations


![Current Version](https://img.shields.io/badge/version-v0.1-blue)
![GitHub contributors](https://img.shields.io/github/contributors/Narayanan5-code/SIH_2022)
![GitHub stars](https://img.shields.io/github/stars/Narayanan5-code/SIH_2022?style=social)
![GitHub forks](https://img.shields.io/github/forks/Narayanan5-code/SIH_2022?style=social)


Development of visibility forecast with elastic lead times using NWP model with DeepAR from past observation for the next 12/24 hours using DeepAR inside sagemaker studio and visualizing using AWS Quicksite with API service for clients for selected airports in the country.

This project aims to forecast the Visibility in the airports (or any parameter) against parameters like wind speed,wind direction,Humidity,Temperature,Dew point temperature.We have used Amazon Sagemaker as the environment for the project which has paved a way to make  our cloud based.

# Our Key Features 
* Cloud Based 
* Elastic lead times prection from 5 mins to one week 
* Decentralized system
* Multivarient Support 
* Multi Step predictions 
* Platform independant 
* Desktop and mobile support
* API Services 
* No code / Low code , orchestrated admin pannel 
* IOT support with API
* Simple Visuvalizations for the users 
* Fast predictions with AWS elastic services
* Real time data feed can be predicted dynamically 
* Extensive Database support for uploading real time data


## Table of Contents
- [Architecture](#Architecture)
	- [Dataset](#tools-required)
	- [Installation](#installation)
- [Development](#development)
    - [Part 1: Heading](#part-1-heading)
	  - [Step 1: Subheading](#step-1-subheading)
	  - [Step 2: Subheading](#step-2-subheading)
	- [Part 2: Heading](#part-2-heading)
- [Running the App](#running-the-app)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [Versioning](#versioning)
- [Authors](#authors)
- [License](#license)
- [Acknowledgments](#acknowledgments)

Open and view the Project using the `.zip` file provided or at my [GitHub Repository](https://github.com/Narayanan5-code/SIH_2022)

The project is also hosted [here](https://ap-south-1.quicksight.aws.amazon.com/sn/accounts/757776451407/dashboards/a647f449-e6c2-4fcc-b7cb-ad6f2e968665?directory_alias=airport-visibility-prediction )


## Architecture 

![Architecture](https://github.com/Narayanan5-code/DOTS_GR822/blob/main/src/images/system-arch.png)

## Modules

### 1. MODELS

#### A.) Autoregressive model (AR)
This project used AR model, which is Autoregressive model, is Autoregressive (AR) models are a subset of time series models, which can be used to predict future values based on previous observations. 
AR models use regression techniques and rely on autocorrelation in order to make accurate predictions.
Autoregressive model works best with data with short lead times

The performance of progressive predictions of timeseries predictions has been compared against vaerious models like cnnn, rnn ,lstm etc and has shown better accuracy.
#### B.) Sagemaker 
It provides an integrated Jupyter authoring notebook instance for easy access to your data sources for exploration and analysis.It also provides common machine learning algorithms that are optimized to run efficiently against extremely large data in a distributed environment. 
#### C.) SageMaker Studio
An integrated machine learning environment where you can build, train, deploy, and analyze your models all in the same application.

### 2 .API SERVICES

- We have centrailised model and output datafile available inside the `S3 Bucket` that can be query by calling the API endpoint created using `API GateWay`
- The Endpoint URL is connected to a `Lambda Function`,where we have added a custom **Layer** to perform data Processing using `Pandas` 

 ##### Using DateTime to fetcht the details like `visibility`,`wind speed`,`wind direction`,`humidity`,`dew point temperature` and `temperature` as `JSON`

- **URL** : https://7ytnzu57ti.execute-api.ap-south-1.amazonaws.com/prod/get-data

- **Authorization** : None 

- **request_body** : date_time

- **Connected Lambda Function** : `getData`

#### Results:

`{
    "statusCode": 200,
    "body": "{
    "time":"20201101 1400", 
    "Wind_speed":12.0,
    "Wind_dir":0,
    "Visibility":2500.0,
    "Temperature":22.0,
    "dewpoint":7.0,
    "Humidity":37.9247722383}"
}`


### 3. User Interface

Auto Regressor is a Multi Variant model that uses the output of
previous iterations as the input of the current iteration which results in
better accuracy.

The output from the Auto Regressor model is compared with the
observed value in order to check whether the nowcasted data is
accurate.

The Nowcasted visibility values are plotted against various factors like
temperature. time, dewpoint, and humidity which ensures that the user
understands the correlation between the various factors that
contribute to visibility.

The predicted data is visualised in the frontend for the user and the
data can be also passed using API Keys



## Authors

#### Lakshmi Narayanan R
* [GitHub](https://github.com/Narayanan5-code)
* [LinkedIn](https://www.linkedin.com/in/lakshmi-narayanan-r/)

#### Magesh Sundar G
* [GitHub](https://github.com/magesh-sundar)
* [LinkedIn](https://www.linkedin.com/in/mageshsundarg/)

#### Jaikrishna B
* [GitHub](https://github.com/jaikrish2402)
* [LinkedIn](https://www.linkedin.com/in/jaikrishna2402/)

#### Mukund R S
* [GitHub](https://github.com/mukund-9652)
* [LinkedIn](https://www.linkedin.com/in/mukundrs/)

#### Shri Harri Priya R
* [GitHub](https://github.com/rshriharripriya)
* [LinkedIn](https://www.linkedin.com/in/rshriharripriya/)

#### Manthra K S
* [GitHub](https://github.com/Manthra25)
* [LinkedIn](https://www.linkedin.com/in/manthra-k-s-6ab632205/)

## License

`Project Title` is open source software [licensed as MIT][license].

## Acknowledgments

* [AWS Sagemaker](https://github.com/aws/amazon-sagemaker-examples)
* [AWS QuickSight](https://docs.aws.amazon.com/quicksight/index.html)
* [DeepAR](https://docs.aws.amazon.com/sagemaker/latest/dg/deepar.html)
* [Tensorflow](https://www.tensorflow.org/learn)
