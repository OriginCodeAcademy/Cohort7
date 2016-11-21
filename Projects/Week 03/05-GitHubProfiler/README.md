# GitHub Profiler

## DUE TUESDAY @ 1PM

In this assignment, you will be building a web application in AngularJS that asks for a users GitHub username, then pulls up the information about that user made available through the GitHub API.

<img src="http://i.imgur.com/U71GnYa.png" alt="">

## VERY IMPORTANT NOTE
The GitHub API is very generous in that anybody can access their open API. However, they only allow 60 requests per hour from an IP address. As we are all sharing the same IP address, we are going to hit that number very quickly!

The solution to this problem is to grab a personal access token from GitHub and modify your HTTP call to include said token.

For example, instead of
```
http://api.github.com/users/cameronoca
```

You would use
```
http://api.github.com/users/cameronoca?access_token={INSERT_TOKEN_HERE}
```

See [this stack overflow discussion](http://stackoverflow.com/questions/33655700/github-api-fetch-issues-with-exceeds-rate-limit-prematurely) to learn how to create a personal access token on GitHub.

## Useful API Tips
- Use [http://api.github.com/users/{username}](http://api.github.com/users/cameronoca) to fetch information about a user.

## Useful Styling Tips
- Use [Bootstrap Wells](http://getbootstrap.com/components/#wells) to achieve the grey box effect.
- Use [Image Helper Classes](http://getbootstrap.com/css/#images) to achieve the circle image and responsive image effect.
- Use [Input Groups](http://getbootstrap.com/components/#input-groups) to achieve the textbox/button combination effect.
- Use the `text-danger` and `text-success` contextual classes to change the color of text.
- Use the grid system to accomplish the "side by side" effect shown in the demo above.

## Useful Angular Tips
- Use the $http service to make calls to the GitHub API.
- Use the [ng-src](https://docs.angularjs.org/api/ng/directive/ngSrc) directive to dynamically update the image based on the searched user.
- Use the [ng-href](https://docs.angularjs.org/api/ng/directive/ngHref) directive to dynamically update the link to the searched users profile.

## Extras
- Add a button called "View Repositories" that once clicked, will ask the GitHub API for information about the current users repositories and bind it to a table in your app.