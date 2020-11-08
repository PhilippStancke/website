---
abstract: Este articulo se enfoca en buscar una explicación por el comportamiento de la población estadounidense por Estado en las elecciones del presidente. Nosotros analizamos factores de género que pueden haber influenciado este comportamiento.
authors:
- admin
#- Robert Ford
date: "2019-11-30T00:00:00Z"
doi: ""
featured: true
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/KHxxCc8XMNE)'
  focal_point: ""
  preview_only: false
# links:
# - name: Custom Link
#   url: http://example.org
projects:
# - internal-project
# publication: In *Source Themes Conference*
# publication_short: #n *STC*
publication_types:
- "4"
publishDate: "2019-11-30T00:00:00Z"
#slides: example
summary: Diese Arbeit wurde im Rahmen des Moduls "Economía Política de Género", an der Universidad de los Andes (Bogotá, Kolumbien) geschrieben.
tags:
- Women's March
- USA
- Donald Trump
- Elections
- 2017
- Politics
title: El ambiente político y los resultados de las elecciones estadounidenses
#url_code: '#'
#url_dataset: '#'
url_pdf: 
#url_poster: '#'
#url_project: ""
#url_slides: ""
#url_source: '#'
#url_video: '#'
---

<!DOCTYPE html>
<html>
<head>
	
	<title>Choropleth Tutorial - Leaflet</title>

	<meta charset="utf-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	
	<link rel="shortcut icon" type="image/x-icon" href="docs/images/favicon.ico" />

    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.5.1/dist/leaflet.css" integrity="sha512-xwE/Az9zrjBIphAcBb3F6JVqxf46+CDLwfLMHloNu6KEQCAWi6HcDUbeOfBIptF7tcCzusKFjFw2yuvEpDL9wQ==" crossorigin=""/>
    <script src="https://unpkg.com/leaflet@1.5.1/dist/leaflet.js" integrity="sha512-GffPMF3RvMeYyc1LWMHtK8EbPv0iNZ8/oTtHPx9/cc2ILxQ+u905qIwdpULaqDkyBKgOaB57QTMg7ztg8Jm2Og==" crossorigin=""></script>


	<style>
		html, body {
			height: 100%;
			margin: 0;
		}
		#map {
			width: 600px;
			height: 400px;
		}
	</style>

	<style>#map { width: 800px; height: 500px; }
.info { padding: 6px 8px; font: 14px/16px Arial, Helvetica, sans-serif; background: white; background: rgba(255,255,255,0.8); box-shadow: 0 0 15px rgba(0,0,0,0.2); border-radius: 5px; } .info h4 { margin: 0 0 5px; color: #777; }
.legend { text-align: left; line-height: 18px; color: #555; } .legend i { width: 18px; height: 18px; float: left; margin-right: 8px; opacity: 0.7; }</style>
</head>
<body>

<div id='map'></div>

<script type="text/javascript" src="mergedData.js"></script>

<script type="text/javascript">

	var map = L.map('map').setView([37.8, -96], 4);

	L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpejY4NXVycTA2emYycXBndHRqcmZ3N3gifQ.rJcFIG214AriISLbB6B5aw', {
		maxZoom: 18,
		attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, ' +
			'<a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, ' +
			'Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
		id: 'mapbox.light'
	}).addTo(map);


	// control that shows state info on hover
	var info = L.control();

	info.onAdd = function (map) {
		this._div = L.DomUtil.create('div', 'info');
		this.update();
		return this._div;
	};

	info.update = function (props) {
		this._div.innerHTML = '<h4>US Population Density</h4>' +  (props ?
			'<b>' + props.NAME + '</b><br />' + props.percentage + ' people / mi<sup>2</sup>'
			: 'Hover over a state');
	};

	info.addTo(map);


	// get color depending on population density value
	function getColor(d) {
		return d > 1 ? '#800026' :
				d > 0.6  ? '#BD0026' :
				d > 0.5  ? '#E31A1C' :
				d > 0.4  ? '#FC4E2A' :
				d > 0.3 ? '#FD8D3C' :
				d > 0.2 ? '#FEB24C' :
				d > 0.1 ? '#FED976' :
							'#FFEDA0';
	}

	function style(feature) {
		return {
			weight: 1,
			opacity: 0.2,
			color: 'white',
			dashArray: '3',
			fillOpacity: 0.5,
			fillColor: getColor(feature.properties.percentage)
		};
	}

	function highlightFeature(e) {
		var layer = e.target;

		layer.setStyle({
			weight: 5,
			color: '#666',
			dashArray: '',
			fillOpacity: 0.7
		});

		if (!L.Browser.ie && !L.Browser.opera && !L.Browser.edge) {
			layer.bringToFront();
		}

		info.update(layer.feature.properties);
	}

	var geojson;

	function resetHighlight(e) {
		geojson.resetStyle(e.target);
		info.update();
	}

	function zoomToFeature(e) {
		map.fitBounds(e.target.getBounds());
	}

	function onEachFeature(feature, layer) {
		layer.on({
			mouseover: highlightFeature,
			mouseout: resetHighlight,
			click: zoomToFeature
		});
	}

	geojson = L.geoJson(statesData, {
		style: style,
		onEachFeature: onEachFeature
	}).addTo(map);

	map.attributionControl.addAttribution('Datos de elecciones &copy; <a href="http://census.gov/">US Census Bureau</a>');


	var legend = L.control({position: 'bottomright'});

	legend.onAdd = function (map) {

		var div = L.DomUtil.create('div', 'info legend'),
			grades = [0, 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 1],
			labels = [],
			from, to;

		for (var i = 0; i < grades.length; i++) {
			from = grades[i];
			to = grades[i + 1];

			labels.push(
				'<i style="background:' + getColor(from) + '"></i> ' +
				from + (to ? '&ndash;' + to : '+'));
		}

		div.innerHTML = labels.join('<br>');
		return div;
	};

	legend.addTo(map);

</script>



</body>
</html>

