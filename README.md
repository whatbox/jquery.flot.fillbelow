# Fill below plugin for jQuery Flot
[![Build Status](https://travis-ci.org/whatbox/jquery.flot.fillbelow.png?branch=master)](https://travis-ci.org/whatbox/jquery.flot.fillbelow)

## About
This is a plugin for the jQuery powered Flot plotting library. It's goal is to improve upon the default fillbetween plugin making it more suitable for difference line graphs.
![Difference Line Graph](https://raw.github.com/whatbox/jquery.flot.fillbelow/master/example.png)

This is developed by [Whatbox Inc.](https://whatbox.ca/) for internal use and released as on Open Source project under the MIT license. Patches and bug reports are welcome, please see our [CLA](https://whatbox.ca/policies/contributions).

## Dependencies
The following packages are necessary for this module.
* [jQuery](https://github.com/jquery/jquery)
* [Flot](https://github.com/flot/flot)


## Usage
The usage should be familiar to anyone who has used jquery.flot.fillbetween.js before, the only notable difference is that fill should be false.

	var dataset = [
		{ data: [ ... ], id: "foo" },
		{ data: [ ... ], fillBelowTo: "foo" }
	];

	$.plot($("#placeholder"), dataset, { line: { show: true }});

Similarly, you can set fillbelow on two data sets against each other

	var dataset = [
		{ data: [ ... ], id: "revenue", fillBelowTo: "expenses" },
		{ data: [ ... ], id: "expenses", fillBelowTo: "revenue" }
	];

	$.plot($("#placeholder"), dataset, { line: { show: true }});

You can also either use the default `lines.fillColor` color or a configured color by using the `fillBelowUseSeriesObjectFillColor` property.
 - If `fillBelowUseSeriesObjectFillColor` is `true`, `lines.fillColor` will be used as the fill color. If `lines.fillColor` is not defined, the `series.color` property will be used.
 - If `fillBelowUseSeriesObjectFillColor` is `false`, the `fillColor` property will be used.

        var dataset = [
            { data: [ ... ], id: "revenue", fillBelowTo: "expenses", fillBelowUseSeriesObjectFillColor: false, fillColor: "#FF0000" },
            { data: [ ... ], id: "expenses", fillBelowTo: "revenue", fillBelowUseSeriesObjectFillColor: false, fillColor: "#00FF00" }
        ];
    
        $.plot($("#placeholder"), dataset, { line: { show: true }});
