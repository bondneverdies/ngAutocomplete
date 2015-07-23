# ng-Autocomplete-Validation

An AngularJS directive for adding [Google Places Autocomplete](https://developers.google.com/places/webservice/autocomplete) 
to an input text element, based on [Will Palahnuk directive](http://github.com/wpalahnuk/ngAutocomplete). 

This fork allow the address validation : input.$valid will be false as long as the user has not selected an address provided 
by the Google API. To use this, add required="required" to your input tag.

 
## Requirements

+ AngularJS >= 1.2 (Uses optional directive parameters) _Tested with angularJS 1.2.21_
 
 
## Limitations

You can now set an initial value using ng-model. Using the ng-model to set the textbox value will not trigger the autocomplete query.


## Getting started

Install the library
```bash
$ bower install ng-autocomplete-validation
```

Include the requirements and the library
```html
<script type="text/javascript" src="http://maps.googleapis.com/maps/api/js?libraries=places&sensor=false"></script>
<script type="text/javascript" src="bower_components/angular/angular.min.js"></script>
<script type="text/javascript" src="bower_components/ng-autocomplete-validation/dist/ngAutocomplete.min.js"></script>
```

Declare a dependency on the `ngAutocomplete` module
``` javascript
var app = angular.module('myModule', ['ngAutocomplete']);
```

Add the directive to a textbox

``` javascript
<form>
    <input type="text"  ng-autocomplete ng-model="myplace" options="options" details="details" required="required"/>
</form>
```

## Documentation

+ ng-model - autocomplete textbox binding value

+ details - if specified, a more detailed autocomplete result will be provided, including address parts, lat-lng, etc. (Optional)

+ required - if specified, enable the validation

+ options - configuration for the autocomplete (Optional), see below:

  + types:              {Array}, containing one or more of the supported types listed in the [Google Places API: Supported Place Types list](https://developers.google.com/places/supported_types). The service will return results that match any of the specified types.
	+ bounds:             {[google.maps.LatLngBounds Object](https://developers.google.com/maps/documentation/javascript/reference#LatLngBounds)}, biases results to bounds, but may return results outside these bounds
	+ country:            {String}, ISO 3166-1 Alpha-2 compatible country code. examples; 'ca', 'us', 'gb'
  + watchEnter:         {Boolean}, true; on Enter select top autocomplete result. false(default); enter ends autocomplete
  + strict:             {Boolean}, true; validates angular input only on geocodable addresses. false(default); validates input on every autocompletable address

Example: 
``` javascript
options = {
  types: '(cities)',
  country: 'ca'
}
```

## Usage Examples

+ [Example Plunkers - Simple Usage](http://plnkr.co/edit/GE34ojss9xMGm0024FvM?p=preview)

+ [Example Plunkers - Advanced Usage](http://plnkr.co/edit/GF3nM3XfYX9El2w11pGo?p=preview)


## Credits

**Sylvain B** (https://github.com/bondneverdies)
**Will Palahnuk** (http://github.com/wpalahnuk)
**Google** (https://developers.google.com/maps/documentation/javascript/places)


## See also
 
 https://developers.google.com/maps/documentation/javascript/places
 https://developers.google.com/places/webservice/autocomplete

## Copyright and license

    The MIT License (MIT)

	Copyright (c) 2015 Sylvain B

	Permission is hereby granted, free of charge, to any person obtaining a copy
	of this software and associated documentation files (the "Software"), to deal
	in the Software without restriction, including without limitation the rights
	to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
	copies of the Software, and to permit persons to whom the Software is
	furnished to do so, subject to the following conditions:

	The above copyright notice and this permission notice shall be included in
	all copies or substantial portions of the Software.

	THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
	IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
	FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
	AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
	LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
	OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
	THE SOFTWARE.
