# Maternal Food Recommendation AI

An AI-powered web application for providing personalized food recommendations and nutrition guidance to pregnant women.

## Features

### 🤖 AI Chatbot
- Ask questions about food safety during pregnancy
- Get instant answers about benefits, precautions, and preparation methods
- Trimester-specific recommendations
- Natural language understanding using BERT and FLAN-T5 (optional)

### 📅 Meal Plan Generator
- Generate personalized meal plans (1-30 days)
- Filter by region (North Indian, South Indian, etc.)
- Support for vegetarian, non-vegetarian, and vegan diets
- Daily nutrition summaries
- Variety-based meal selection

### ⭐ Food Recommendations
- Personalized recommendations based on trimester
- Safety checks for health conditions
- Nutritional scoring system
- Category-based meal suggestions

### 📊 Database
- 15+ Indian foods with detailed nutrition information
- Regional origins and preparation tips
- Trimester-specific suitability
- Health benefits and precautions

## Installation

1. Clone the repository:
```bash
git clone https://github.com/tejaslakshmangith/ishuproject.git
cd ishuproject
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Initialize the database:
```bash
python seed_data.py
```

5. Run the application:
```bash
python app.py
```

6. Visit http://localhost:5000 in your browser

## Usage

### First Time Setup
1. Register a new account at `/auth/register`
2. Provide your due date (optional) to calculate trimester
3. Set dietary preferences (vegetarian/non-vegetarian/vegan)

### Using the Chatbot
1. Navigate to `/chatbot`
2. Ask questions like:
   - "Can I eat papaya during pregnancy?"
   - "What are the benefits of spinach?"
   - "How much milk should I drink daily?"

### Generating Meal Plans
1. Navigate to `/meal-plans`
2. Select number of days (1-30)
3. Choose regional preference (optional)
4. Select diet type (optional)
5. Click "Generate Meal Plan"

## Project Structure

```
ishuproject/
├── app.py                  # Main Flask application
├── config.py              # Application configuration
├── seed_data.py           # Database seeder
├── test_app.py            # Test script
├── ai_engine/             # AI/ML modules
│   ├── chatbot.py         # AI chatbot (BERT + FLAN-T5)
│   ├── meal_planner.py    # Meal plan generator
│   ├── recommender.py     # Food recommendation engine
│   └── nutritional_analyzer.py
├── models/                # Database models
│   ├── user.py
│   ├── food.py
│   ├── recommendation.py
│   └── interaction.py
├── routes/                # Flask blueprints
│   ├── auth.py
│   ├── chatbot.py
│   ├── meal_plans.py
│   ├── foods.py
│   ├── recommendations.py
│   └── interactions.py
├── templates/             # HTML templates
│   ├── base.html
│   ├── index.html
│   ├── auth/
│   └── dashboard/
└── utils/                 # Utility functions
```

## Testing

Run the test script to verify all functionality:
```bash
python test_app.py
```

This will test:
- Chatbot functionality
- Meal plan generation
- Database seeding
- Preferences API

## AI Models (Optional)

The chatbot can work in two modes:
1. **Fallback mode** (default): Uses rule-based intent classification and template-based responses
2. **AI mode**: Uses BERT for query understanding and FLAN-T5 for response generation

To enable AI mode, install the transformer dependencies:
```bash
pip install transformers torch sentencepiece protobuf accelerate
```

Note: AI models require significant disk space and memory. The application works perfectly fine in fallback mode.

## API Endpoints

### Chatbot
- `GET /chatbot` - Chatbot interface
- `POST /chatbot/api/ask` - Ask a question
- `GET /chatbot/api/suggestions` - Get suggested questions
- `GET /chatbot/api/history` - Get chat history

### Meal Plans
- `GET /meal-plans` - Meal plan generator interface
- `POST /meal-plans/api/generate` - Generate meal plan
- `GET /meal-plans/api/preferences` - Get available preferences

### Authentication
- `GET /auth/register` - Registration page
- `POST /auth/register` - Create account
- `GET /auth/login` - Login page
- `POST /auth/login` - Authenticate
- `GET /auth/logout` - Logout

## Technology Stack

- **Backend**: Flask 3.0
- **Database**: SQLAlchemy with SQLite
- **Authentication**: Flask-Login + Flask-Bcrypt
- **AI/ML**: transformers, torch (optional)
- **Frontend**: Bootstrap 5, jQuery
- **Icons**: Font Awesome

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License.

## Disclaimer

This application provides general nutritional information and should not replace professional medical advice. Always consult with your healthcare provider for personalized guidance during pregnancy.