LIVE WEATHER DASHBOARD (CLI)

Introduction

The Live Weather Dashboard (CLI) is a terminal-based Python application that creates a real-time weather data pipeline. It uses Python's requests library to fetch current weather information from the OpenWeatherMap Public API based on user input.

This project demonstrates essential Python programming and data engineering concepts, including API integration, JSON parsing, data processing with Pandas, file management, and command-line interface (CLI) development. The application not only displays live weather information but also stores every search in a CSV file, creating a historical weather log for future analysis.

---

Table of Contents

1. API Integration & Data Ingestion
2. JSON Data Parsing & Extraction
3. Data Persistence & Pandas Pipeline
4. Command-Line Interface (CLI) & Output Formatting
5. Potential Future Enhancements

---

1. API Integration & Data Ingestion

The application connects to the OpenWeatherMap Public API to retrieve real-time weather information.

Requests Library

Python's requests library is used to send HTTP GET requests to the API endpoint. Each request includes:

- City name entered by the user
- Unique OpenWeatherMap API Key (AppID)
- Temperature unit (Celsius)

Network Handling

The application validates HTTP response codes and handles common errors gracefully:

- 200 OK – Weather data retrieved successfully
- 404 Not Found – Invalid city name
- Network connection errors
- Invalid API key or other API-related issues

---

2. JSON Data Parsing & Extraction

The API returns weather information in JSON (JavaScript Object Notation) format.

Data Extraction

The JSON response is converted into a Python dictionary, and the application extracts important weather details such as:

- City Name
- Temperature (°C)
- Humidity (%)
- Weather Description
- Wind Speed (m/s)
- Date and Time of Search

These values are displayed in a clean and user-friendly format on the terminal.

---

3. Data Persistence & Pandas Pipeline

One of the key features of the application is maintaining a historical record of weather searches.

Pandas DataFrame

The extracted weather information is stored in a Pandas DataFrame together with the current timestamp.

CSV Logging

The application checks whether weather_history.csv already exists.

- If the file exists, the new weather record is appended.
- If the file does not exist, it is created automatically with column headers.

This creates a continuously growing weather history database for future analysis.

---

4. Command-Line Interface (CLI) & Output Formatting

The project is designed as a simple and interactive command-line application.

User Input

The user enters:

- OpenWeatherMap API Key
- City Name

Formatted Output

Instead of displaying raw JSON data, the application presents weather information in a clean, organized dashboard showing:

- Weather Condition
- Temperature
- Humidity
- Wind Speed

The formatted output improves readability and provides a better user experience.

---

Potential Future Enhancements

- Add graphical visualization of weather history using Matplotlib.
- Support batch weather queries for multiple cities.
- Export weather history to Excel.
- Display 5-day weather forecasts.
- Include air quality and UV index information.
- Build a graphical user interface (GUI) using Tkinter or PyQt.
- Automate scheduled weather logging using Python scheduling libraries.

---

Technologies Used

- Python 3
- Requests
- Pandas
- OpenWeatherMap API
- CSV File Handling
- Datetime Module
- OS Module

---

Author

Charanjit Singh 

Developed as part of the Python Programming Internship Module.