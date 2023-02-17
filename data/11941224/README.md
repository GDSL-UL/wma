# CLIWOC Slim & Routes

- [Dani Arribas-Bel](http://darribas.org/) [`[@darribas]`](https://twitter.com/darribas)

This data package contains two derivatives of the original CLIWOC data product that make using it for visualisation and teaching purposes more convenient. The derivatives are the following:

- `cliwoc_slim`: a version of CLIWOC 2.1 including only records with a longitude and latitude, a subset of the full variable list (`YR`, `MO`, `DY`, `HR`, `latitude`, `longitude`, `ID`, `C1`), and two additional columns, `date` with a processed date (`YR-MO-DY`), and `dys_since_start` with the count of days elapsed since the first record. The resulting file has a substantially smaller footprint.
- `cliwoc_routes`: a transformation of individual logs by the same ship into a single linestring or route. Crossings of longitude -180/180 are dealt with. In addition to the geometries, start date (`start`), end date (`end`), count of records (`records`), country (`C1`), and length of the route in days (`length_days`) are included.

**NOTE**: this product is not intended for climatological or historical research as it makes certain assumptions that favor visualisation. For those goals, the original CLIWOC package is preferred.

## Original Sources

- The original CLIWOC database was the result of a EU-funded project. Main website available at: [https://webs.ucm.es/info/cliwoc/](https://webs.ucm.es/info/cliwoc/)
- The input data to create these derivatives comes from the "HistoricalClimatology.com" team. The link for the [input data file in geopackage format](https://www.historicalclimatology.com/uploads/4/5/1/4/4514421/cliwoc21.gpkg) is available at: [https://www.historicalclimatology.com/cliwoc.html#](https://www.historicalclimatology.com/cliwoc.html#)
- To process the data, these notes by Steven Ottens were most useful: [https://stvno.github.io/page/cliwoc/](https://stvno.github.io/page/cliwoc/)

## Contents

This data package includes the following files:

- `cliwoc_slim.geopackage/mbtiles`: Geopackage and vector tileset versions of the `cliwoc_slim` table, expressed in lon/lat (`EPSG:4326`).
- `cliwoc_routes.geopackage/mbtiles`: Geopackage and vector tileset versions of the `cliwoc_routes` table, expressed in lon/lat (`EPSG:4326`).
- `cliwoc_process.ipynb`: Jupyter Notebook with code required to create both tables in each file format.
- `README.md`: documentation file.

## Computational Platform

The code in `cliwoc_process.ipynb` can be run using the [`darribas/gds:4.0`](https://github.com/darribas/gds_env) Docker container with [`tippecanoe`](https://github.com/mapbox/tippecanoe) installed to create vector tilesets.

