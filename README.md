# AgriTrust AI 🌱
### Human-in-the-Loop Agricultural Decision Support System for Sri Lankan Farmers
AgriTrust AI is a mobile agricultural decision-support application designed to help smallholder farmers make better-informed decisions about **what to grow, market conditions, crop health, and farm management**.
The system combines artificial intelligence, agricultural data, market intelligence, crop-health analysis, farmer feedback, and offline-first functionality into a single mobile platform.
The key research concept behind AgriTrust AI is a **Human-in-the-Loop Reciprocal AI Framework**, where farmers are not only users of AI recommendations but can also provide local observations and feedback that can be used to improve contextual recommendations.
---
## 📌 Project Overview
Smallholder farmers face several challenges including:
- Commodity price volatility
- Climate and weather uncertainty
- Crop suitability problems
- Crop diseases and pests
- Limited access to agricultural information
- Poor internet connectivity in some farming areas
- Lack of transparency in AI-based recommendations
- Mismatch between AI recommendations and local farming experience
Many existing digital agricultural systems provide one-directional recommendations where the farmer receives an AI prediction but has limited ability to provide local context or correct the recommendation.
AgriTrust AI aims to address this problem by combining:
```text
Agricultural Data
       +
Market Intelligence
       +
AI Recommendations
       +
Crop Health Analysis
       +
Farmer Feedback
       +
Offline Support

into a unified mobile application.

⸻

🎯 Research Problem

Smallholder farmers experience income instability due to volatile commodity markets and climate-related agricultural risks.

Existing digital agricultural decision-support systems can also suffer from low adoption when recommendations are opaque, do not adequately account for local conditions, or fail to incorporate farmers’ practical knowledge.

AgriTrust AI therefore investigates how a mobile agricultural decision-support system can combine economic forecasting, agronomic recommendations, crop-health analysis, and reciprocal farmer feedback.

⸻

🔬 Research Gap

The research framework identifies a gap between:

1. Technical research on agricultural forecasting and crop recommendation models
2. Research concerning farmer trust, adoption, and interaction with AI systems

AgriTrust AI addresses this gap by proposing a mobile architecture that combines:

* Commodity price forecasting
* Price anomaly detection
* Soil and crop suitability analysis
* Crop disease diagnosis
* Farmer feedback
* Contextual recommendation calibration
* Offline-first functionality

The central research concept is the Human-in-the-Loop Reciprocal Calibration Framework.

⸻

💡 Proposed Solution

AgriTrust AI is designed as an offline-capable mobile application that provides agricultural decision support through several interconnected modules.

Core system

                  AgriTrust AI
                       │
        ┌──────────────┼──────────────┐
        │              │              │
     Farm AI        Market AI      Crop Health
        │              │              │
        └──────────────┼──────────────┘
                       │
                Farmer Feedback
                       │
                Context Calibration

⸻

⭐ Core Features

1. 🌾 Farm & Crop Recommendation

Farmers can create farms and plots and enter agricultural information such as:

* Soil nitrogen (N)
* Soil phosphorus (P)
* Soil potassium (K)
* Soil pH
* Temperature
* Humidity
* Rainfall/weather information
* Current crop
* Previous crop

The system can then provide crop recommendations based on the available agricultural information.

The recommendation interface is designed to provide explanations rather than only displaying a predicted crop.

Example:

Recommended Crop
Tomato
Confidence
82%
Reasons:
✓ Suitable soil pH
✓ Suitable nutrient levels
✓ Suitable environmental conditions

⸻

2. 📈 Commodity Price Forecasting

The Market Intelligence module is designed to provide:

* Current commodity prices
* Historical prices
* Market comparisons
* 30-day price forecasts
* Price trend visualization

The proposed research model for price forecasting is the:

Temporal Fusion Transformer (TFT)

Conceptual flow:

Historical Market Prices
          ↓
   Temporal Fusion
     Transformer
          ↓
   30-Day Forecast

⸻

3. 🚨 Price Anomaly Detection

AgriTrust AI also proposes an anomaly detection component that can identify unusual price movements.

The proposed model is:

Attention-Boosted LSTM-VAE

Conceptual flow:

Historical Price Data
        ↓
LSTM-VAE
        ↓
Anomaly Detection
        ↓
Normal / Unusual Price

The system can display:

* Anomaly status
* Anomaly score
* Affected date
* Price information
* Explanation

⸻

4. 🤝 Reciprocal Farmer Feedback

This is one of the central research features of AgriTrust AI.

Instead of treating the farmer as a passive receiver of AI predictions, the system allows the farmer to provide local observations.

For example:

AI Recommendation
       ↓
Farmer evaluates recommendation
       ↓
Farmer provides feedback
       ↓
Local observation recorded
       ↓
Context calibration
       ↓
Future recommendation improvement

Possible feedback includes:

* Recommendation is suitable
* Recommendation is not suitable
* Local soil condition
* Pest observations
* Weather observations
* Farmer comments
* Other field conditions

The proposed research framework identifies reciprocal feedback and contextual calibration as a key contribution of the system.

⸻

5. 📷 Crop Disease & Pest Diagnosis

The Crop Health module allows farmers to capture or upload an image of a crop leaf.

Workflow:

Camera / Gallery
       ↓
Image Preview
       ↓
AI Analysis
       ↓
Disease Classification
       ↓
Confidence
       ↓
Suggested Action

The proposed lightweight model approach includes:

MobileNetV3 / lightweight CNN-based image classification

The system is intended to support on-device inference where practical.

⸻

6. 📱 Offline-First Support

Agricultural users may experience limited or unreliable internet connectivity.

AgriTrust AI therefore includes an offline-first architecture using local storage.

The application can locally store information such as:

* Farmer profile
* Farm information
* Plot information
* Soil observations
* Recent recommendations
* Recent market information
* Disease history
* Pending farmer feedback

When connectivity becomes available:

Local SQLite
     ↓
Sync Queue
     ↓
Backend API
     ↓
Server Database

⸻

🧠 AI/ML Architecture

The proposed AI components include:

Function	Proposed Technique
Price forecasting	Temporal Fusion Transformer (TFT)
Price anomaly detection	Attention-Boosted LSTM-VAE
Crop suitability	Stacked Ensemble
Leaf disease classification	Quantized MobileNetV3 CNN
Farmer feedback calibration	Bayesian contextual re-weighting

Important development approach

The initial application will use mock AI services.

For example:

CropRecommendationService
        ↓
MockCropRecommendationService

Later:

CropRecommendationService
        ↓
Real ML Model / API

This allows the mobile application to be developed and tested before the final machine-learning models are integrated.

⸻

🏗️ System Architecture

                    Flutter Mobile App
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
       Farm              Market             Health
        │                  │                  │
        └──────────────────┼──────────────────┘
                           │
                     REST / HTTPS
                           │
                       FastAPI
                           │
             ┌─────────────┼─────────────┐
             │             │             │
          Farm API      Market API    Health API
             │             │             │
             └─────────────┼─────────────┘
                           │
                      PostgreSQL
                           │
                     AI/ML Services

Local mobile storage:

Flutter
   ↓
SQLite
   ↓
Offline Data
   ↓
Sync Queue
   ↓
FastAPI
   ↓
PostgreSQL

⸻

🛠️ Technology Stack

Frontend

* Flutter
* Dart

Backend

* Python
* FastAPI
* REST API

Databases

* PostgreSQL
* SQLite

Authentication

* JWT-based authentication

Machine Learning

* Python
* Temporal Fusion Transformer
* LSTM-VAE
* Ensemble learning
* MobileNetV3
* TensorFlow Lite / TFLite

Version Control

* Git
* GitHub

⸻

📁 Project Structure

agritrust_ai/
│
├── lib/
│   ├── main.dart
│   │
│   ├── core/
│   │   ├── config/
│   │   ├── constants/
│   │   ├── errors/
│   │   ├── network/
│   │   ├── storage/
│   │   ├── theme/
│   │   └── routing/
│   │
│   ├── shared/
│   │   ├── widgets/
│   │   ├── models/
│   │   ├── services/
│   │   └── components/
│   │
│   ├── auth/
│   │
│   ├── home/
│   │
│   ├── farm/
│   │
│   ├── market/
│   │
│   ├── crop_health/
│   │
│   └── profile/
│
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── core/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── services/
│   │   └── ml/
│   │
│   └── requirements.txt
│
├── database/
│   ├── migrations/
│   └── seed/
│
├── test/
│
├── .env.example
├── README.md
└── pubspec.yaml

⸻

👥 Development Team

The project is developed by a three-member team.

Member 1 — Farm Intelligence

Responsible for:

* Farmer profile
* Farm management
* Plot management
* Soil information
* Crop recommendations
* Recommendation explanations
* Farmer feedback
* Farm-related backend services

⸻

Member 2 — Sri Lankan Market Intelligence

Responsible for:

* Commodity management
* Market management
* Market prices
* Historical price charts
* Price forecasting interface
* Price anomaly interface
* Market comparison
* Price alerts
* Market-related backend services

⸻

Member 3 — Crop Health & Platform

Responsible for:

* Authentication
* Crop disease diagnosis
* Disease history
* Offline SQLite
* Synchronization queue
* Shared UI components
* Application navigation
* Shared infrastructure
* Final system integration

⸻

🗄️ Main Database Entities

The planned database includes:

users
farms
plots
soil_observations
crop_recommendations
farmer_feedback
commodities
markets
market_prices
price_forecasts
price_anomalies
disease_diagnoses
sync_queue
notifications

⸻

🔌 API Structure

The backend will expose REST APIs.

Authentication

POST /api/auth/register
POST /api/auth/login
GET  /api/auth/me

Farms

GET  /api/farms
POST /api/farms
GET  /api/farms/{id}

Plots

POST /api/plots
GET  /api/plots/{id}

Soil

POST /api/soil-observations
GET  /api/plots/{id}/soil

Recommendations

POST /api/recommendations
GET  /api/recommendations/{id}
POST /api/recommendations/{id}/feedback

Markets

GET /api/commodities
GET /api/markets
GET /api/prices
GET /api/prices/history
GET /api/forecasts
GET /api/anomalies

Crop Health

POST /api/disease/analyze
GET  /api/disease/history

Synchronization

POST /api/sync

⸻

🔄 Development Strategy

The project will be developed in stages.

Phase 1 — System Foundation

* Flutter project
* FastAPI backend
* Database structure
* Authentication
* Navigation
* Shared models
* API contracts
* Shared UI components

Phase 2 — Feature Development

Three development streams:

             AgriTrust AI
                  │
       ┌──────────┼──────────┐
       ↓          ↓          ↓
      Farm      Market      Health
       │          │          │
   Member 1    Member 2    Member 3

Phase 3 — Integration

Integrate:

* Farm module
* Market module
* Crop Health module
* Authentication
* Offline storage
* Synchronization

Phase 4 — Mock AI Testing

Test the complete application using mock AI services.

Phase 5 — Real ML Integration

Replace mock services with real machine-learning models.

⸻

🤖 AI Service Architecture

AI functionality will use service interfaces.

Example:

CropRecommendationService
        │
        ├── MockCropRecommendationService
        │
        └── RealCropRecommendationService

Similarly:

PriceForecastService
        │
        ├── MockPriceForecastService
        │
        └── TFTPriceForecastService
AnomalyDetectionService
        │
        ├── MockAnomalyDetectionService
        │
        └── LSTMVAEAnomalyService
DiseaseDetectionService
        │
        ├── MockDiseaseDetectionService
        │
        └── TFLiteDiseaseDetectionService

This architecture allows the application interface to remain stable while the underlying AI models are improved.

⸻

📊 Planned Evaluation

The system can eventually be evaluated using both technical and user-centered measurements.

Crop Recommendation

Potential evaluation:

* Accuracy
* Precision
* Recall
* F1-score

Price Forecasting

Potential evaluation:

* MAE
* RMSE
* MAPE

Anomaly Detection

Potential evaluation:

* Precision
* Recall
* F1-score

Disease Classification

Potential evaluation:

* Accuracy
* Precision
* Recall
* F1-score

Human-in-the-Loop Component

The research can evaluate:

* Farmer feedback usefulness
* Recommendation relevance
* Perceived transparency
* User trust
* System usability
* Changes in recommendations after contextual feedback

The effect of reciprocal feedback should be empirically evaluated rather than assumed.

⸻

📚 Planned Datasets

The research framework identifies several potential datasets:

* AGMARKNET / Indonesian Price Center daily price logs
* Multi-regional crop recommendation datasets
* PlantVillage leaf disease dataset
* NASA POWER meteorological data

For the final Sri Lankan implementation, datasets and market-data sources should be selected and validated according to the project’s actual target environment.

⸻

🇱🇰 Sri Lankan Target

The application is intended to be adapted to the Sri Lankan agricultural context.

The market intelligence component will therefore be designed so that market-data providers can be changed without rewriting the application.

Market records should support:

Commodity
Market
District
Date
Price
Unit
Price Type
Source

The application should not treat development/mock prices as real market information.

⸻

🔐 Data & Privacy

The system should follow responsible data-handling practices.

Important principles include:

* Secure authentication
* Password hashing
* JWT-based authorization
* Controlled API access
* Minimal collection of personal information
* Secure handling of farm location information
* Protection of farmer-generated observations
* Clear distinction between real and demo/AI-generated information

⸻

🚧 Future Enhancements

Future versions may investigate:

* Bluetooth agricultural sensors
* NodeMCU/IoT integration
* Multilingual voice interaction
* SMS-based agricultural information
* Cooperative features
* Agricultural input ordering
* Blockchain-based agricultural traceability
* GCN-based IoT cybersecurity
* Drones
* Agricultural robots
* Self-sovereign identity

These features are outside the initial MVP scope.

⸻

🎓 Research Contribution

The proposed research contribution consists of two major aspects.

1. System Artifact

A functional mobile agricultural decision-support application that demonstrates:

* AI-based agricultural recommendations
* Market intelligence
* Crop-health analysis
* Offline-first operation
* Human-in-the-loop interaction

2. Methodological Contribution

An empirical investigation of reciprocal human-in-the-loop feedback and contextual calibration in agricultural AI decision support.

The project will investigate whether allowing farmers to provide local observations and feedback can improve the relevance, transparency, usability, and acceptance of AI-generated recommendations.

The project does not assume that this mechanism improves outcomes; its effectiveness will be evaluated experimentally.

⸻

🧪 Current Development Principle

The project follows a mock-first, ML-later development strategy.

                    UI
                     ↓
              Service Interface
                     ↓
               Mock Service
                     ↓
              Complete System
                     ↓
                Testing
                     ↓
               Real ML Model

This allows the team to develop the complete application architecture before the final machine-learning models are available.

⸻

📜 Project Status

Current Stage: Development / Architecture

Planned MVP

* Flutter application
* User registration/login
* Farmer profile
* Farm management
* Plot management
* Soil data entry
* Crop recommendation interface
* Farmer feedback
* Sri Lankan market interface
* Historical price charts
* Price forecast interface
* Price anomaly interface
* Crop disease camera
* Disease history
* SQLite offline storage
* Synchronization queue
* FastAPI backend
* PostgreSQL database
* Mock AI services

Future ML Integration

* TFT price forecasting
* LSTM-VAE anomaly detection
* Crop suitability model
* MobileNetV3/TFLite disease classification
* Reciprocal feedback calibration model

⸻

👨‍🎓 Academic Project

AgriTrust AI is developed as a university research/software engineering project.

The project combines:

Mobile Application Development + Artificial Intelligence + Agricultural Decision Support + Market Intelligence + Human-in-the-Loop AI

⸻

📄 License

This project currently does not specify an open-source license.

⸻

🌱 AgriTrust AI

AI should support the farmer’s decision — not replace the farmer’s knowledge.

**For the GitHub creation page:** turn **Add README → ON**, create the repository, and GitHub will create the initial `README.md`. After that, you can replace its contents with the above version. The framework's stated title and research objectives are reflected in the README. AgriTrust AI Framework.pdf
