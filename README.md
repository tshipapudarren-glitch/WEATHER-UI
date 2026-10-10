# ICE Task 4 - Weather Dashboard UI

## 1. Introduction
The Weather Dashboard application is a React Native mobile application built with TypeScript and Expo[cite: 1]. It displays current weather conditions, a 24-hour hourly forecast, a 5-day daily forecast, sun and moon data, and additional weather metrics (such as humidity, wind speed, pressure, and UV index) across three major South African cities: Johannesburg, Cape Town, and Durban[cite: 1].

## 2. Development Environment
The application was developed, tested, and debugged using the following environment tools:
* **Framework:** React Native[cite: 1]
* **Platform:** Expo / Expo Go[cite: 1]
* **Language:** TypeScript[cite: 1]
* **Emulator/Testing:** BlueStacks 5[cite: 1]
* **Package Manager:** npm[cite: 1]

## 3. Error Log

| # | Location | Problem | Error Type | Correction |
|---|---|---|---|---|
| 1 | Imports | `ImageBackground` was missing from the React Native import list, causing rendering errors for the hero card. | Import / Rendering | Added `ImageBackground` to the `react-native` import statement. |
| 2 | City Selector Button | Button mapping checked `selectedCity === weather.country` instead of `weather.city`, and `onPress` passed the country string. | State / Logic | Updated the conditional check and state setter to use `weather.city` so individual cities highlight and switch correctly. |
| 3 | Current Details (`Humidity`) | The humidity detail card was incorrectly rendering `selectedWeather.feelsLike` instead of `selectedWeather.humidity`. | Data Selection | Changed the humidity value interpolation to use `${selectedWeather.humidity}%`. |
| 4 | Hourly Forecast ScrollView | The hourly ScrollView had `horizontal={false}` and hardcoded the current temperature for all hours instead of hourly temperatures. | Scrolling / Data Selection | Changed `horizontal={true}` for side-scrolling and updated hourly card text to display `hour.temperature`. |
| 5 | Daily Forecast Rendering | The 5-day forecast `.map()` method lacked a `return` statement inside its callback block. | Rendering / Syntax | Added a proper implicit return inside the daily forecast map function. |
| 6 | `WeatherDetail` Component | The reusable `WeatherDetail` component displayed `label` for both text fields instead of displaying the `value`. | Component Props | Updated the component's second text element to render `{value}`. |

## 4. Testing
The application was thoroughly tested across all three available cities (Johannesburg, Cape Town, and Durban) using the BlueStacks 5 emulator[cite: 1]:
* **City Selection:** Verified that clicking each city button successfully updates the hero background image, city name, temperature, and all weather details.
* **Hourly Forecast:** Verified that the 24-hour forecast scrolls horizontally and displays correct hourly temperatures and icons.
* **Daily Forecast:** Verified that the 5-day forecast renders all days with high and low temperatures correctly.
* **Sun & Moon / Additional Details:** Checked that sunrise, sunset, moon phases, and metrics like wind and humidity display accurate data.

## 5. Screenshot
*(Insert your screenshot showing the completed Weather Dashboard application running successfully inside the BlueStacks 5 emulator using Expo Go here)*[cite: 1]

## 6. Conclusion
Through investigating and fixing this Weather Dashboard application, I gained practical experience in debugging React Native components, managing state with TypeScript, handling layout props like horizontal scrolling, and fixing array mapping and component property passing bugs[cite: 1].
