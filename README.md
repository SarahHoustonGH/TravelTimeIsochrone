# TravelTime Isochrone

This R script extracts isochrone maps from the TravelTime platform using the TravelTimeR package and displays them in a leaflet map.

## What is the TravelTime API?

The TravelTime API is a service provided by TravelTime that allows developers to calculate travel time and distances. It supports various modes of transportation and provides functionalities such as isochrone mapping, route optimization, and time-specific travel calculations.

## How the Code Works

1. **Load Required Libraries**: The script begins by loading the necessary R libraries - `traveltimeR` for interfacing with the TravelTime API and `leaflet` for creating interactive maps.

2. **Set API Credentials**: To access the TravelTime API, you need to set your API credentials using the `Sys.setenv()` function. You can sign up for an API key [here](https://docs.traveltime.com/api/overview/introduction).

3. **Request Isochrones for Multiple Locations**:
    - The script defines a list of arrival coordinates representing airports in Southeast England.
    - It then initializes an empty list to store the resulting maps.
    - Next, it loops through each arrival coordinate, creates a search object, and requests isochrones from the API using `time_map_fast()` function.
    - The resulting isochrone shapes are extracted and stored along with their colors in the `maps` list.

4. **Create Leaflet Map**:
    - After obtaining the isochrone data, the script creates a leaflet map.
    - It adds provider tiles for the map background and tiles for roads.
    - Then, it adds polygons representing each isochrone to the map.

5. **Display the Map**: Finally, the script displays the generated map.

## Requirements

- R environment
- `traveltimeR` and `leaflet` R packages
- TravelTime API credentials (API ID and API key)

## Notes

- The script uses the TravelTime API to generate isochrone maps for specified arrival coordinates (in this case, airports). You may modify the coordinates and parameters as needed.
- Free API usage is limited to a maximum of 5 searches per minute, if you are using the "free - restricted" version you will receive an email to state you are at the maximum of your API usage with this code.

