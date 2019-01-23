# geocolor - was geocolor.io

geocolor classifies data contained in geojson properties, and assigns color values based on the [simplestyle-spec](https://github.com/mapbox/simplestyle-spec/blob/master/1.1.0/README.md). This means that when your geojson is rendered in github, [gists](https://gist.github.com/morganherlocker/b963cc241018326f1d16), mapbox, or other simplestyle-spec compliant renderers, you will get nice styles that help to visualize your data.

![Geocolors SC Counties](https://raw.githubusercontent.com/jalbertbowden/geocolor/master/img/geocolors-screenshot-sc-counties.jpeg)

## Install

```bash
npm install geocolor
```

## Colors

The color gradient is defined by simply passing an array of colors with as many stops as you want.

## Classification

Curently supported classifications:

- equal intervals
- quantiles
- jenks

## Example

![Geocolors Continental US Pins Example](https://raw.githubusercontent.com/jalbertbowden/geocolor/master/img/geocolors-pins-continental-us.jpg)

```js
var geocolor = require('geocolor')

var cities = {
  // [point data](https://github.com/morganherlocker/geocolor/blob/master/test/in/cities.geojson)
}

var z = 'Population',
    classification = 'jenks', // 'quantile' and 'interval' also supported
    numberOfBreaks = 5,
    colors = ['green', 'yellow', 'red']

geo = geocolor(cities, z, classification, numberOfBreaks, colors)

// properties now contains style info with encoded colors
console.log(geo) 
```

## Dev

Running tests:

```bash
npm test
```

## More Examples

![Geocolors Rivers Example](https://raw.githubusercontent.com/jalbertbowden/geocolor/master/img/geocolors-rivers.jpeg)  

![Geocolors Choloropleth South Carolina County Poverty](https://raw.githubusercontent.com/jalbertbowden/geocolor/master/img/geocolors-sc-counties-alt.jpeg)

![Geocolors Map Pin Gradient 1](https://raw.githubusercontent.com/jalbertbowden/geocolor/master/img/geocolors-pins-1.jpg)

![Geocolors Map Pin Gradient 2](https://raw.githubusercontent.com/jalbertbowden/geocolor/master/img/geocolors-pins-2.jpg)


