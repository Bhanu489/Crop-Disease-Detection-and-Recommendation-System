
# 🌱 Plant Pulse: Your Smart Farming Assistant

**Plant Pulse** is a smart web application built to support farmers by providing intelligent crop recommendations, fertilizer suggestions, and plant disease diagnosis through the power of machine learning.

---

## 🚀 Features

- **🌾 Crop Recommendation**  
  Suggests the most suitable crop based on soil nutrients (N, P, K), pH, rainfall, and real-time temperature & humidity using OpenWeatherMap API.

- **🧪 Fertilizer Recommendation**  
  Recommends the best fertilizer based on soil nutrient imbalance for a selected crop, improving crop yield and soil health.

- **🦠 Disease Detection**  
  Uses a deep learning model to detect plant diseases from uploaded leaf images and suggests remedies for early intervention.

---

## 🛠 Technologies Used

### 🔹 Frontend
- HTML
- CSS (Bootstrap, Font Awesome)
- JavaScript

### 🔹 Backend
- **Framework:** Flask (Python)
- **ML Libraries:**  
  - `scikit-learn` (for crop recommendation)  
  - `PyTorch` (for plant disease detection)
- **Others:** NumPy, Pandas

### 🔹 External APIs
- [OpenWeatherMap API](https://openweathermap.org/) – Fetches live temperature and humidity for crop recommendation.

---

## 🧑‍💻 How to Run the Project

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/your-repository-name.git
   cd your-repository-name
   ```

2. **Set Up a Virtual Environment (Optional but Recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Get Your OpenWeatherMap API Key**
   - Sign up at [OpenWeatherMap](https://openweathermap.org/) to get a free API key.
   - Open `config.py` and replace:
     ```python
     API_KEY = "YOUR_API_KEY"
     ```

5. **Run the Flask App**
   ```bash
   python app.py
   ```

6. **Open the Web App**
   - Go to your browser and open:  
     `http://127.0.0.1:5000`

---

## 📁 Project Structure

```
PlantPulse/
├── app.py                     # Main Flask app
├── config.py                  # API key config
├── requirements.txt           # Python dependencies
├── Runtime.txt                # Python runtime version
├── Data/
│   └── fertilizer.csv         # Fertilizer dataset
├── models/
│   ├── plant_disease_model.pth # Disease detection model (ResNet9)
│   └── RandomForest.pkl       # Crop recommendation model
├── static/
│   ├── css/
│   │   ├── bootstrap.css
│   │   ├── font-awesome.min.css
│   │   └── style.css
│   └── js/
│       └── cities.js
├── templates/
│   ├── crop.html
│   ├── crop-result.html
│   ├── disease.html
│   ├── disease-result.html
│   ├── fertilizer.html
│   ├── fertilizer-result.html
│   ├── index.html
│   ├── layout.html
│   └── try_again.html
└── utils/
    ├── disease.py             # Disease information
    ├── fertilizer.py          # Fertilizer recommendation logic
    └── model.py               # ResNet9 model definition
```

---

## 🧠 How It Works

### 1. 🌾 Crop Recommendation
- Input: N, P, K, pH, rainfall, and city name.
- Weather data (temperature, humidity) is fetched from OpenWeatherMap.
- Features are passed to a Random Forest model (`RandomForest.pkl`) to predict the optimal crop.

### 2. 🧪 Fertilizer Recommendation
- Input: N, P, K values and selected crop.
- The system compares current values to ideal levels from `fertilizer.csv` and suggests adjustments.

### 3. 🦠 Disease Detection
- Input: Leaf image upload.
- Image is processed and classified using a deep learning ResNet9 model (`plant_disease_model.pth`).
- Information about the disease and remedies is shown using `disease.py`.

---

## 📬 Contributing

Feel free to fork this project and submit a pull request. Contributions are welcome!

---

## 📄 License

This project is licensed under the MIT License.

---

## 💡 Acknowledgments

- [OpenWeatherMap](https://openweathermap.org/)
- scikit-learn & PyTorch communities
