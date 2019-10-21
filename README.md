# Campus Detection Service ES6 Boilerplate

Boilerplate for an ES6 module that uses the [Campus Detection Service API](https://developers.iu.edu/resources/campus-detection-api/).

> For use as part of the JavaScript Community Workshop at [Statewide IT 2019](https://statewideit.iu.edu/).

## How it should work

For this tutorial, create an ES6 class module that:

- Provides a `CampusDetectionService` class to encapsulate campus detection functionality
- Provides an `async getClosestCampus()` method that queries the [`GET /campus/closest` endpoint](https://campus-detect.apps.iu.edu/campus/closest) and returns a `Promise` that resolves to an object with the following properties:

```js
{
  fullName: 'Indiana University Bloomington',
  shortName: 'IU Bloomington',
  abbr: 'iub',
  distance: 4.9
}
```

- Provides a `setPreferredCampus(campusAbbr)` method that uses the [`POST /campus/cookie`](https://campus-detect.apps.iu.edu/campus/cookie) endpoint to set a cookie storing the user's preferred campus

### Things to consider

- The `getClosestCampus()` method should first check to see if the user has set a preferred campus and return it instead
- The `setPreferredCampus()` method should check if the `campusAbbr` parameter is a valid campus abbreviation and `throw` an error if not
- The module should not rely on an external HTTP library or jQuery to make `GET` or `POST` requests to the Campus Detection Service API
- Include a `README.md` file that explains to developers how to use the module
- Include DocBlock-style comments for your class methods similar to those used in the [ES6 class module boilerplate](https://github.com/scottanthonymurray/es6-workshop-boilerplate/blob/master/ModuleName.js)