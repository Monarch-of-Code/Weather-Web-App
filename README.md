# Weather Informer

A lightweight client-side weather dashboard that shows current weather, a multi-day forecast, and a map. Uses OpenWeatherMap and OpenStreetMap to provide location-aware weather, nearby popular cities, dynamic background images, and weather icons.

**Features**
- **Search**: Lookup weather by city name (search box).
- **Geolocation**: Auto-detects user location (browser Geolocation API) and shows local weather on load.
- **Map**: Interactive map with markers using Leaflet and OpenStreetMap tiles.
- **Forecast**: 5-day / 3-hour forecast summarized into daily items.
- **Popular nearby cities**: Lists nearby cities using OpenWeatherMap's `find` endpoint.
- **Dynamic UI**: Backgrounds, icons, and a summary panel update based on weather conditions.

**Tech Stack**
- **Frontend**: HTML, CSS, vanilla JavaScript
- **Libraries / Services**: Leaflet, Boxicons, Google Fonts
- **APIs**: OpenWeatherMap (current weather, forecast, find), Nominatim (reverse geocoding), OpenStreetMap tiles

**Installation**
- Clone or download the repo:

	```bash
	git clone <repository-url>
	cd Weather-Web-App
	```

- Open the app in a browser by opening [index.html](index.html).

Notes: This is a static, client-side app — no build step or server is required.

**Environment variables / API key**
- The project requires an OpenWeatherMap API key. The app reads the key from the `API_KEY` constant in [script.js](script.js).
- To set your own key, open [script.js](script.js) and replace the value of `API_KEY` near the top of the file.

Example:

```js
// in [script.js](script.js)
const API_KEY = "YOUR_OPENWEATHERMAP_API_KEY";
```

**API routes / external endpoints used**
- OpenWeatherMap current weather: `https://api.openweathermap.org/data/2.5/weather` (used by `getWeatherData` and `getWeatherDataByCoords`)
- OpenWeatherMap forecast: `https://api.openweathermap.org/data/2.5/forecast` (used by `getForecastData` and `getForecastByCoords`)
- OpenWeatherMap find (nearby cities): `https://api.openweathermap.org/data/2.5/find` (used by `getNearbyPopularCities`)
- Nominatim reverse geocoding: `https://nominatim.openstreetmap.org/reverse` (used by `reverseGeocode`)
- OpenStreetMap tile layer: `https://tile.openstreetmap.org/{z}/{x}/{y}.png` (used by Leaflet)

**Usage**
- Open [index.html](index.html) in a modern browser.
- Allow location access to show weather for your current position. If denied, the app falls back to Pakistan as the default location.
- Use the search box to fetch weather for any city.
- Click on the map to fetch weather for the clicked coordinates.
- Click a city in the "Popular Cities" list to load its weather and forecast.

**Folder structure**
- [index.html](index.html) — Main HTML file
- [script.js](script.js) — All application logic (API calls, UI updates, Leaflet map handlers)
- [style.css](style.css) — Styles and responsive layout
- IMAGES/ — All background images and icon assets
	- IMAGES/favicon/ — favicon files
	- IMAGES/groups/ — background images per weather group
	- IMAGES/ids/ — weather icons used in UI
	- IMAGES/levels/ — icons for humidity/air speed etc.

**Notes & warnings**
- The repository currently contains a hard-coded `API_KEY` in [script.js](script.js). Do not commit a private API key to public repositories. Replace it with your own key or load it securely if deploying.
- This is a purely client-side app; the API key will be visible in browser developer tools unless you proxy requests through a server.
- Some weather icons/background file paths contain spaces or escaped characters; keep the IMAGES folder structure intact to avoid broken assets.

**License**
- MIT — see LICENSE for details (you can add a LICENSE file if needed).

**Author**
- **Muhammad Muzammil** (Monarch of Code) — Full Stack Developer
