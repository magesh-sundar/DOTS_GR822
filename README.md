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
- 
Open and view the Project using the `.zip` file provided or at my [GitHub Repository](https://github.com/Narayanan5-code/SIH_2022)

The project is also hosted [here](https://ap-south-1.quicksight.aws.amazon.com/sn/accounts/757776451407/dashboards/a647f449-e6c2-4fcc-b7cb-ad6f2e968665?directory_alias=airport-visibility-prediction )


## Architecture 

!(/src/images/arch.png?raw=true)

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

<!-- ### Installation

All installation steps go here.

* Installing a particular tool
  * Steps to complete it
  
* Installing another tool -->


## Development

This section is completely optional. For big projects, the developement strategies are not discussed. But for small projects, you can give some insight to people. It has 2 benefits in my opinion:

1. It's a way to give back to the community. People get to learn from you and appreciate your work
2. You can refer the README in future as a quick refresher before an interview or for an old project to check if it can help you in your currect work

### Part 1: Heading
Input:
1. Model simulated Temperature, Wind Speed, Wind Direction, Humidity
2. Observed visibility data (Met report) from selected Airport 

Output:
1. Hourly visibility product for 12/24 hours(or for any lead time)
2. Format: Visibility in meters 
3. Platform: This project is platform independent.

#### Step 1: Subheading

* Mention the steps here
  * You can also have nested steps to break a step into small tasks
  
#### Step 2: Subheading

* Mention the steps here.
  * You can also have nested steps to break a step into small tasks

For details now how everything has been implemented, refer the source code

### Part 2: Heading

* Mention the steps here

## Running the App

Steps and commands for running the app are to be included here

* Example steps:
  ```
    Example command
  ```

## Deployment

This section is completely optional. Add additional notes about how to deploy this on a live system

## Contributing

Mention what you expect from the people who want to contribute

We'd love to have your helping hand on `Project Title`! See [CONTRIBUTING.md] for more information on what we're looking for and how to get started.

## Versioning

If your project has multiple versions, include information about it here. 

For the available versions, see the [tags on this repository][tags]

## Authors

#### Lakshmi Narayanan R
* [GitHub](https://github.com/Narayanan5-code)
* [LinkedIn]

#### Magesh Sundar G
* [GitHub]()
* [LinkedIn]

#### Jaikrishna B
* [GitHub]
* [LinkedIn]

#### Mukund R S
* [GitHub]
* [LinkedIn]

#### Shri Harri Priya R
* [GitHub]
* [LinkedIn]

#### Manthra K S
* [GitHub]
* [LinkedIn]

You can also see the complete [list of contributors][contributors] who participated in this project.

## License

`Project Title` is open source software [licensed as MIT][license].


## Acknowledgments

This section can also be called as `Resources` or `References`

* Code Honor if someone's work was referred to
* Tutorials followed
* Articles that helped
* Inspiration
* etc

[//]: # (HyperLinks)

[GitHub Repository]: https://github.com/madhur-taneja/README-Template
[GitHub Pages]: https://madhur-taneja.github.io/README-Template
[CONTRIBUTING.md]: https://github.com/madhur-taneja/README-template/blob/master/CONTRIBUTING.md
[tags]: https://github.com/madhur-taneja/README-template/tags

[GitHub]: https://github.com/madhur-taneja
[LinkedIn]: https://www.linkedin.com/in/madhur-taneja/

[contributors]: https://github.com/madhur-taneja/README-template/contributors
[license]: https://github.com/madhur-taneja/README-template/blob/master/LICENSE.md
