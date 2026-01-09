# 🏠 Bangalore House Price Prediction

A machine learning web application that predicts house prices in Bangalore based on location, square footage, number of bedrooms (BHK), and bathrooms.

## 🚀 Features

- **Interactive Web Interface**: User-friendly HTML/CSS/JavaScript frontend
- **Real-time Predictions**: Get instant price estimates based on property features
- **Location-based Analysis**: Supports multiple Bangalore locations
- **RESTful API**: Flask backend with JSON responses
- **Pre-trained Model**: Uses scikit-learn model trained on Bangalore housing data

## 📁 Project Structure

```
House-Price-Prediction-main/
├── client/                 # Frontend files
│   ├── app.html           # Main HTML interface
│   ├── app.css            # Styling
│   └── app.js             # JavaScript functionality
├── server/                # Backend files
│   ├── artifacts/         # Model and data files
│   │   ├── banglore_home_prices_model.pickle
│   │   └── columns.json
│   ├── server.py          # Flask API server
│   └── util.py            # Utility functions
├── model/                 # Model development
│   ├── Bengaluru_House_Data.csv
│   ├── banglore_home_prices_model.pickle
│   ├── columns.json
│   └── Untitled.ipynb     # Jupyter notebook
└── main.py               # Entry point
```

## 🛠️ Installation & Setup

### Prerequisites
- Python 3.7+
- pip package manager

### Dependencies
```bash
pip install flask numpy scikit-learn pandas
```

### Quick Start
1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd House-Price-Prediction-main
   ```

2. **Start the Flask server**
   ```bash
   cd server
   python server.py
   ```

3. **Open the web interface**
   - Open `client/app.html` in your web browser
   - The server runs on `http://127.0.0.1:5000`

## 🎯 Usage

### Web Interface
1. Enter the **total square footage** of the property
2. Select the number of **bedrooms (BHK)** (1-5)
3. Select the number of **bathrooms** (1-5)
4. Choose the **location** from the dropdown
5. Click **"Estimate Price"** to get the prediction

### API Endpoints

#### Get Available Locations
```http
GET /get_location_names
```
**Response:**
```json
{
  "locations": ["Electronic City", "Rajaji Nagar", ...]
}
```

#### Predict House Price
```http
POST /predict_home_price
```
**Parameters:**
- `total_sqft`: Total square footage (float)
- `location`: Location name (string)
- `bhk`: Number of bedrooms (integer)
- `bath`: Number of bathrooms (integer)

**Response:**
```json
{
  "estimated_price": 85.5
}
```

## 🧠 Model Information

- **Algorithm**: Linear Regression (scikit-learn)
- **Dataset**: Bangalore house prices dataset
- **Features**: Square footage, location, BHK, bathrooms
- **Output**: Price prediction in Lakhs (₹)

## 🔧 Technical Details

### Backend (Flask)
- **server.py**: Main Flask application with API endpoints
- **util.py**: Model loading and prediction utilities
- **CORS enabled**: Allows cross-origin requests from frontend

### Frontend (Vanilla JS)
- **Responsive design**: Works on desktop and mobile
- **AJAX requests**: Real-time communication with backend
- **Form validation**: Ensures valid input data

### Model Artifacts
- **banglore_home_prices_model.pickle**: Trained ML model
- **columns.json**: Feature column mappings for the model

## 🚀 Deployment

For production deployment:
1. Use a production WSGI server (e.g., Gunicorn)
2. Configure nginx for static file serving
3. Update API URLs in `app.js` for production endpoints
4. Set up proper environment variables

## 📊 Sample Predictions

| Location | Sqft | BHK | Bath | Predicted Price |
|----------|------|-----|------|----------------|
| Electronic City | 1000 | 2 | 2 | ~45 Lakhs |
| Rajaji Nagar | 1200 | 3 | 2 | ~65 Lakhs |

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🐛 Known Issues

- Model is trained specifically for Bangalore locations
- Price predictions are estimates and may not reflect current market conditions
- Limited to properties with 1-5 BHK and bathrooms

## 📞 Support

For questions or issues, please open an issue in the repository or contact the maintainers.

---

**Note**: This application is for educational and demonstration purposes. Actual property prices may vary significantly based on market conditions, property condition, and other factors not included in the model.