# LIVEWEATHER-DASHBOARD
The Live Weather Dashboard (CLI) is a terminal-based application that creates a real-time data pipeline. It uses Python's requests library to fetch current weather data from the OpenWeatherMap public API based on user input.

         Introduction

​The Live Weather Dashboard (CLI) is a command-line interface application designed to fetch, process, log, and display real-time weather information for any given city. As outlined in the file 1000231569.jpg, this project integrates core data engineering and software development concepts, including working with public APIs, JSON parsing, data manipulation with Pandas, and file management.

​By utilizing the OpenWeatherMap public API, the application serves as a practical pipeline that demonstrates how raw, live data from the web can be consumed dynamically and structured into a persistent historical data log (CSV format) for future analytics.

      Table of Contents


•​API Integration & Data Ingestion

•​JSON Data Parsing & Extraction

•​Data Persistence & Pandas Pipeline

•​Command-Line Interface (CLI) & Output Formatting


1. API Integration & Data Ingestion

​To obtain live, accurate weather data, the application connects to the OpenWeatherMap public API.

​The requests Library: Python’s built-in requests library is used to handle HTTP communication. The application sends a GET request to the API endpoint containing the target city name and a unique API developer key (AppID).

​Network Handling: This component manages API request states, ensuring the application gracefully handles connectivity errors, invalid city queries, or rate limits by checking the HTTP status codes (e.g., 200 OK for success, 404 Not Found for invalid cities).


2. JSON Data Parsing & Extraction

​Public web APIs typically respond with data structured in JSON (JavaScript Object Notation) format.

​Payload Structure: The raw API response contains nested structures containing coordinates, weather conditions, main metrics (temperature, pressure, humidity), wind speed, and system data.
​Extraction Process: The application parses this string response into a Python dictionary. It systematically extracts key-value pairs needed for the user dashboard, such as:

•​Temperature (converted from Kelvin to Celsius/Fahrenheit)

•​Humidity percentage

•​Weather description (e.g., "Clear sky", "Light rain")

•​Wind speed and direction

3.Data Persistence & Pandas Pipeline

​A key feature of this dashboard is its ability to build a historical archive of all weather searches.

​Pandas DataFrame Integration: Once the weather variables are extracted, they are structured into a single-row Pandas DataFrame along with a timestamp of the query.

​CSV Logging Pipeline: The pipeline checks if a historical log file (weather_history.csv) already exists. If it does, the Pandas pipeline appends the new DataFrame to the existing file without overwriting old data (mode='a'). If it doesn't exist, it creates the file and initializes the column headers.


​4. Command-Line Interface (CLI) & Output Formatting

​The user interface is designed purely for the terminal, focusing on readability and presentation.

​User Input: The script prompts the user to input a city name or type a keyword to exit.

​Visual Display: Instead of dumping a raw dictionary, the data is cleanly aligned using text formatting blocks, separators, or third-party tabular libraries (like tabulate) to display clear weather summaries, making it easily readable at a glance.


    Potential Future Enhancements


​Data Visualization Add-on: A separate script could read the generated weather_history.csv file using Pandas and plot temperature trends over time using libraries like Matplotlib or Seaborn. 

​Multi-city Batch Queries: Modifying the CLI input loop to take a list of cities separated by commas, fetching data for all of them concurrently, and appending them to the log as a single batch operation.

#Author Charanjit Developed as part of internship Python programming module.
