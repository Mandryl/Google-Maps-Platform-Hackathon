# Quistroll

## Overview

Quistroll is a service that brings a new function to Google Map which takes us to unfamiliar places in abroad.

In case you are sick of all-too-common travel, we highly recommend that you use Quistroll.

## Setup
Get some necessary information and set the environment variables by following the steps below.

### Google Map Platform

From the Google Cloud console, you can use the Google Maps Platform service.

You will need to create an API key that enables the Maps Javascript API for the frontend and another API key that enables the Places API and Directions API for the backend. ([link](https://developers.google.com/maps/documentation/javascript/get-api-key))

After creating the API keys, set the environment variables as follows.

```shell
export VUE_APP_GOOGLE_MAP_KEY = <your-maps-javascript-api-key>

```

### Express Server
The following environment variables should also be set for the backend server.

```shell
export VUE_APP_GOOGLE_MAP_KEY = <your-maps-javascript-api-key>

```

### dotenv

In addition, Debatter_bot uses [dotenv](https://github.com/motdotla/dotenv) library.

You can also set environment variables by adding a .env file directly under the project root folder.

## Deployment

Quistroll is built up with Node.js. When you deploy, you can use a free Node.js service such as [Glitch](https://glitch.com/) or set up your Node.js environment on a paid computing service.

To start up the program, simply execute the following command.

```shell
npm run build
npm start
```

## How to use
Turn on your location service on your smart phone, then open your browser and follow instructions.

Since a quiz is displayed on the upper side of your browser, so head to a place where a quiz indicates and click on submit button.

Quistroll has prepared a quiz on Tokyo as a sample.
(To add quizzes about other regions, please edit the json file.)

### Detail

1. In the first screen, the user scans the QR code and loads the quiz. (The QR code for the sample quiz is here.)

2. Point of departure and final destination is designated in each city. What you do is that head to final destination via some checkpoints.

3. After clicking on submit button, Quistroll judges your location is right or not based on your current location on GPS, Quistroll checks your location if it is right or not. 

4. If your submission is right, Quistroll shows next checkpoint's quiz, so go to the next destination. 

5.If your submission is wrong, some hints pop up depending on the number of times you submit wrong location. By the way, hints are displayed up to three times. Based on some hints, find a correct checkpoint.
