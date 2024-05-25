# SmartFlight: Real-Time Navigation and Risk Management for Aviation

## Project Overview
**SmartFlight** is a comprehensive solution designed to enhance flight safety and efficiency through real-time route optimization and risk management. By leveraging data from multiple sources and employing advanced algorithms, SmartFlight aims to minimize human errors and navigate various challenges encountered during flight navigation.

## Objective
- Design, develop, and implement a robust software solution for optimal route planning.
- Provide real-time risk assessments and suggest alternative routes.
- Integrate a real-time health metrics tracker based on flight sensor data.

## Key Features
- **Real-Time Data Integration**: Collects data from sources like OpenWeatherMap, AviationStack, and FAA NOTAMs.
- **Route Optimization**: Uses the Ant Colony Optimization (ACO) algorithm to find the safest and most efficient flight routes.
- **Risk Management**: Continuously assesses risks such as adverse weather conditions and electronic failures.
- **User Interface**: Provides an intuitive dashboard for pilots and control center operators to visualize optimal routes and associated risks.

## Tech Stack
- **Frontend**: HTML, CSS, JavaScript, Bootstrap, jQuery
- **Backend**: Flask (Python)
- **APIs**: OpenWeatherMap, AviationStack, FAA NOTAMs
- **Database**: Structured database with API accessibility
- **Algorithms**: Ant Colony Optimization (ACO)

## Project Structure
- `app.py`: Main application file containing the Flask app and route definitions.
- `templates/index.html`: Frontend HTML file.
- `static/`: Directory containing CSS, JavaScript, and other static files.
- `README.md`: Project documentation.
- `requirements.txt`: Python dependencies.

## Installation and Setup
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/smartflight.git
   cd smartflight
   ```

2. **Create and Activate a Virtual Environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Set API Keys**:
   - OpenWeatherMap API Key: `ef16aec95335978903143560c0af85ef`
   - AviationStack API Key: `4970ec9c0caf33db5b6670a82bc858ae`
   - Add your API keys to the environment variables or directly in the code.

5. **Run the Application**:
   ```bash
   flask run
   ```
   The application will be available at `http://127.0.0.1:5000/`.

## Usage Instructions
1. **Access the Web Interface**:
   Open your web browser and go to `http://127.0.0.1:5000/`.

2. **Input Flight Details**:
   - Enter the source airport code (e.g., JFK).
   - Enter the destination airport code (e.g., LAX).
   - Specify the number of nodes and iterations for the ACO algorithm.

3. **Optimize Route**:
   - Click on the "Optimize" button.
   - View the optimized route and associated risks in the results section.

## API Documentation
### Endpoints
- **`GET /`**: Serves the main HTML page.
- **`POST /optimize`**: Accepts form data to optimize the flight route.
  - **Parameters**:
    - `source_code`: Source airport code.
    - `destination_code`: Destination airport code.
    - `num_nodes`: Number of nodes for the ACO algorithm.
    - `iterations`: Number of iterations for the ACO algorithm.

### Example Usage
**Fetch Weather Data**:
```python
url = f"http://api.openweathermap.org/data/2.5/onecall?lat={lat}&lon={lon}&exclude=hourly,daily&appid={api_key}"
response = requests.get(url)
weather_data = response.json()
```

**Fetch Flight Data from AviationStack**:
```python
url = f"http://api.aviationstack.com/v1/flights?access_key={api_key}&dep_iata={source_code}&arr_iata={destination_code}"
response = requests.get(url)
flight_data = response.json()
```

## Contributing
1. **Fork the Repository**:
   ```bash
   git clone https://github.com/yourusername/smartflight.git
   ```

2. **Create a Feature Branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Commit Your Changes**:
   ```bash
   git commit -m "Add your message here"
   ```

4. **Push to the Branch**:
   ```bash
   git push origin feature/your-feature-name
   ```

5. **Open a Pull Request**: Describe your changes and submit a pull request.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.


---

By following these instructions, you will be able to set up, run, and evaluate the SmartFlight project effectively. Thank you for your time and consideration in reviewing this project.
