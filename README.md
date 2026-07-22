<div align="center">

# 🌦️ AtmosCast AI
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
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square)
![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-blueviolet?style=flat-square)
![Made with Love](https://img.shields.io/badge/Made%20with-%E2%9D%A4-red?style=flat-square)

</div>

---

## 📖 Project Description

**AtmosCast AI** reimagines weather forecasting by engaging more than just your eyes. Instead of showing a plain temperature card, it builds an **immersive sensory experience** — pairing live weather data with **AI-generated ambient soundscapes** that match the sky outside your window.

Rain doesn't just show as an icon — you *hear* it. A thunderstorm doesn't just say "⚡ Storm" — you feel the rumble in the background audio. Add to that an **AI-generated tomorrow's forecast** with natural-language narration, and AtmosCast AI feels less like a utility and more like a companion for your day.

> 🎯 **Goal:** Make weather *felt*, not just *read*.

---

## ✨ Key Features

| | Feature | Description |
|---|---------|--------------|
| 🌍 | **Real-Time Weather Data** | Fetches live conditions using the OpenWeather API |
| 🔊 | **Dynamic Ambient Sound Sync** | Auto-plays contextual sounds matching current weather |
| 🐦 | **Condition-Based Audio Mapping** | Sunny → birds, Rain → rainfall, Storm → thunder + rain, Windy → wind ambience |
| 🔮 | **Tomorrow's Forecast Prediction** | AI-assisted prediction of next-day weather trends |
| 🗣️ | **AI Weather Narration** | Natural-language, human-like weather summaries |
| 🎨 | **Clean, Responsive UI** | Built with modern HTML5/CSS3 for a smooth cross-device experience |
| ⚡ | **Lightweight Flask Backend** | Fast, minimal-dependency Python server |
| 🌐 | **Location-Based Forecasting** | Search any city worldwide for instant conditions |

---

## 🖼️ Screenshots

<div align="center">

### 🏠 Home Dashboard
<img src="./assets/screenshots/home-dashboard.png" alt="Home Dashboard Screenshot" width="80%"/>

### 🌦️ Live Weather + Ambient Sound Player
<img src="./assets/screenshots/weather-sound-player.png" alt="Weather Sound Player Screenshot" width="80%"/>

### 🔮 AI Forecast Narration
<img src="./assets/screenshots/ai-narration.png" alt="AI Narration Screenshot" width="80%"/>

</div>

> 📌 *Place your actual screenshots inside `assets/screenshots/` and update the file names above.*

---

## 🏗️ System Architecture

```
┌──────────────────────┐        ┌───────────────────────┐        ┌────────────────────┐
│   User Interface     │  HTTP  │   Flask Backend        │  API   │   OpenWeather API   │
│  (HTML/CSS/JS)        │ ─────▶ │  (Python / Routing)    │ ─────▶ │  (Live Weather Data)│
└──────────────────────┘        └───────────────────────┘        └────────────────────┘
          ▲                               │
          │                               ▼
          │                     ┌───────────────────────┐
          │                     │  Weather → Sound        │
          │                     │  Mapping Engine          │
          │                     └───────────────────────┘
          │                               │
          │                               ▼
          │                     ┌───────────────────────┐
          └────────────────────│  AI Narration & Next-Day │
                                │  Prediction Module       │
                                └───────────────────────┘
```

**Flow:**
1. User enters a city or shares location.
2. Flask backend calls the **OpenWeather API** for live data.
3. Weather condition is mapped to a corresponding **ambient sound**.
4. AI module generates a **narration + tomorrow's forecast**.
5. Frontend renders data, plays synced audio, and displays narration.

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| 🎨 Frontend | HTML5, CSS3, JavaScript | UI structure, styling, interactivity |
| ⚙️ Backend | Python, Flask | Server-side logic & API routing |
| ☁️ Weather Data | OpenWeather API | Real-time & forecast weather data |
| 🔊 Audio Engine | JavaScript (Web Audio) | Ambient sound playback & syncing |
| 🧠 AI Layer | Python (custom logic / NLP) | Narration generation & next-day prediction |

---

## 📂 Folder Structure

```
AtmosCast-AI/
│
├── app.py                     # Main Flask application entry point
├── requirements.txt            # Python dependencies
├── .env.example                 # Sample environment variables
│
├── static/
│   ├── css/
│   │   └── style.css           # Application styling
│   ├── js/
│   │   └── script.js           # Frontend logic & audio sync
│   └── sounds/
│       ├── birds.mp3
│       ├── rain.mp3
│       ├── thunder.mp3
│       └── wind.mp3
│
├── templates/
│   └── index.html               # Main UI template
│
├── modules/
│   ├── weather_service.py       # OpenWeather API integration
│   ├── sound_mapper.py          # Weather → sound logic
│   └── ai_narration.py          # AI forecast & narration generator
│
├── assets/
│   └── screenshots/              # README screenshots
│
└── README.md
```

---

## ⚙️ Installation Guide

<details>
<summary><strong>📥 Click to expand full setup instructions</strong></summary>

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/<your-username>/AtmosCast-AI.git
cd AtmosCast-AI
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

# Optional: AI Narration Settings
AI_NARRATION_ENABLED=True
```

> 🔐 **Never commit your `.env` file.** Add it to `.gitignore` to keep API keys secure.

---

## 🚀 Usage Instructions

1. Launch the app locally using the steps above.
2. Enter a **city name** in the search bar.
3. View real-time weather conditions (temperature, humidity, condition icon).
4. Listen as the **ambient sound automatically syncs** with the weather.
5. Scroll down to see **tomorrow's AI-predicted forecast** with narration.
6. Explore different cities to hear how the soundscape changes! 🌍🎧

---

## 🔮 Future Enhancements

- [ ] 🎙️ Voice-based weather assistant (text-to-speech narration)
- [ ] 📍 Auto-detect location via geolocation API
- [ ] 📱 Progressive Web App (PWA) support for mobile installs
- [ ] 🌙 Dark mode / theme customization
- [ ] 📊 7-day extended forecast with trend charts
- [ ] 🧠 Improved AI model for more accurate next-day predictions
- [ ] 🔔 Weather alert notifications (storms, extreme heat, etc.)
- [ ] 🌐 Multi-language support for narration

---

## 🌟 Why AtmosCast AI is Unique

Most weather apps stop at showing numbers and icons. **AtmosCast AI goes further:**

| Traditional Weather Apps | 🌦️ AtmosCast AI |
|---------------------------|------------------|
| Shows temperature & icons only | Shows data **and** lets you *hear* the weather |
| Static, one-way information | Immersive, sensory experience |
| Generic forecast text | AI-generated, human-like narration |
| No emotional connection | Ambient sound creates atmosphere & mood |
| One-size-fits-all UI | Designed for both utility and experience |

> 💡 AtmosCast AI blends **meteorology, AI, and sound design** into one seamless product — making it a standout portfolio project that demonstrates full-stack thinking, creativity, and technical depth.

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

Made with ❤️ and ☕ by **[Your Name]**

</div>
