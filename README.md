<div align="center">

# 🌬️ AtmosCast AI
### *Weather You Can Hear, Not Just See*

**An AI-powered weather forecasting web app that turns real-time weather data into immersive, synchronized ambient soundscapes.**

<br/>

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-2.x-000000?style=for-the-badge&logo=flask&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![OpenWeather API](https://img.shields.io/badge/OpenWeather-API-EB6E4B?style=for-the-badge&logo=openweathermap&logoColor=white)

![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Status](https://img.shields.io/badge/Status-Live-brightgreen?style=flat-square)
![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-blueviolet?style=flat-square)
![Made with Love](https://img.shields.io/badge/Made%20with-%E2%9D%A4-red?style=flat-square)

**[🔗 Live Demo](https://aerowave.onrender.com)**

</div>

---

## 📖 Project Description

**AtmosCast AI** reimagines weather forecasting by engaging more than just your eyes. Instead of showing a plain temperature card, it builds an **immersive sensory experience** — pairing live weather data with a **procedural ambient audio layer** that matches the sky outside your window.

Overcast skies bring in a calm crackle of insects and crickets. Rain doesn't just show as an icon — you *hear* it. A thunderstorm doesn't just say "⚡ Storm" — you feel the rumble in the background audio. Add to that an **AI-generated tomorrow's forecast** with predicted humidity, wind, pressure, and expected conditions, and AeroWave AI feels less like a utility and more like a companion for your day.

> 🎯 **Goal:** Make weather *felt*, not just *read*.

---

## ✨ Key Features

| | Feature | Description |
|---|---------|--------------|
| 🌍 | **Real-Time Weather Data** | Live conditions (temperature, "feels like", min/max) fetched via the OpenWeather API |
| 🔍 | **City Search** | Instantly search and switch between any city worldwide |
| 🎧 | **Procedural Audio Layer** | An in-page audio player streams a soundscape matched to current conditions (e.g. *Insects Crickets* for overcast skies) |
| 🐦 | **Condition-Based Audio Mapping** | Sunny → birds chirping, Rain → rain sounds, Thunderstorm → thunder + rain, Windy → wind ambience |
| 📊 | **Detailed Live Metrics** | Humidity, wind speed, pressure, visibility, sunrise & sunset — all on one dashboard |
| 🔮 | **AI-Powered Tomorrow's Forecast** | Dedicated Forecast tab comparing today vs. tomorrow's temperature |
| 📈 | **Predicted Environmental Data** | Forecasted humidity, wind speed, pressure, and expected sky condition for the next day |
| 🎨 | **Clean, Responsive UI** | Dark-themed, glassmorphic dashboard built with HTML5/CSS3 for a smooth cross-device experience |
| ⚡ | **Lightweight Flask Backend** | Fast, minimal-dependency Python server, deployed live on Render |

---

## 🖼️ Screenshots

<div align="center">

### 🏠 Live Weather Dashboard
*Current conditions for the searched city — temperature, condition, feels-like, and min/max*
<img src="./assets/screenshots/live-dashboard.png" alt="Live Weather Dashboard Screenshot" width="80%"/>

### 🎧 Procedural Audio Layer + Environmental Metrics
*Ambient sound player synced to weather, alongside humidity, wind, pressure, visibility, sunrise & sunset*
<img src="./assets/screenshots/audio-metrics.png" alt="Procedural Audio Layer Screenshot" width="80%"/>

### 🔮 AI Forecast Tab
*Tomorrow's predicted temperature, humidity, wind, pressure, and expected condition*
<img src="./assets/screenshots/ai-forecast.png" alt="AI Forecast Screenshot" width="80%"/>

</div>

> 📌 *Place your actual screenshots inside `assets/screenshots/` and update the file names above.*

---

## 🏗️ System Architecture

```
┌──────────────────────┐        ┌───────────────────────┐        ┌────────────────────┐
│   User Interface     │  HTTP  │   Flask Backend        │  API   │   OpenWeather API   │
│  (Live/Forecast/About)│ ─────▶ │  (app.py routing)       │ ─────▶ │  (Live Weather Data)│
└──────────────────────┘        └───────────────────────┘        └────────────────────┘
          ▲                               │
          │                               ▼
          │                     ┌───────────────────────┐
          │                     │   audio_engine.py        │
          │                     │  Weather → Sound Mapping │
          │                     └───────────────────────┘
          │                               │
          │                               ▼
          │                     ┌───────────────────────┐
          └────────────────────│   forecast_engine.py      │
                                │  + weather_model.pkl      │
                                │  (Tomorrow's Prediction)  │
                                └───────────────────────┘
```

**Flow:**
1. User searches for a city on the **Live** tab.
2. Flask backend (`app.py`) calls the **OpenWeather API** for live data.
3. `audio_engine.py` maps the current condition to a matching ambient sound clip.
4. Frontend renders the dashboard and plays the synced procedural audio.
5. On the **Forecast** tab, `forecast_engine.py` uses the trained `weather_model.pkl` to predict tomorrow's temperature, humidity, wind, pressure, and expected condition.

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| 🎨 Frontend | HTML5, CSS3, JavaScript | UI structure (Live/Forecast/About), styling, interactivity |
| ⚙️ Backend | Python, Flask | Server-side logic & API routing |
| ☁️ Weather Data | OpenWeather API | Real-time weather data |
| 🔊 Audio Engine | Python + HTML5 Audio | Weather-to-sound mapping & in-browser playback |
| 🧠 AI/ML Layer | Python (`train_global_model.py`, `weather_model.pkl`) | Next-day weather prediction |
| ☁️ Deployment | Render | Live hosting (`aerowave.onrender.com`) |

---

## 📂 Folder Structure

```
AeroWave_AI/
│
├── app.py                       # Main Flask application entry point
├── audio_engine.py               # Weather → sound mapping & playback logic
├── forecast_engine.py            # Tomorrow's weather prediction logic
├── train_global_model.py         # Script to train the forecasting ML model
├── weather_model.pkl              # Trained AI/ML model for forecasting
├── requirements.txt               # Python dependencies
├── .gitignore
├── README.md
│
├── templates/
│   ├── base.html                  # Shared layout/base template
│   ├── live.html                  # Live current weather + audio page
│   ├── forecast.html              # Tomorrow's AI forecast page
│   └── about.html                 # About the project page
│
├── static/
│   ├── style.css                  # Core application styling
│   ├── media.css                  # Media/responsive styling
│   ├── script.js                  # Frontend logic & audio sync
│   │
│   └── sounds/
│       ├── birds_chirping.wav
│       ├── light_rain.wav
│       ├── heavy_rain.wav
│       ├── thunderstorm.wav
│       ├── wind_blowing.wav
│       ├── cold_wind.wav
│       ├── spring_forest.wav
│       └── insects_crickets.wav
```

---

## ⚙️ Installation Guide

<details>
<summary><strong>📥 Click to expand full setup instructions</strong></summary>

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/<your-username>/AeroWave_AI.git
cd AeroWave_AI
```

### 2️⃣ Create a Virtual Environment
```bash
python -m venv venv

# Activate it:
# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
```

### 3️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 4️⃣ Configure Environment Variables
Create a `.env` file in the root directory (see [Environment Variables](#-environment-variables) below).

### 5️⃣ Run the Application
```bash
python app.py
```

### 6️⃣ Open in Browser
```
http://127.0.0.1:5000
```

</details>

---

## 🔑 Environment Variables

Create a `.env` file in the project root with the following keys:

```env
# OpenWeather API Configuration
OPENWEATHER_API_KEY=your_openweather_api_key_here

# Flask Configuration
FLASK_ENV=development
FLASK_APP=app.py
SECRET_KEY=your_secret_key_here
```

> 🔐 **Never commit your `.env` file.** Add it to `.gitignore` to keep API keys secure.

---

## 🚀 Usage Instructions

1. Visit the [live app](https://aerowave.onrender.com) or launch it locally using the steps above.
2. Use the **search bar** to look up any city.
3. On the **Live** tab, view temperature, condition, feels-like, min/max, humidity, wind speed, pressure, visibility, sunrise, and sunset.
4. Press play on the **Procedural Audio Layer** player to hear the ambient sound matching current conditions.
5. Switch to the **Forecast** tab to see tomorrow's predicted temperature, humidity, wind, pressure, and expected condition.
6. Check the **About** tab to learn more about the project.

---

## 🔮 Future Enhancements

- [ ] 🎙️ Voice-based weather assistant (text-to-speech narration)
- [ ] 📍 Auto-detect location via geolocation API
- [ ] 📱 Progressive Web App (PWA) support for mobile installs
- [ ] 🌙 Light/dark theme toggle
- [ ] 📊 7-day extended forecast with trend charts
- [ ] 🧠 Improved AI model for more accurate next-day predictions
- [ ] 🔔 Weather alert notifications (storms, extreme heat, etc.)
- [ ] 🌐 Multi-language support

---

## 🌟 Why AeroWave AI is Unique

Most weather apps stop at showing numbers and icons. **AeroWave AI goes further:**

| Traditional Weather Apps | 🌬️ AeroWave AI |
|---------------------------|------------------|
| Shows temperature & icons only | Shows data **and** lets you *hear* the weather |
| Static, one-way information | Immersive, procedural audio experience |
| Basic next-day guess | AI-predicted temperature, humidity, wind & pressure |
| No emotional connection | Ambient sound creates atmosphere & mood |
| One-size-fits-all UI | Dedicated Live, Forecast, and About experiences |

> 💡 AeroWave AI blends **meteorology, machine learning, and sound design** into one seamless product — making it a standout portfolio project that demonstrates full-stack thinking, creativity, and technical depth.

---

## 🤝 Contributing

Contributions are welcome and appreciated! 🎉

1. **Fork** this repository
2. Create your feature branch
   ```bash
   git checkout -b feature/YourFeatureName
   ```
3. **Commit** your changes
   ```bash
   git commit -m "Add: YourFeatureName"
   ```
4. **Push** to your branch
   ```bash
   git push origin feature/YourFeatureName
   ```
5. Open a **Pull Request** and describe your changes

Please make sure your code follows the existing style and includes relevant documentation/comments.

---

## 📄 License

This project is licensed under the **MIT License** — you're free to use, modify, and distribute it with attribution.

See the [LICENSE](./LICENSE) file for full details.

---

## 👤 Author

<div align="center">

**[Your Name]**

💼 Aspiring Software Developer | AI & Web Enthusiast

[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/<your-username>)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/<your-profile>)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your.email@example.com)

</div>

---

<div align="center">

### 🌤️ *"Don't just check the weather — experience it."*

⭐ **If you found this project interesting, consider giving it a star!** ⭐

Made with ❤️ and ☕ by **[Jayita Kapoor]**

</div>
