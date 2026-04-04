# 🚗 HU Commute Calculator

A lightweight, interactive web application designed for the Habib University community to calculate the precise distance of their daily commute and visualize the financial impact of the drastic fuel price hikes between February and April 2026.

## 📌 Overview

With petrol prices jumping from Rs 253/L to Rs 458/L in just a few months, the cost of commuting to campus has skyrocketed. This tool allows users to drop a pin on an interactive map of Karachi, input their vehicle's fuel average (Km/L), and instantly see how much more they are spending per week compared to the start of the semester. 

## ✨ Features

* **Interactive Map Integration:** Tap or drag a pin on the map to set your exact starting location.
* **Smart Search:** Text-based location search tailored specifically for Karachi neighborhoods.
* **Real-time Routing:** Calculates the actual driving distance (not just straight-line) to Habib University.
* **Financial Damage Report:** Breaks down the weekly cost of the commute across five different price points from early 2026.
* **100% Client-Side:** Runs entirely in the browser with no backend database or premium API keys required.

## 🛠️ Tech Stack

This project is built using vanilla web technologies and open-source mapping tools to ensure it remains free and accessible:

* **Frontend:** HTML5, CSS3, Vanilla JavaScript (ES6+).
* **Map Rendering:** [Leaflet.js](https://leafletjs.com/) for lightweight, mobile-friendly interactive maps.
* **Geocoding API:** [Nominatim (OpenStreetMap)](https://nominatim.org/) to convert user text inputs (e.g., "Gulshan e Iqbal") into precise Latitude/Longitude coordinates.
* **Routing API:** [Project OSRM (Open Source Routing Machine)](http://project-osrm.org/) to calculate the fastest driving route and distance from the user's pin to the campus.

## 🚀 How It Works

1. **Geocoding:** When a user types a location, the Nominatim API fetches the corresponding coordinates in Karachi and updates the Leaflet map.
2. **Coordinate Selection:** The user can interact with the Leaflet map to refine their starting position. The application listens for `dragend` or `click` events to capture the final Latitude and Longitude.
3. **Distance Calculation:** These coordinates, along with Habib University's fixed coordinates (`24.9056° N, 67.1382° E`), are sent to the OSRM API. OSRM computes the driving route and returns the exact distance in meters.
4. **Data Processing:** The JavaScript logic converts the distance to kilometers, calculates the liters required per trip based on the user's input, and multiplies this by the historical fuel rates to generate the final weekly cost comparison.

## 📊 Fuel Price Data (2026)

The calculations are based on the following timeline of petrol prices in Pakistan:

| Date | Rate (Rs/L) |
| :--- | :--- |
| **April 03, 2026** | 	378.41 |
| **April 3, 2026** | Rs 458.40 |
| **March 7, 2026** | Rs 321.17 |
| **March 1, 2026** | Rs 266.17 |
| **February 16, 2026** | Rs 258.17 |
| **February 1, 2026** | Rs 253.17 |

## 💻 Local Setup & Deployment

Because this app relies entirely on frontend code and public APIs, setup is instantaneous.

1. Clone the repository:

   ```bash
   git clone https://github.com/basilsaeedbari/hu-commute-calculator.git
