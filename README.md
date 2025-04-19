# weatherapp
## Date:19-04-2025

## AIM
To devolpe a simple weather application using React that allows the user to enter a city name and view simulated weather data such as temperature, wind speed, and sky condition.
## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app weather-app</li>
  <li>cd weather-app</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, open or create App.js and set up a functional component called WeatherApp.

### STEP 4
Create a mock data object with predefined weather info for cities like Kerala, Arni, Chennai, etc.

### STEP 5
Add a text input field to accept the city name from the user.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test with city names from the mock data and confirm the error message appears for invalid ones.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM

App.js
```
import React, { useState } from 'react';
import './App.css';

function App() {
  const mockData = {
    Chennai: { temperature: '15°C', wind: '10 km/h', sky: 'Cloudy' },
    Kerala: { temperature: '18°C', wind: '12 km/h', sky: 'Sunny' },
    Arni: { temperature: '20°C', wind: '8 km/h', sky: 'Rainy' },
  };
 

  const [city, setCity] = useState('');
  const [weather, setWeather] = useState(null);
  const [error, setError] = useState('');

  const handleSearch = () => {
    const data = mockData[city.trim()];
    if (data) {
      setWeather(data);
      setError('');
    } else {
      setWeather(null);
      setError('City not found.');
    }
  };

  return (
    <div className="container">
      <h2>Simple Weather App</h2>
      <input
        type="text"
        placeholder="Enter city name"
        value={city}
        onChange={(e) => setCity(e.target.value)}
        onKeyDown={(e) => e.key === 'Enter' && handleSearch()}
      />
      <button onClick={handleSearch}>Search</button>
<br></br>
      {weather && (
        <div className="weather-box">
          <p><strong>Temperature:</strong> {weather.temperature}</p>
          <p><strong>Wind:</strong> {weather.wind}</p>
          <p><strong>Sky:</strong> {weather.sky}</p>
        </div>
      )}

      {error && <p className="error">{error}</p>}
    </div>
  );
}

export default App;

```
App.css
```
.container {
  text-align: center;
  font-family: Arial, sans-serif;
  margin-top: 50px;
}

input {
  padding: 8px;
  width: 200px;
  margin-right: 10px;
}

button {
  padding: 8px 16px;
  cursor: pointer;
}

.weather-box {
  margin-top: 20px;
  background-color: #f2f2f2;
  padding: 15px;
  border-radius: 10px;
  display: inline-block;
}

.error {
  color: red;
  margin-top: 20px;
}

```


## OUTPUT
![1-web](https://github.com/user-attachments/assets/a535cfae-f8df-4d2f-a843-f9967cfdd24d)
![2-web](https://github.com/user-attachments/assets/9b85ec12-547e-4f2e-bf02-79f6427100bd)
![3-web](https://github.com/user-attachments/assets/83bcd0df-9b1a-4f4a-b4d0-3b14376a6563)
![4-web](https://github.com/user-attachments/assets/d75d0dce-1743-4430-a9c7-72a4d0e1bb31)


## RESULT
The program for developing a weather app in React.js is executed successfully.
