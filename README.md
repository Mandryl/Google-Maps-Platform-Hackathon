# Quistroll

## Overview

Quistroll is a service that brings a new function to Google Map which takes us to unfamiliar places in abroad.

In case you are sick of all-too-common travel, we highly recommend that you use Quistroll.

[![](https://img.youtube.com/vi/Zf3ldja1VyM/0.jpg)](https://www.youtube.com/watch?v=Zf3ldja1VyM)

## Setup
Get some necessary information and set the environment variables by following the steps below.

### Google Map Platform

From the Google Cloud console, you can use the Google Maps Platform service.

You will need to create an API key that enables [Maps Javascript API](https://developers.google.com/maps/documentation/javascript/overview) for the frontend and another API key that enables [Places API](https://developers.google.com/maps/documentation/places/web-service) and [Directions API](https://developers.google.com/maps/documentation/directions/overview) for the backend. ([link](https://developers.google.com/maps/documentation/javascript/get-api-key))

After creating the API keys, set the environment variables as follows.

```shell
export VUE_APP_GOOGLE_MAP_KEY = <FrontEnd API-KEY>
export BACK_GOOGLE_MAP_KEY = <BackEnd API-KEY>
```

### Express Server
The following environment variables should also be set for the backend server.

```shell
export PORT = <Listen Port of Express Server (Default is "3000")>
export LOG_LEVEL = <Log Level of Logger (Default is "info")>
export BASIC_ID = <User ID of Basic Authentication>
export BASIC_PASS = <Password of Basic Authentication>
```

### dotenv

In addition, Quistroll uses [dotenv](https://github.com/motdotla/dotenv) library.

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
(To add quizzes about other regions, please edit the [json](https://github.com/Mandryl/Google-Maps-Platform-Hackathon/blob/main/server/db/initialData/quiz.json) file.)

### Detail

1. In the first screen, the user scans the QR code and loads the quiz. (The QR code for the sample quiz is [here](https://github.com/Mandryl/Google-Maps-Platform-Hackathon/blob/main/artifact/image/tokyo/Qrcode_Tokyo.jpg).)

2. Point of departure and final destination is designated in each city. What you do is that head to final destination via some checkpoints.

3. After clicking on submit button, Quistroll judges your location is right or not based on your current location on GPS, Quistroll checks your location if it is right or not. 

4. If your submission is right, Quistroll shows next checkpoint's quiz, so go to the next destination. 

5. If your submission is wrong, some hints pop up depending on the number of times you submit wrong location. By the way, hints are displayed up to three times. Based on some hints, find a correct checkpoint.
- If you submit a wrong place once, images of the check point posted by Google Map users will be displayed as a hint.

- If you submit a wrong place twice, a review of the check point posted by a Google Map user will be displayed as a hint.

- If you submit a wrong place three times, a nearby place of the check point will be displayed as a hint.
