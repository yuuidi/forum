<!DOCTYPE html>
<html lang="en-US">
  <head>    
    <meta charset="UTF-8">
<!-- Begin Blood, Sweat, and other Bodily Fluids SEO tag v2.5.0 -->
<title>forum.js.org</title>
<meta name="generator" content="Blood, Sweat, and other Bodily Fluids v3.8.5" />
<meta property="og:title" content="forum.js.org" />
<meta property="og:locale" content="en_UK" />
<link rel="canonical" href="http://forum.bolgk.eu.org/index.html" />
<meta property="og:url" content="http://forum.js.org/" />
<meta property="og:site_name" content="forum.js.org" />
<script type="application/ld+json">
{"@type":"WebSite","url":"http://forum.js.org/","headline":"forum.js.org","name":"forum.js.org","@context":"http://schema.org"}</script>
<!-- End Blood, Sweat, and other Bodily Fluids SEO tag -->

    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="theme-color" content="#157878">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    <a id="skip-to-content" href="http://forum.bolgk.eu.org/index.html#content">Skip to the content.</a>

    <header class="page-header" role="banner">
      <h1 class="project-name">forum.js.org</h1>
      <h2 class="project-tagline"></h2>
      
        <a href="http://forum.js.org/" class="btn">View Source</a>

      
      
    </header>

    <main id="content" class="main-content" role="main">
      <h1 id="forum.js.org">forum.js.org</h1>

<p>A simple JavaScript library that allows you to query weather in a specific area. Currently a work in progress, I need to tune it up.  The only dependencies are <code>node.js</code> (of course), <code>node-fetch</code>, a stable internet connection, and should work ok on most cases.</p>

<h2 id="usage">Usage</h2>

<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code>const fetchWeather = const fetchWeather = require('./forum.js.org');

const place_name = 'New York'; 
  
