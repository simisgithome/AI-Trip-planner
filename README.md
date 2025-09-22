# AI Trip Planner

An intelligent travel planning application that uses Google Cloud Vertex AI to generate personalized trip itineraries based on user preferences, budget, and interests.

## 🌟 Features

- **AI-Powered Itinerary Generation**: Leverages Google Cloud Vertex AI to create detailed, personalized travel plans
- **Interactive Trip Form**: Easy-to-use interface for collecting user preferences
- **Detailed Daily Plans**: Day-by-day activities with times, costs, and descriptions
- **Smart Recommendations**: Restaurant, accommodation, and transportation suggestions
- **Budget Tracking**: Estimated costs for activities and overall trip budget
- **Responsive Design**: Works seamlessly on desktop and mobile devices

## 🏗️ Architecture

```
AI-Trip-Planner/
│
├─ frontend/          # React.js frontend application
│   ├─ components/    # Reusable UI components
│   ├─ screens/       # Main application screens
│   └─ App.js         # Main app component
│
├─ backend/           # Node.js/Express.js backend
│   ├─ routes/        # API route definitions
│   ├─ controllers/   # Business logic controllers
│   └─ server.js      # Express server setup
│
├─ ai-engine/         # Python AI integration
│   └─ itinerary-generator.py  # Vertex AI integration
│
└─ database/          # Database schema documentation
    └─ schema.md      # Firestore/PostgreSQL schemas
```

## 🚀 Getting Started

### Prerequisites

- Node.js (v16 or higher)
- Python (v3.8 or higher)
- Google Cloud Platform account (for Vertex AI)
- npm or yarn package manager

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd AI-Trip-Planner
   ```

2. **Install backend dependencies**
   ```bash
   npm install
   ```

3. **Install frontend dependencies**
   ```bash
   cd frontend
   npm install
   cd ..
   ```

4. **Install Python dependencies**
   ```bash
   cd ai-engine
   pip install -r requirements.txt
   cd ..
   ```

5. **Set up Google Cloud credentials**
   ```bash
   # Set environment variables
   export GOOGLE_CLOUD_PROJECT_ID=your-project-id
   export GOOGLE_CLOUD_REGION=us-central1
   
   # Or create a .env file in the root directory
   echo "GOOGLE_CLOUD_PROJECT_ID=your-project-id" > .env
   echo "GOOGLE_CLOUD_REGION=us-central1" >> .env
   ```

### Running the Application

1. **Start the backend server**
   ```bash
   npm run start:backend
   # or
   node backend/server.js
   ```

2. **Start the frontend development server**
   ```bash
   npm run start:frontend
   # or
   cd frontend && npm start
   ```

3. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:3001
   - Health check: http://localhost:3001/health

## 🔧 Configuration

### Environment Variables

Create a `.env` file in the root directory with the following variables:

```env
# Google Cloud Configuration
GOOGLE_CLOUD_PROJECT_ID=your-project-id
GOOGLE_CLOUD_REGION=us-central1

# Server Configuration
PORT=3001
NODE_ENV=development

# Database Configuration (optional)
DATABASE_URL=your-database-url
```

### Google Cloud Setup

1. **Create a Google Cloud Project**
   - Go to [Google Cloud Console](https://console.cloud.google.com)
   - Create a new project or select existing one

2. **Enable Vertex AI API**
   ```bash
   gcloud services enable aiplatform.googleapis.com
   ```

3. **Set up authentication**
   ```bash
   gcloud auth application-default login
   ```

## 📡 API Documentation

### Endpoints

#### Generate Itinerary
```
POST /api/itinerary
```

**Request Body:**
```json
{
  "destination": "Paris, France",
  "startDate": "2025-03-15",
  "endDate": "2025-03-20",
  "budget": 2500,
  "travelers": 2,
  "interests": ["culture", "food", "art"],
  "preferences": "Romantic getaway, museums, fine dining"
}
```

**Response:**
```json
{
  "id": 1,
  "destination": "Paris, France",
  "duration": 5,
  "estimatedBudget": 2800,
  "dailyPlans": [...],
  "recommendations": {...},
  "createdAt": "2025-01-15T10:30:00Z"
}
```

#### Get Itinerary
```
GET /api/itinerary/:id
```

#### Update Itinerary
```
PUT /api/itinerary/:id
```

#### Delete Itinerary
```
DELETE /api/itinerary/:id
```

## 🧪 Testing

### Backend Tests
```bash
npm run test:backend
```

### Frontend Tests
```bash
npm run test:frontend
```

### AI Engine Tests
```bash
cd ai-engine
python -m pytest tests/
```

## 🚢 Deployment

### Docker Deployment
```bash
# Build and run with Docker Compose
docker-compose up --build
```

### Google Cloud Deployment
```bash
# Deploy to Google Cloud Run
gcloud run deploy ai-trip-planner \
  --source . \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated
```

### Traditional Hosting
1. Build the frontend: `npm run build:frontend`
2. Set `NODE_ENV=production`
3. Start the server: `npm start`

## 🛠️ Development

### Project Structure

- **Frontend**: React.js with hooks for state management
- **Backend**: Express.js with RESTful API design
- **AI Engine**: Python with Google Cloud Vertex AI integration
- **Database**: Supports both Firestore and PostgreSQL

### Adding New Features

1. **Frontend Components**: Add to `frontend/components/`
2. **API Routes**: Add to `backend/routes/`
3. **AI Functionality**: Extend `ai-engine/itinerary-generator.py`
4. **Database Schema**: Update `database/schema.md`

### Code Style

- **JavaScript**: ESLint + Prettier
- **Python**: Black + Flake8
- **Commits**: Conventional Commits format

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/new-feature`
3. Commit changes: `git commit -m 'feat: add new feature'`
4. Push to branch: `git push origin feature/new-feature`
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- **Documentation**: Check the `/docs` folder for detailed guides
- **Issues**: Report bugs via GitHub Issues
- **Discussions**: Use GitHub Discussions for questions

## 🙏 Acknowledgments

- Google Cloud Vertex AI for AI capabilities
- React.js community for frontend framework
- Express.js for backend framework
- All contributors and beta testers

## 📊 Roadmap

- [ ] User authentication and profiles
- [ ] Social sharing of itineraries
- [ ] Mobile app development
- [ ] Integration with booking platforms
- [ ] Offline mode support
- [ ] Multi-language support
- [ ] Advanced budget tracking
- [ ] Weather integration
- [ ] Real-time collaboration

---

**Happy Travels! 🌍✈️**