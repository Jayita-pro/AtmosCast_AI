# AtmosCast AI 🌦️

AtmosCast AI is a live weather dashboard that pairs real-time weather data with an immersive **procedural audio layer** — ambient soundscapes (like crickets, rain, or wind) that match the current conditions and time of day for any city you search.

Live demo: [atmoscast-ai.onrender.com](https://atmoscast-ai.onrender.com)

---

## ✨ Features

### 🔴 Live Weather
- Real-time temperature, "feels like," and daily min/max
- Current condition description (e.g. "Overcast clouds") with a matching weather icon
- Detailed stats grid: humidity, wind speed, pressure, visibility, sunrise, and sunset
- Dynamic animated background that shifts with time of day and weather (clear/cloudy/rainy, day/evening/night)

### 🎧 Procedural Audio Layer
- Pre-recorded ambient audio tracks (e.g. "Insects Crickets") automatically selected based on the current weather condition and time of day
- Built-in audio player with play/pause, seek, and volume controls

### 📅 Forecast
- "Today vs Tomorrow" temperature comparison
- Predicted humidity, wind speed, pressure, and expected condition for the next day
- AI status indicator showing the forecasting model is active

### 🔍 City Search
- Search any city from the navbar to instantly refresh live weather, stats, and audio

### ℹ️ About
- Overview of the project, how it works, and the team behind it

---

## 🛠️ Tech Stack

| Layer       | Technology                                   |
|-------------|-----------------------------------------------|
| Backend     | Python (Flask)                                |
| Templating  | Jinja2                                        |
| Weather Data| [OpenWeatherMap API](https://openweathermap.org/api) |
| Audio       | Pre-recorded static audio files (mapped by condition/time) |
| Frontend    | HTML, CSS (custom, glassmorphism-style UI), vanilla JS |
| Fonts/Icons | Google Fonts (Plus Jakarta Sans), Font Awesome |
| Hosting     | Render                                        |

---

## 📂 Project Structure

```
atmoscast-ai/
├── static/
│   ├── style.css
│   ├── media.css
│   ├── script.js
│   └── audio/              # Pre-recorded ambient sound files
├── templates/
│   ├── base.html
│   ├── live.html
│   ├── forecast.html
│   └── about.html
├── app.py                  # Flask app entry point
├── requirements.txt
├── .env                    # Environment variables (not committed)
└── README.md
```

> Note: adjust the structure above to match your actual repo layout if it differs.

---

## ⚙️ Setup & Installation

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/atmoscast-ai.git
cd atmoscast-ai
```

### 2. Create a virtual environment
```bash
python -m venv venv
source venv/bin/activate      # On Windows: venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure environment variables
Create a `.env` file in the project root:

```env
OPENWEATHER_API_KEY=your_openweathermap_api_key_here
FLASK_APP=app.py
FLASK_ENV=development
SECRET_KEY=your_secret_key_here
```

Get a free API key from [OpenWeatherMap](https://home.openweathermap.org/api_keys).

### 5. Run the app locally
```bash
flask run
```
Or:
```bash
python app.py
```

The app should now be running at `http://127.0.0.1:5000`.

---

## 🚀 Deployment

This project is deployed on **Render**. To deploy your own instance:

1. Push your code to GitHub.
2. Create a new **Web Service** on [Render](https://render.com).
3. Connect your GitHub repo.
4. Set the build command:
   ```bash
   pip install -r requirements.txt
   ```
5. Set the start command:
   ```bash
   gunicorn app:app
   ```
6. Add your environment variables (e.g. `OPENWEATHER_API_KEY`) in the Render dashboard under **Environment**.
7. Deploy 🎉

---

## 🔑 Environment Variables Reference

| Variable               | Description                              |
|------------------------|-------------------------------------------|
| `OPENWEATHER_API_KEY`  | API key for fetching live weather data    |
| `SECRET_KEY`           | Flask secret key for session security     |
| `FLASK_ENV`            | `development` or `production`             |

---

## 🗺️ Roadmap Ideas

- [ ] Multi-day extended forecast
- [ ] User accounts with saved/favorite cities
- [ ] More procedural audio variations
- [ ] Dark/light theme toggle

---

## 📄 License

Specify your license here (e.g. MIT).

---

## 👥 Team

_Add team member names and roles here (see the About page in the app for reference)._

