# Fusion Table Searchable Map Template
You want to put your data on a searchable, filterable map. This is a free, open source template to help you do it.

[![Searchable Map Template screenshot](https://raw.github.com/derekeder/FusionTable-Map-Template/master/images/searchable-map-template-v1.2.jpg)](http://derekeder.github.io/FusionTable-Map-Template/)

[See the working demo &raquo;](http://derekeder.github.io/FusionTable-Map-Template/)

## Features

* full screen, iframe and content templates
* display up to 100,000 map points
* address search (with variable radius and geocomplete)
* geolocation (find me!)
* results count
* RESTful URLs for sharing searches
* ability to easily add additional search filters (checkboxes, sliders, etc)
* mobile and tablet friendly using responsive design
* built with HTML, CSS and Javascript - no server side code required


## Releases

* [v 1.4](https://github.com/derekeder/FusionTable-Map-Template/releases/tag/v1.4) - iframe template, MapsLib class
* [v 1.3](https://github.com/derekeder/FusionTable-Map-Template/releases/tag/v1.3) - Bootstrap 3.2, more robust query function, dynamic zoom
* [v 1.2](https://github.com/derekeder/FusionTable-Map-Template/releases/tag/v1.2) - Bootstrap 3, jQuery 1.10.2, jQuery Address 1.6
* [v 1.1](https://github.com/derekeder/FusionTable-Map-Template/releases/tag/v1.1) - Bootstrap 2.0.3, jQuery 1.7.1, jQuery Address 1.4 
  
## Dependencies

* [Google Fusion Tables](http://www.google.com/fusiontables/Home)
* [Google Maps API V3](https://developers.google.com/maps/documentation/javascript)
* [jQuery](http://jquery.org)
* [jQuery Address](https://github.com/asual/jquery-address)
* [Bootstrap 3.2.0](http://getbootstrap.com/)

## Community
There's a [public Google Group](https://groups.google.com/forum/#!forum/fusion-table-map-template) for anyone who wants to or has used the Searchable Map Template. Join the growing community of map makers to learn, share and benefit from each other!

[Join the Fusion Table Map Template Google Group &raquo;](https://groups.google.com/forum/#!forum/fusion-table-map-template)

## Setup

Follow the steps below and you'll be in business with your own map.

1. Create a Fusion Table ([here's a great tutorial](https://support.google.com/fusiontables/answer/2527132?hl=en&topic=2573107&ctx=topic))
1. Make sure at least one column is set to a type of Location and that Fusion Tables has geocoded it
1. Set the Fusion Table to be publicly visible (via the Share button in the upper right) and make sure 'Allow Download' is enabled.
1. Create your own Google Maps JavaScript API key to replace the default in the Map Options section of the index.html file above. By inserting your own key, Google will allow 25,000 requests per day to your Searchable Map.
  1. Go to the [Google Developers Maps JavaScript API](https://console.developers.google.com/projectselector/apis/credentials) page and click the Get a Key button
  1. On the Google Developers Console page, select Create a New Project and press Continue
  1. On the Credentials page, create a key, which should look something like `AIzaSyBNVkiNzErPTEGpxWp0cvdqDMd2BxD-S50`.
  1. Copy and paste your key into the Map Options section of the index.html file as described above.
  1. To find or edit your key in the future, go back to the Google Developers Console page
1. Download or clone this project and fire up your text editor of choice. Open up `index.html` and set your map options at the bottom of the file ([see the full list of options](#mapslib-options))
   1. **fusionTableId** - the ID of your Fusion Table (found in Fusion Tables under File => About this table)
   1. **googleApiKey** - the API key from your [Google API Console](https://code.google.com/apis/console/)
   1. **locationColumn** - the name of your location column in your Fusion Table
   1. **map_center** - the lat/long you want your map to center on ([find yours here](http://www.itouchmap.com/latlong.html))
   1. **locationScope** - the area you want to limit searches to (set to 'chicago' by default)
1. **New** Get a Google Maps API key. [Follow these instructions](https://developers.google.com/maps/documentation/javascript/get-api-key) and replace the key on this line of `index.html`: `<script type="text/javascript" src="https://maps.google.com/maps/api/js?sensor=false&libraries=places&key=[YOUR KEY HERE]"></script>`
1. Add/modify additional filters to maps_lib.js. This will depend on the data you are trying to map. Take a look at the [wiki](https://github.com/derekeder/FusionTable-Map-Template/wiki) for [filter examples](https://github.com/derekeder/FusionTable-Map-Template/wiki/Filter-examples) and [list views](https://github.com/derekeder/FusionTable-Map-Template/wiki/List-search-results) to get started.
1. Upload this map and all the supporting files (css, fonts, images and js folders) to your site 

## MapsLib options

You can configure your map by passing in a dictionary of options when you create a new `MapsLib` instance in `index.html` or `index_iframe.html`. Here's an example:

```javascript
var myMap = new MapsLib({
  fusionTableId:      "1m4Ez9xyTGfY2CU6O-UgEcPzlS0rnzLU93e4Faa0",
