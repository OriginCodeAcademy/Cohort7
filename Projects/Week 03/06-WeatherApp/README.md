# Weather App

### Due Wedenesday @ 10:30AM

In this assignment, you will be building an Angular application that allows a user to search for weather data using the [OpenWeatherMap](http://openweathermap.org/) API in a similar fashion to the following screenshot.

<img src="http://i.imgur.com/vLI7hzb.png" />

## Tasks
1. Create a folder named `06-WeatherApp` in your `dev` folder.
2. Setup your Git workflow.
  - Initialize an empty git repository in `06-WeatherApp` by running `git init` in the command prompt.
  - Create a repository on GitHub called `06-WeatherApp` and follow the instructions to add a remote origin.
3. Open this folder in your favorite text editor (Ours is Sublime!)
4. Create an `index.html` file and a corresponding `index.js` file.
5. Make use of the following AngularJS features to build this application.
  - Create a `factory` and inject a `$http` service to be used for calling the OpenWeatherMap API. (Remember, seperation of concerns!)
  - Create a `controller` and inject the factory you created above. Figure out the code you'll need to write to facilitate the given requirements.
  - Create an HTML Template to bind the information received from OpenWeatherMap to a view.
  
## Requirements
- Must be able to search for a city by name and see weather for that location.
- Must have a group of buttons for preloaded cities - when clicked, these buttons should load weather information for that location.
- Must have a search history that tracks the term entered and the time that the term was entered.
- Must be able to handle errors gracefully (Use the [angular-toastr](https://github.com/Foxandxss/angular-toastr) package to show an error to the user if the call to the API fails. It can be installed to your project using `bower install angular-toastr`.)

## Extras
- Come up with an idea with your pair partner and see what you can accomplish!

## Turn in instructions
* Push your changes to GitHub 
* [Click here to create an issue in the class repository](https://www.github.com/OriginCodeAcademy/2016-CW-FallCohort/issues/new?title=06-WeatherApp&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20the%20url%20of%20your%20repository%20below)%0A%0A2.%20How%20was%20it%20working%20with%20APIs%20for%20the%20first%20time%3F%0A%0A3.%20What%20was%20the%20most%20difficult%20part%20about%20working%20with%20an%20API%3F%0A%0A4.%20What's%20your%20favorite%20part%20about%20this%20assignment%3F)
  * Include a link to your repository in the description
  * Answer the questions filled out for you in the description