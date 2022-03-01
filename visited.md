---
layout: page
title: Visited Places
subtitle: Where I left memories
permalink: /hobbies/visited/
---

<script src="/js/ammap.js" type="text/javascript"></script>
<script src="/js/worldHigh.js" type="text/javascript"></script>
<script src="/js/dark.js" type="text/javascript"></script>
<div id="mapdiv" style="width: 100%; height: 750px;"></div>
<div style="width: 100%; font-size: 70%; padding: 5px 0; text-align: center; background-color: #535364; margin-top: 1px; color: #B4B4B7;">The light blue countries visited and grey ones for future, \(0w0)/ if possible.</div>
<script type="text/javascript">
var map = AmCharts.makeChart("mapdiv",{
type: "map",
theme: "dark",
projection: "winkel3",
panEventsEnabled : true,
backgroundColor : "#535364",
backgroundAlpha : 1,
zoomControl: {
zoomControlEnabled : true
},
dataProvider : {
map : "worldHigh",
getAreasFromMap : true,
areas :
[
	{
		"id": "FR",
		"showAsSelected": true
	},
	{
		"id": "BE",
		"showAsSelected": true
	},
	{
		"id": "NL",
		"showAsSelected": true
	},
	{
		"id": "DK",
		"showAsSelected": true
	},
	{
		"id": "IS",
		"showAsSelected": true
	},
	{
		"id": "NO",
		"showAsSelected": true
	},
	{
		"id": "ES",
		"showAsSelected": true
	},
	{
		"id": "CH",
		"showAsSelected": true
	},
	{
		"id": "CA",
		"showAsSelected": true
	},
	{
		"id": "MX",
		"showAsSelected": true
	},
	{
		"id": "US",
		"showAsSelected": true
	},
	{
		"id": "CN",
		"showAsSelected": true
	},
	{
		"id": "HK",
		"showAsSelected": true
	},
	{
		"id": "ID",
		"showAsSelected": true
	},
	{
		"id": "JP",
		"showAsSelected": true
	},
	{
		"id": "MO",
		"showAsSelected": true
	},
	{
		"id": "SG",
		"showAsSelected": true
	},
	{
		"id": "TW",
		"showAsSelected": true
	},
	{
		"id": "AE",
		"showAsSelected": true
	},
	{
		"id": "AU",
		"showAsSelected": true
	},
	{
		"id": "SE",
		"showAsSelected": true
	}
]
},
areasSettings : {
autoZoom : true,
color : "#B4B4B7",
colorSolid : "#84ADE9",
selectedColor : "#84ADE9",
outlineColor : "#666666",
rollOverColor : "#00429E",
rollOverOutlineColor : "#000000"
}
});
</script>
