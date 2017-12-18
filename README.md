### Technical Test

Produce a console app to query weather data, in .NET to meet the following requirements. 

The app will query data on openweathermap.org. A git repository will be used to manage the code. You can sign up for a GitHub account 
if you do not have one, and make a public repository that we can access.

Try to complete as many steps as possible.

You 

Each stage in the app should be developed as a seperate git branch, so we can test each step of the development.

It may be useful for you to use the Newtonsoft JSON to serialize and deserialize strings to .NET objects

------
## Step 1

Sign up for an api key http://openweathermap.org/appid

Create a new console application. 

This application will just assume that the first three strings in the commandline arguments are:
	ApiKey, CityName, CountryCode

It will then write the arguments to the console and wait for a key to be pressed before closing.
Please look at all steps before you start.
```
i.e.
ApiKey: 12323413
CityName: London
CountryCode: UK
```
------
## Step 2

The console app will get the current weather based on the arguments supplied previously see:

https://openweathermap.org/current#one

It will print the data shown above and then print the results of the api call to the console. You can print the results as a raw string, or format them however you wish
```
i.e.
ApiKey: 12323413
CityName: London
CountryCode: UK
Results:{"coord":{"lon":-0.13,"lat":51.51},"weather":[{"id":300,"main":"Drizzle","description":"light intensity drizzle","icon":"09d"}],"base":"stations","main":{"temp":280.32,"pressure":1012,"humidity":81,"temp_min":279.15,"temp_max":281.15},"visibility":10000,"wind":{"speed":4.1,"deg":80},"clouds":{"all":90},"dt":1485789600,"sys":{"type":1,"id":5091,"message":0.0103,"country":"GB","sunrise":1485762037,"sunset":1485794875},"id":2643743,"name":"London","cod":200}
```
------
## Step 3

A forth command line argument should be added to the app called Section it can be one of the following strings ("weather", "wind", "main", "clouds"). 
If it is not supplied the app should continue to work as in step 2. 
If supplied the app should only return that part of the result from the api call

```
i.e.
ApiKey: 12323413
CityName: London
CountryCode: UK
Section: main
Results:"main":{"temp":280.32,"pressure":1012,"humidity":81,"temp_min":279.15,"temp_max":281.15}
```
------
## Step 4

The results of the API call should be saved to a file as well as being displayed on the screen. This file keep all results from previous requests. 

------
## Step 5

If the City and Country have already been queried the results from the api call should be shown. Along with any matching results from the file.

------
## Step 6

The results from the file should be ordered most recent first and only the first 3 matches shown.