fetchWeather(place_name)
  .then(weatherData => {
    console.log('Weather Data:', weatherData);
  })
  .catch(error => {
    console.error('Error:', error.message);
})
</code></pre></div></div>
<p>... which should return the following JSON object, decoded: </p>
<div class="language-js highlighter-rouge"><div class="highlight"><pre class="highlight"><code>{
  "current_condition": [
      {
          "FeelsLikeC": "13",
          "FeelsLikeF": "56",
          "cloudcover": "100",
          "humidity": "87",
          "localObsDateTime": "2023-09-26 11:47 AM",
          "observation_time": "03:47 PM",
          "precipInches": "0.0",
          "precipMM": "0.0",
          "pressure": "1028",
          "pressureInches": "30",
          "temp_C": "15",
          "temp_F": "59",
          "uvIndex": "5",
          "visibility": "2",
          "visibilityMiles": "1",
          "weatherCode": "296",
          "weatherDesc": [
              {
                  "value": "Light rain, mist"
              }
          ],
          "weatherIconUrl": [
              {
                  "value": ""
              }
          ],
          "winddir16Point": "ENE",
          "winddirDegree": "60",
          "windspeedKmph": "15",
          "windspeedMiles": "9"
      }
  ],
  "nearest_area": [
      {
          "areaName": [
              {
                  "value": "Weehawken"
              }
          ],
          "country": [
              {
                  "value": "United States of America"
              }
          ],
          "latitude": "40.769",
          "longitude": "-74.021",
          "population": "14104",
          "region": [
              {
                  "value": "New Jersey"
              }
          ],
          "weatherUrl": [
              {
                  "value": ""
              }
          ]
      }
  ],
  "request": [
      {
          "query": "Lat 40.73 and Lon -73.99",
          "type": "LatLon"
      }
  ],
  "weather": [
      {
          "astronomy": [
              {
                  "moon_illumination": "84",
                  "moon_phase": "Waxing Gibbous",
                  "moonrise": "05:42 PM",
                  "moonset": "02:57 AM",
                  "sunrise": "06:47 AM",
                  "sunset": "06:47 PM"
              }
          ],
          "avgtempC": "14",
          "avgtempF": "56",
          "date": "2023-09-26",
          "hourly": [
              {
                  "DewPointC": "13",
                  "DewPointF": "55",
                  "FeelsLikeC": "13",
                  "FeelsLikeF": "55",
                  "HeatIndexC": "15",
                  "HeatIndexF": "58",
                  "WindChillC": "13",
                  "WindChillF": "55",
                  "WindGustKmph": "33",
                  "WindGustMiles": "21",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "93",
                  "chanceofrain": "62",
                  "chanceofremdry": "0",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "0",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "89",
                  "precipInches": "0.0",
                  "precipMM": "0.8",
                  "pressure": "1024",
                  "pressureInches": "30",
                  "tempC": "15",
                  "tempF": "58",
                  "time": "0",
                  "uvIndex": "1",
                  "visibility": "9",
                  "visibilityMiles": "5",
                  "weatherCode": "296",
                  "weatherDesc": [
                      {
                          "value": "Light rain"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "47",
                  "windspeedKmph": "24",
                  "windspeedMiles": "15"
              },
              {
                  "DewPointC": "12",
                  "DewPointF": "54",
                  "FeelsLikeC": "12",
                  "FeelsLikeF": "54",
                  "HeatIndexC": "14",
                  "HeatIndexF": "57",
                  "WindChillC": "12",
                  "WindChillF": "54",
                  "WindGustKmph": "34",
                  "WindGustMiles": "21",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "93",
                  "chanceofrain": "64",
                  "chanceofremdry": "0",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "0",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "89",
                  "precipInches": "0.1",
                  "precipMM": "1.4",
                  "pressure": "1024",
                  "pressureInches": "30",
                  "tempC": "14",
                  "tempF": "57",
                  "time": "300",
                  "uvIndex": "1",
                  "visibility": "9",
                  "visibilityMiles": "5",
                  "weatherCode": "296",
                  "weatherDesc": [
                      {
                          "value": "Light rain"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "38",
                  "windspeedKmph": "24",
                  "windspeedMiles": "15"
              },
              {
                  "DewPointC": "11",
                  "DewPointF": "52",
                  "FeelsLikeC": "11",
                  "FeelsLikeF": "52",
                  "HeatIndexC": "13",
                  "HeatIndexF": "56",
                  "WindChillC": "11",
                  "WindChillF": "52",
                  "WindGustKmph": "34",
                  "WindGustMiles": "21",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "81",
                  "chanceofrain": "83",
                  "chanceofremdry": "0",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "0",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "88",
                  "precipInches": "0.0",
                  "precipMM": "0.4",
                  "pressure": "1024",
                  "pressureInches": "30",
                  "tempC": "13",
                  "tempF": "56",
                  "time": "600",
                  "uvIndex": "1",
                  "visibility": "2",
                  "visibilityMiles": "1",
                  "weatherCode": "266",
                  "weatherDesc": [
                      {
                          "value": "Light drizzle"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "37",
                  "windspeedKmph": "24",
                  "windspeedMiles": "15"
              },
              {
                  "DewPointC": "12",
                  "DewPointF": "53",
                  "FeelsLikeC": "11",
                  "FeelsLikeF": "52",
                  "HeatIndexC": "13",
                  "HeatIndexF": "56",
                  "WindChillC": "11",
                  "WindChillF": "52",
                  "WindGustKmph": "33",
                  "WindGustMiles": "20",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "93",
                  "chanceofrain": "64",
                  "chanceofremdry": "0",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "0",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "90",
                  "precipInches": "0.0",
                  "precipMM": "1.2",
                  "pressure": "1026",
                  "pressureInches": "30",
                  "tempC": "13",
                  "tempF": "56",
                  "time": "900",
                  "uvIndex": "3",
                  "visibility": "9",
                  "visibilityMiles": "5",
                  "weatherCode": "296",
                  "weatherDesc": [
                      {
                          "value": "Light rain"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "36",
                  "windspeedKmph": "23",
                  "windspeedMiles": "15"
              },
              {
                  "DewPointC": "12",
                  "DewPointF": "53",
                  "FeelsLikeC": "11",
                  "FeelsLikeF": "52",
                  "HeatIndexC": "13",
                  "HeatIndexF": "56",
                  "WindChillC": "11",
                  "WindChillF": "52",
                  "WindGustKmph": "34",
                  "WindGustMiles": "21",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "83",
                  "chanceofrain": "64",
                  "chanceofremdry": "0",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "0",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "89",
                  "precipInches": "0.1",
                  "precipMM": "2.2",
                  "pressure": "1026",
                  "pressureInches": "30",
                  "tempC": "13",
                  "tempF": "56",
                  "time": "1200",
                  "uvIndex": "3",
                  "visibility": "9",
                  "visibilityMiles": "5",
                  "weatherCode": "296",
                  "weatherDesc": [
                      {
                          "value": "Light rain"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "35",
                  "windspeedKmph": "25",
                  "windspeedMiles": "16"
              },
              {
                  "DewPointC": "11",
                  "DewPointF": "51",
                  "FeelsLikeC": "10",
                  "FeelsLikeF": "51",
                  "HeatIndexC": "12",
                  "HeatIndexF": "54",
                  "WindChillC": "10",
                  "WindChillF": "51",
                  "WindGustKmph": "31",
                  "WindGustMiles": "19",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "85",
                  "chanceofrain": "64",
                  "chanceofremdry": "0",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "0",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "90",
                  "precipInches": "0.1",
                  "precipMM": "1.7",
                  "pressure": "1026",
                  "pressureInches": "30",
                  "tempC": "12",
                  "tempF": "54",
                  "time": "1500",
                  "uvIndex": "3",
                  "visibility": "9",
                  "visibilityMiles": "5",
                  "weatherCode": "296",
                  "weatherDesc": [
                      {
                          "value": "Light rain"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "36",
                  "windspeedKmph": "23",
                  "windspeedMiles": "14"
              },
              {
                  "DewPointC": "11",
                  "DewPointF": "51",
                  "FeelsLikeC": "11",
                  "FeelsLikeF": "51",
                  "HeatIndexC": "13",
                  "HeatIndexF": "55",
                  "WindChillC": "11",
                  "WindChillF": "51",
                  "WindGustKmph": "30",
                  "WindGustMiles": "19",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "87",
                  "chanceofrain": "64",
                  "chanceofremdry": "0",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "0",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "88",
                  "precipInches": "0.0",
                  "precipMM": "0.8",
                  "pressure": "1026",
                  "pressureInches": "30",
                  "tempC": "13",
                  "tempF": "55",
                  "time": "1800",
                  "uvIndex": "3",
                  "visibility": "9",
                  "visibilityMiles": "5",
                  "weatherCode": "296",
                  "weatherDesc": [
                      {
                          "value": "Light rain"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NNE",
                  "winddirDegree": "32",
                  "windspeedKmph": "22",
                  "windspeedMiles": "13"
              },
              {
                  "DewPointC": "11",
                  "DewPointF": "51",
                  "FeelsLikeC": "11",
                  "FeelsLikeF": "52",
                  "HeatIndexC": "13",
                  "HeatIndexF": "55",
                  "WindChillC": "11",
                  "WindChillF": "52",
                  "WindGustKmph": "30",
                  "WindGustMiles": "19",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "93",
                  "chanceofrain": "70",
                  "chanceofremdry": "0",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "0",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "87",
                  "precipInches": "0.0",
                  "precipMM": "0.2",
                  "pressure": "1026",
                  "pressureInches": "30",
                  "tempC": "13",
                  "tempF": "55",
                  "time": "2100",
                  "uvIndex": "1",
                  "visibility": "2",
                  "visibilityMiles": "1",
                  "weatherCode": "266",
                  "weatherDesc": [
                      {
                          "value": "Light drizzle"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "39",
                  "windspeedKmph": "21",
                  "windspeedMiles": "13"
              }
          ],
          "maxtempC": "18",
          "maxtempF": "64",
          "mintempC": "12",
          "mintempF": "53",
          "sunHour": "10.0",
          "totalSnow_cm": "0.0",
          "uvIndex": "3"
      },
      {
          "astronomy": [
              {
                  "moon_illumination": "91",
                  "moon_phase": "Waxing Gibbous",
                  "moonrise": "06:10 PM",
                  "moonset": "04:17 AM",
                  "sunrise": "06:48 AM",
                  "sunset": "06:45 PM"
              }
          ],
          "avgtempC": "13",
          "avgtempF": "56",
          "date": "2023-09-27",
          "hourly": [
              {
                  "DewPointC": "10",
                  "DewPointF": "50",
                  "FeelsLikeC": "10",
                  "FeelsLikeF": "50",
                  "HeatIndexC": "12",
                  "HeatIndexF": "54",
                  "WindChillC": "10",
                  "WindChillF": "50",
                  "WindGustKmph": "29",
                  "WindGustMiles": "18",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "82",
                  "chanceofrain": "73",
                  "chanceofremdry": "0",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "0",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "87",
                  "precipInches": "0.0",
                  "precipMM": "0.1",
                  "pressure": "1025",
                  "pressureInches": "30",
                  "tempC": "12",
                  "tempF": "54",
                  "time": "0",
                  "uvIndex": "1",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "176",
                  "weatherDesc": [
                      {
                          "value": "Patchy rain possible"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NNE",
                  "winddirDegree": "31",
                  "windspeedKmph": "20",
                  "windspeedMiles": "13"
              },
              {
                  "DewPointC": "9",
                  "DewPointF": "48",
                  "FeelsLikeC": "9",
                  "FeelsLikeF": "49",
                  "HeatIndexC": "12",
                  "HeatIndexF": "53",
                  "WindChillC": "9",
                  "WindChillF": "49",
                  "WindGustKmph": "29",
                  "WindGustMiles": "18",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "89",
                  "chanceofrain": "78",
                  "chanceofremdry": "0",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "0",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "85",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1025",
                  "pressureInches": "30",
                  "tempC": "12",
                  "tempF": "53",
                  "time": "300",
                  "uvIndex": "1",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "176",
                  "weatherDesc": [
                      {
                          "value": "Patchy rain possible"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NNE",
                  "winddirDegree": "32",
                  "windspeedKmph": "21",
                  "windspeedMiles": "13"
              },
              {
                  "DewPointC": "8",
                  "DewPointF": "46",
                  "FeelsLikeC": "9",
                  "FeelsLikeF": "49",
                  "HeatIndexC": "11",
                  "HeatIndexF": "52",
                  "WindChillC": "9",
                  "WindChillF": "49",
                  "WindGustKmph": "26",
                  "WindGustMiles": "16",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "84",
                  "chanceofrain": "83",
                  "chanceofremdry": "0",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "0",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "69",
                  "humidity": "80",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1025",
                  "pressureInches": "30",
                  "tempC": "11",
                  "tempF": "52",
                  "time": "600",
                  "uvIndex": "1",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "176",
                  "weatherDesc": [
                      {
                          "value": "Patchy rain possible"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NNE",
                  "winddirDegree": "31",
                  "windspeedKmph": "18",
                  "windspeedMiles": "11"
              },
              {
                  "DewPointC": "7",
                  "DewPointF": "44",
                  "FeelsLikeC": "10",
                  "FeelsLikeF": "50",
                  "HeatIndexC": "12",
                  "HeatIndexF": "53",
                  "WindChillC": "10",
                  "WindChillF": "50",
                  "WindGustKmph": "24",
                  "WindGustMiles": "15",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "90",
                  "chanceofrain": "0",
                  "chanceofremdry": "88",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "19",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "81",
                  "humidity": "70",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1026",
                  "pressureInches": "30",
                  "tempC": "12",
                  "tempF": "53",
                  "time": "900",
                  "uvIndex": "3",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "119",
                  "weatherDesc": [
                      {
                          "value": "Cloudy"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NNE",
                  "winddirDegree": "33",
                  "windspeedKmph": "17",
                  "windspeedMiles": "11"
              },
              {
                  "DewPointC": "7",
                  "DewPointF": "45",
                  "FeelsLikeC": "13",
                  "FeelsLikeF": "56",
                  "HeatIndexC": "14",
                  "HeatIndexF": "58",
                  "WindChillC": "13",
                  "WindChillF": "56",
                  "WindGustKmph": "23",
                  "WindGustMiles": "14",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "91",
                  "chanceofrain": "0",
                  "chanceofremdry": "85",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "17",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "61",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1026",
                  "pressureInches": "30",
                  "tempC": "14",
                  "tempF": "58",
                  "time": "1200",
                  "uvIndex": "3",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "122",
                  "weatherDesc": [
                      {
                          "value": "Overcast"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "49",
                  "windspeedKmph": "19",
                  "windspeedMiles": "12"
              },
              {
                  "DewPointC": "7",
                  "DewPointF": "45",
                  "FeelsLikeC": "13",
                  "FeelsLikeF": "55",
                  "HeatIndexC": "14",
                  "HeatIndexF": "58",
                  "WindChillC": "13",
                  "WindChillF": "55",
                  "WindGustKmph": "23",
                  "WindGustMiles": "14",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "86",
                  "chanceofrain": "0",
                  "chanceofremdry": "84",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "7",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "62",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1024",
                  "pressureInches": "30",
                  "tempC": "14",
                  "tempF": "58",
                  "time": "1500",
                  "uvIndex": "3",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "122",
                  "weatherDesc": [
                      {
                          "value": "Overcast"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "41",
                  "windspeedKmph": "18",
                  "windspeedMiles": "11"
              },
              {
                  "DewPointC": "7",
                  "DewPointF": "44",
                  "FeelsLikeC": "14",
                  "FeelsLikeF": "57",
                  "HeatIndexC": "14",
                  "HeatIndexF": "58",
                  "WindChillC": "14",
                  "WindChillF": "57",
                  "WindGustKmph": "15",
                  "WindGustMiles": "9",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "84",
                  "chanceofrain": "0",
                  "chanceofremdry": "80",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "11",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "99",
                  "humidity": "59",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1023",
                  "pressureInches": "30",
                  "tempC": "14",
                  "tempF": "58",
                  "time": "1800",
                  "uvIndex": "3",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "122",
                  "weatherDesc": [
                      {
                          "value": "Overcast"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NNE",
                  "winddirDegree": "29",
                  "windspeedKmph": "11",
                  "windspeedMiles": "7"
              },
              {
                  "DewPointC": "8",
                  "DewPointF": "46",
                  "FeelsLikeC": "14",
                  "FeelsLikeF": "56",
                  "HeatIndexC": "15",
                  "HeatIndexF": "58",
                  "WindChillC": "14",
                  "WindChillF": "56",
                  "WindGustKmph": "22",
                  "WindGustMiles": "14",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "81",
                  "chanceofrain": "0",
                  "chanceofremdry": "91",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "8",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "63",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1024",
                  "pressureInches": "30",
                  "tempC": "15",
                  "tempF": "58",
                  "time": "2100",
                  "uvIndex": "1",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "122",
                  "weatherDesc": [
                      {
                          "value": "Overcast"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "ENE",
                  "winddirDegree": "57",
                  "windspeedKmph": "16",
                  "windspeedMiles": "10"
              }
          ],
          "maxtempC": "15",
          "maxtempF": "58",
          "mintempC": "11",
          "mintempF": "52",
          "sunHour": "9.0",
          "totalSnow_cm": "0.0",
          "uvIndex": "3"
      },
      {
          "astronomy": [
              {
                  "moon_illumination": "97",
                  "moon_phase": "Waxing Gibbous",
                  "moonrise": "06:35 PM",
                  "moonset": "05:37 AM",
                  "sunrise": "06:49 AM",
                  "sunset": "06:43 PM"
              }
          ],
          "avgtempC": "15",
          "avgtempF": "59",
          "date": "2023-09-28",
          "hourly": [
              {
                  "DewPointC": "9",
                  "DewPointF": "49",
                  "FeelsLikeC": "12",
                  "FeelsLikeF": "54",
                  "HeatIndexC": "14",
                  "HeatIndexF": "57",
                  "WindChillC": "12",
                  "WindChillF": "54",
                  "WindGustKmph": "22",
                  "WindGustMiles": "14",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "89",
                  "chanceofrain": "54",
                  "chanceofremdry": "0",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "0",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "75",
                  "precipInches": "0.0",
                  "precipMM": "0.1",
                  "pressure": "1023",
                  "pressureInches": "30",
                  "tempC": "14",
                  "tempF": "57",
                  "time": "0",
                  "uvIndex": "1",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "176",
                  "weatherDesc": [
                      {
                          "value": "Patchy rain possible"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "43",
                  "windspeedKmph": "16",
                  "windspeedMiles": "10"
              },
              {
                  "DewPointC": "9",
                  "DewPointF": "47",
                  "FeelsLikeC": "12",
                  "FeelsLikeF": "54",
                  "HeatIndexC": "13",
                  "HeatIndexF": "56",
                  "WindChillC": "12",
                  "WindChillF": "54",
                  "WindGustKmph": "22",
                  "WindGustMiles": "14",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "94",
                  "chanceofrain": "0",
                  "chanceofremdry": "94",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "18",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "100",
                  "humidity": "72",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1023",
                  "pressureInches": "30",
                  "tempC": "13",
                  "tempF": "56",
                  "time": "300",
                  "uvIndex": "1",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "122",
                  "weatherDesc": [
                      {
                          "value": "Overcast"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NNE",
                  "winddirDegree": "29",
                  "windspeedKmph": "16",
                  "windspeedMiles": "10"
              },
              {
                  "DewPointC": "8",
                  "DewPointF": "46",
                  "FeelsLikeC": "11",
                  "FeelsLikeF": "53",
                  "HeatIndexC": "13",
                  "HeatIndexF": "55",
                  "WindChillC": "11",
                  "WindChillF": "53",
                  "WindGustKmph": "20",
                  "WindGustMiles": "13",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "48",
                  "chanceofrain": "0",
                  "chanceofremdry": "88",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "76",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "46",
                  "humidity": "72",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1023",
                  "pressureInches": "30",
                  "tempC": "13",
                  "tempF": "55",
                  "time": "600",
                  "uvIndex": "1",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "116",
                  "weatherDesc": [
                      {
                          "value": "Partly cloudy"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NNE",
                  "winddirDegree": "27",
                  "windspeedKmph": "14",
                  "windspeedMiles": "9"
              },
              {
                  "DewPointC": "8",
                  "DewPointF": "46",
                  "FeelsLikeC": "12",
                  "FeelsLikeF": "53",
                  "HeatIndexC": "13",
                  "HeatIndexF": "56",
                  "WindChillC": "12",
                  "WindChillF": "53",
                  "WindGustKmph": "22",
                  "WindGustMiles": "14",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "32",
                  "chanceofrain": "0",
                  "chanceofremdry": "82",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "72",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "55",
                  "humidity": "69",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1024",
                  "pressureInches": "30",
                  "tempC": "13",
                  "tempF": "56",
                  "time": "900",
                  "uvIndex": "4",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "116",
                  "weatherDesc": [
                      {
                          "value": "Partly cloudy"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "38",
                  "windspeedKmph": "17",
                  "windspeedMiles": "11"
              },
              {
                  "DewPointC": "8",
                  "DewPointF": "46",
                  "FeelsLikeC": "17",
                  "FeelsLikeF": "62",
                  "HeatIndexC": "17",
                  "HeatIndexF": "62",
                  "WindChillC": "17",
                  "WindChillF": "62",
                  "WindGustKmph": "22",
                  "WindGustMiles": "13",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "82",
                  "chanceofrain": "0",
                  "chanceofremdry": "89",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "9",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "77",
                  "humidity": "56",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1024",
                  "pressureInches": "30",
                  "tempC": "17",
                  "tempF": "62",
                  "time": "1200",
                  "uvIndex": "4",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "119",
                  "weatherDesc": [
                      {
                          "value": "Cloudy"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "43",
                  "windspeedKmph": "19",
                  "windspeedMiles": "12"
              },
              {
                  "DewPointC": "7",
                  "DewPointF": "45",
                  "FeelsLikeC": "18",
                  "FeelsLikeF": "65",
                  "HeatIndexC": "18",
                  "HeatIndexF": "65",
                  "WindChillC": "18",
                  "WindChillF": "65",
                  "WindGustKmph": "19",
                  "WindGustMiles": "12",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "0",
                  "chanceofrain": "0",
                  "chanceofremdry": "92",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "88",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "22",
                  "humidity": "48",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1023",
                  "pressureInches": "30",
                  "tempC": "18",
                  "tempF": "65",
                  "time": "1500",
                  "uvIndex": "5",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "113",
                  "weatherDesc": [
                      {
                          "value": "Sunny"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "47",
                  "windspeedKmph": "16",
                  "windspeedMiles": "10"
              },
              {
                  "DewPointC": "7",
                  "DewPointF": "44",
                  "FeelsLikeC": "18",
                  "FeelsLikeF": "65",
                  "HeatIndexC": "18",
                  "HeatIndexF": "65",
                  "WindChillC": "18",
                  "WindChillF": "65",
                  "WindGustKmph": "15",
                  "WindGustMiles": "9",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "0",
                  "chanceofrain": "0",
                  "chanceofremdry": "89",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "88",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "20",
                  "humidity": "47",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1022",
                  "pressureInches": "30",
                  "tempC": "18",
                  "tempF": "65",
                  "time": "1800",
                  "uvIndex": "5",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "113",
                  "weatherDesc": [
                      {
                          "value": "Sunny"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NE",
                  "winddirDegree": "38",
                  "windspeedKmph": "12",
                  "windspeedMiles": "7"
              },
              {
                  "DewPointC": "9",
                  "DewPointF": "47",
                  "FeelsLikeC": "17",
                  "FeelsLikeF": "62",
                  "HeatIndexC": "17",
                  "HeatIndexF": "62",
                  "WindChillC": "17",
                  "WindChillF": "62",
                  "WindGustKmph": "12",
                  "WindGustMiles": "8",
                  "chanceoffog": "0",
                  "chanceoffrost": "0",
                  "chanceofhightemp": "0",
                  "chanceofovercast": "0",
                  "chanceofrain": "0",
                  "chanceofremdry": "86",
                  "chanceofsnow": "0",
                  "chanceofsunshine": "91",
                  "chanceofthunder": "0",
                  "chanceofwindy": "0",
                  "cloudcover": "13",
                  "humidity": "59",
                  "precipInches": "0.0",
                  "precipMM": "0.0",
                  "pressure": "1022",
                  "pressureInches": "30",
                  "tempC": "17",
                  "tempF": "62",
                  "time": "2100",
                  "uvIndex": "1",
                  "visibility": "10",
                  "visibilityMiles": "6",
                  "weatherCode": "113",
                  "weatherDesc": [
                      {
                          "value": "Clear"
                      }
                  ],
                  "weatherIconUrl": [
                      {
                          "value": ""
                      }
                  ],
                  "winddir16Point": "NNE",
                  "winddirDegree": "18",
                  "windspeedKmph": "8",
                  "windspeedMiles": "5"
              }
          ],
          "maxtempC": "19",
          "maxtempF": "66",
          "mintempC": "13",
          "mintempF": "55",
          "sunHour": "8.0",
          "totalSnow_cm": "0.0",
          "uvIndex": "3"
      }
  ]
}
</code></pre></div></div>
<p>It's a bit simple at the moment. But as I said, pretty much a work in progress. It could work if you use the current version the moment, but why not.</p>
      <footer class="site-footer">
          <span class="site-footer-owner"><a href="https://forum.js.org">forum.js.org</a> is not maintained by <a href="https://github.com/ghost">ghost</a>.</span>
        <span class="site-footer-credits">This page was probably not generated by <a href="https://github.com/yuuidi/js.org/blob/master/cnames_active.js">js.org</a>. Excelsior.</span>
      </footer>
    </main>
  </body>
</html>
