<!-- jump mark TOP -->
<a id="top"></a>

---
<div align="center">

# GeoJSON Sandbox
<!-- Status badges -->
![x] ![w] ![l] ![f] ![s]

</div>

<!-- ToC -->
<details>
  <summary>Inhaltsverzeichnis</summary>
  <ul style="list-style-type: none;">
    <li><a href="#was-ist-geojson">Was ist GeoJSON</a></li>
    <li><a href="#spezifikation">Spezifikation</a></li>
    <li><a href="#beispiel-objekt">Beispiel-Objekt</a></li>
    <li><a href="#anwendungsfälle">Anwendungsfälle</a></li>
  </ul>
</details>

## Was ist GeoJSON

GeoJSON ist ein [offenes Standardformat ![external link][e]][rfc] für die strukturierte Speicherung und den Austausch von Geodaten, das auf [JSON ![external link][e]][json] basiert. Als menschenlesbares, leichtgewichtiges und flexibles Format bietet GeoJSON eine bessere Unterstützung für die Entwicklung von Web-Anwendungen.  

<p align="right"><a href="#top">top ^</a></p>

## Spezifikation

GeoJSON-Objekte bestehen aus Geometrien und Metadaten (Eigenschaften).

> `Point`: Punkt  
> `LineString`: Linie aus zusammenhängenden Strecken  
> `Polygon`: geschlossenes Vieleck  
> `MultiPoint`, `MultiLineString`, `MultiPolygon`: mehrteilige Geometrien  
> `GeometryCollection`: Sammlung unterschiedlicher Geometrien  
> `Feature`: räumlich begrenzte Einheit bestehend aus Geometrien und Eigenschaften  
> `FeatureCollection`: Sammlung von Features  

Koordinaten werden in der Regel im Format `[Längengrad, Breitengrad]` (Longitude, Latitude) im WGS84-Koordinatensystem angegeben. Mit dem `properties`-Objekt können Feature-Eigenschaften definiert werden in der Form `"eigenschaft": "wert"`.  

<p align="right"><a href="#top">top ^</a></p>

## Beispiel-Objekt

```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "city": "Dresden",
        "country": "Germany",
        "poi": "Dresdner Zwinger"
      },
      "geometry": {
        "coordinates": [
          13.7337,
          51.0530
        ],
        "type": "Point"
      }
    }
  ]
}
```

Im Beispiel wird ein "point of interest" in Dresden dargestellt mit den Koordinaten (Längengrad: 13.7337, Breitengrad: 51.0530) sowie beschreibende Eigenschaften, wie Stadt und Land.

<p align="right"><a href="#top">top ^</a></p>

## Anwendungsfälle

- **Datenaustausch**: GeoJSON ermöglicht einen plattform- und anwendungsübergreifenden Austausch von Geodaten.
- **Datenanalyse**: GeoJSON wird zur Analyse und Visualisierung von Geodaten in GIS-Anwendungen wie QGIS oder ArcGIS verwendet.
- **Webkarten**: GeoJSON findet Verwendung in Software-Bibliotheken wie Leaflet oder [Mapbox ![external link][e]][geojsonio] zur Erstellung von Karten.

### GeoJSON und GitHub

[GitHub erkennt GeoJSON-Daten ![external link][e]][githubmap] in deinem Repository automatisch und stellt sie als interaktive Karte dar. Strichbreite, Farbe, Füllung und Transparenz lassen sich dabei über die Eigenschaften eines GeoJSON-Objektes anpassen.

```
"properties": {
    "stroke": "#ff3377",
    "stroke-width": 0.5,
    "stroke-opacity": 1,
    "fill": "#00cccc",
    "fill-opacity": 0.6
}
```

<p align="right"><a href="#top">top ^</a></p>

<!-- Badges & Icons -->
[f]: https://img.shields.io/github/forks/mephi78/geojson-sandbox?style=flat&color=lightseagreen&labelColor=%230F639C
[l]: https://img.shields.io/github/last-commit/mephi78/geojson-sandbox?labelColor=%230F639C
[w]: https://img.shields.io/badge/work-in%20progress-yellow?labelColor=%230F639C
[e]: https://codeberg.org/Mephi/my-assets/raw/icons/PNG/mephi-external-link-16x16-blue.png
[s]: https://img.shields.io/github/stars/mephi78/geojson-sandbox?style=flat&color=goldenrod&labelColor=%230F639C
[x]: https://img.shields.io/badge/status-experimental-orange?labelColor=%230F639C

<!-- external links -->
[awesome]: https://github.com/tmcw/awesome-geojson
[geojsonio]: https://geojson.io
[githubmap]: https://github.blog/news-insights/the-library/gist-meets-geojson/
[json]: https://www.json.org/json-de.html
[rfc]: https://datatracker.ietf.org/doc/html/rfc7946