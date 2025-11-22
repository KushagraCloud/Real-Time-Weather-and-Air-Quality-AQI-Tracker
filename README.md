# Real-Time-Weather-and-Air-Quality-AQI-Tracker
# Real-Time Weather and AQI Tracker

## Overview

This is a command-line utility developed in Python 3.x. The function is to fetch and consolidate real-time meteorological data and Air Quality Index (AQI) reports from Open-Meteo API endpoints based on user-provided city names.

## Requirements

* Python 3.x
* The `requests` library for all HTTP communication.

## Installation and Execution

1.  **Dependencies:** Install the required library via pip.

    ```bash
    pip install requests
    ```

2.  **Execution:** Run the main script. The application will prompt for city input.

    ```bash
    python weather_aqi_tracker.py
    ```

## Functionality Summary

The application performs the following sequence:

1.  **Geocoding:** Converts city name input to latitude and longitude coordinates.
2.  **API Fetch:** Queries the Open-Meteo Weather API and Air Quality API simultaneously.
3.  **Stability:** Employs a `fetch_with_retry` mechanism with exponential backoff for all API calls (up to 3 retries).
4.  **Output:** Displays current temperature, wind metrics, weather condition interpretation, and Air Quality Index (EAQI/US AQI, PM2.5, PM10).

## Core Architecture

| Function | Role |
| :--- | :--- |
| `fetch_with_retry` | Handles all external HTTP requests and implements connection resilience. |
| `get_coordinates` | Translates user text input into numerical geographic data (Lat/Lon). |
| `fetch_weather_and_aqi_data` | Aggregates data from two separate API services into a single dictionary object. |
| `display_results` | Renders processed data (converting WMO codes to descriptions) into the final console report. |

## Documentation

For formal requirements and design principles, refer to `project_statement.md`.
