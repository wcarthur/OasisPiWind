# OasisPiWind

Perform the area peril and vulnerability lookup for PiWind example model. This will serve as an exemplar for creating look-up service for other models, and should encapculate best practices.

## Request Format

The request is in CSV or JSON format, and can be compressed or uncompressed.

For CSV set the Content-Type header to 'text/csv; charset=utf-8'.
For JSON set the Content-Type header to 'application/json; charset=utf-8'.
For zipped date set Content-Encoding header to 'gzip'.

### CSV
```
ID,LAT,LON,COVERAGE,CLASS_1,CLASS_2
1,0.5,0.5,1,A,B
2,1.5,0.5,1,A,B
```
### JSON
```javascript
[
  {
    "id": 1,
    "lat": 0.5, 
    "lon": 0.5, 
    "coverage": 1, 
    "class_1": "A", 
    "class_2": "B", 
  },
    {
    "id": 2,
    "lat": 0.5, 
    "lon": 0.5, 
    "coverage": 1, 
    "class_1": "A", 
    "class_2": "B", 
  }
}
```

## Response format

The response is in JSON format, and can be compressed or uncompressed.
```javascript
{
  "status": "success",
  "items": {
    "id": 1,
    "coverage": 1, 
    "status": "success", 
    "area_peril_id": 1, 
    "vulnerability_id": 1
  },
    {
    "id": 2,
    "coverage": 10, 
    "status": "nomatch", 
    "area_peril_id": 1, 
    "vulnerability_id": None,
    "message": "No vulnerability match."
  }
  {
    "id": 3,
    "coverage": 1, 
    "status": "fail", 
    "area_peril_id": None, 
    "vulnerability_id": 1,
    "message": "Invalid lat/lon."
  }
}
```
## Lookup Data
The lookup data is created using the PiWind output generated using the code in the [OasisImplementationModels](https://github.com/OasisLMF/OasisImplementationModels.git) repo. The area peril data was converted to be  the corners of the grid squares rather than a centroid point. 


## Example Client Code

TO BE UPDATED

## Manual installation

TO BE UPDATED

### Installation requirements

Python:
* Python 64 2.7
* Flask 0.10.1
* Shapely 1.5.13

### Deployment

TO BE UPDATED

## Installation script

TO BE UPDATED

## Server test

TO BE UPDATED