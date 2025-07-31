🌍 Travel Recommendation System
An AI-powered travel planner that delivers personalized destination suggestions based on your interests, location, weather, and real-time events. The system combines deep learning (RBM) with real-time data integration to ensure smart, contextual, and dynamic travel recommendations.

✨ Key Features
🎯 Personalized Recommendations

Learns user preferences using Restricted Boltzmann Machines (RBM)

Ranks destinations by user profile + contextual data

🔍 Filter Options

Travel mode (Driving, Walking, Transit)

Category preferences (Food, Trekking, Nightlife, etc.)

Minimum rating & max distance

☁️ Real-Time Weather & Forecast (OpenWeatherMap)

🎉 Event Discovery near your city (Eventbrite)

🧭 Trekking Spots via OpenStreetMap + Wikipedia

📚 Destination Insights from Wikipedia summaries

🧾 Itinerary Builder to plan and save selected destinations

🧠 Machine Learning
The core engine uses Restricted Boltzmann Machines (RBM) for collaborative filtering:

🔗 User-Destination Matrix: Learns hidden features from past user selections

🧩 Latent Factor Extraction: Captures nuanced preferences (e.g., nature + hiking + low crowd)

❄️ Cold Start Solution: Hybrid fallback with content-based logic

📈 Score Fusion: ML scores enhanced using travel time, rating, season, and context

The ML pipeline is modular and built in Python (TensorFlow + Pandas). It adapts continuously as new preferences are submitted.

🛠 Tech Stack
Layer	Technology
Frontend	React.js, CSS
Backend	Flask (Python), Flask-CORS
ML Engine	TensorFlow, Pandas, NumPy
APIs Used	Google Maps, OpenWeatherMap, Eventbrite, Overpass API, Wikipedia
Styling	Responsive Custom CSS
State Mgmt	React Hooks
Deployment	Localhost / Docker
Security	.env-based API key handling

🧩 Folder Structure
bash
Copy
Edit
travel-recommendation/
├── backend/
│   ├── app.py              # Flask backend + ML integration
│   ├── ml/
│   │   └── recommender.py  # RBM model + scoring engine
│   ├── .env                # API credentials
├── frontend/
│   ├── src/
│   │   └── App.js          # React frontend
│   └── public/
└── README.md
🚀 Getting Started
📦 Backend
bash
Copy
Edit
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
Create a .env file:

env
Copy
Edit
GOOGLE_MAPS_API_KEY=your_key
OPENWEATHER_API_KEY=your_key
EVENTBRITE_API_KEY=your_key
Run backend server:

bash
Copy
Edit
python app.py
💻 Frontend
bash
Copy
Edit
cd frontend
npm install
npm start
Visit: http://localhost:3000

🔄 Recommendation Flow
User selects city + preferences

Flask backend:

Gets coordinates (Google Geocoding)

Retrieves destinations (Google Places / Overpass API)

Gets weather + forecast (OpenWeather)

Fetches events (Eventbrite)

Extracts Wikipedia summaries

RBM model ranks destinations using:

User latent features

Travel time, rating, season, reviews

Frontend displays top N destinations + weather/events

User adds selected places to itinerary

🧠 Scoring Logic
python
Copy
Edit
score = rbm_score + (rating * 10) + (reviews * 0.01) - (travel_time * 0.5)
if category in user_preferences:
    score += 1.0
rbm_score is the personalized recommendation probability from the RBM model

Fallback logic used for cold start or sparse input

📈 Live Preview (Optional Screenshots)
🔍 Filter form (city, preferences, rating)

🧭 Trekking / Event cards

📋 Smart itinerary section

🌦️ Weather + Forecast cards

👨‍💻 Author
Saket Zanwar
💼 GitHub • LinkedIn

📄 License
MIT License – free for use and adaptation.
