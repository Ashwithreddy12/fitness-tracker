# 🏋️ Health & Fitness Tracker

A comprehensive fitness tracking application built with React, TypeScript, and Supabase. Track your workouts, meals, and monitor your progress with beautiful charts and analytics.

![Fitness Tracker Dashboard](https://images.pexels.com/photos/4164761/pexels-photo-4164761.jpeg?auto=compress&cs=tinysrgb&w=1200&h=400&fit=crop)


## ✨ Features

- **🔐 User Authentication**: Secure registration and login with JWT tokens
- **💪 Workout Tracking**: Log exercises with duration and calorie tracking
- **🍎 Meal Logging**: Track food intake with detailed nutritional information
- **📊 Progress Analytics**: Visualize your fitness journey with interactive charts
- **📱 Responsive Design**: Works seamlessly on desktop and mobile devices
- **⚡ Real-time Updates**: Data syncs instantly across all components
- **🔍 Food Search**: Built-in nutrition database for easy meal logging
- **🎯 Goal Tracking**: Monitor calorie balance and fitness goals

## 🛠️ Tech Stack

- **Frontend**: React 18, TypeScript, Tailwind CSS
- **Charts**: Recharts for data visualization
- **Icons**: Lucide React
- **Database**: Supabase (PostgreSQL)
- **Authentication**: Supabase Auth with JWT
- **Build Tool**: Vite
- **Styling**: Tailwind CSS with custom design system

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ and npm
- Supabase account (free tier available)

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/health-fitness-tracker.git
cd health-fitness-tracker
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Set Up Supabase

#### Option A: Use the Connect Button (Recommended)
1. Start the development server: `npm run dev`
2. Click "Connect to Supabase" button in the top right
3. Follow the setup wizard

#### Option B: Manual Setup
1. Create a new project at [supabase.com](https://supabase.com)
2. Go to Settings → API in your Supabase dashboard
3. Copy your project URL and anon key
4. Create `.env.local` file:

```env
VITE_SUPABASE_URL=https://your-project-id.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-key-here
```

### 4. Database Setup

The database schema will be automatically created when you first run the application. The migration includes:

- **Users table**: Managed by Supabase Auth
- **Workouts table**: Exercise tracking with calories and duration
- **Meals table**: Food intake with nutritional breakdown
- **Row Level Security**: Ensures users only see their own data

### 5. Start Development Server

```bash
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) to view the application.

## 📱 Application Structure

```
src/
├── components/
│   ├── Auth/           # Login and registration components
│   ├── Dashboard/      # Main dashboard with stats and charts
│   ├── Layout/         # Header and navigation components
│   ├── Meals/          # Meal tracking and food search
│   ├── Progress/       # Analytics and progress charts
│   └── Workouts/       # Workout logging and history
├── contexts/           # React context for authentication
├── lib/               # Supabase client configuration
├── services/          # API service functions
└── types/             # TypeScript type definitions
```

## 🎯 Key Features Overview

### Authentication System
- Secure user registration with email validation
- JWT-based login with persistent sessions
- Protected routes and API calls
- Automatic session management

### Dashboard
- Daily and weekly progress overview
- Interactive charts showing calorie balance
- Quick stats for workouts and nutrition
- Visual progress indicators

### Workout Tracking
- Add workouts with exercise type selection
- Duration tracking with automatic calorie estimation
- Exercise database integration
- Workout history with delete functionality

### Meal & Nutrition Tracking
- Food search with nutrition database
- Detailed macronutrient tracking (protein, carbs, fat)
- Meal categorization (breakfast, lunch, dinner, snack)
- Calorie intake monitoring

### Progress Analytics
- Weekly and monthly progress views
- Calorie balance visualization
- Activity distribution charts
- Trend analysis and averages

## 🔧 Development

### Available Scripts

```bash
npm run dev          # Start development server
npm run build        # Build for production
npm run preview      # Preview production build
npm run lint         # Run ESLint
```

### Environment Variables

Create a `.env.local` file with:

```env
# Supabase Configuration
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key

# Optional: External API Keys
VITE_NUTRITIONIX_APP_ID=your_nutritionix_app_id
VITE_NUTRITIONIX_API_KEY=your_nutritionix_api_key
```

### Database Schema

The application automatically creates these tables:

#### Workouts Table
- `id`: Unique identifier
- `user_id`: Reference to authenticated user
- `name`: Workout name
- `exercise_type`: Type of exercise
- `duration`: Duration in minutes
- `calories_burned`: Estimated calories burned
- `date`: Workout date
- `created_at`: Timestamp

#### Meals Table
- `id`: Unique identifier
- `user_id`: Reference to authenticated user
- `name`: Food/meal name
- `calories`: Total calories
- `protein`: Protein content in grams
- `carbs`: Carbohydrate content in grams
- `fat`: Fat content in grams
- `meal_type`: breakfast, lunch, dinner, or snack
- `date`: Meal date
- `created_at`: Timestamp

## 🌐 API Integration

### Built-in Mock APIs
The application includes mock implementations for:
- **Nutrition API**: Food search and nutritional data
- **Exercise API**: Calorie estimation for different exercises

### External API Integration
For production use, you can integrate with:
- **[Nutritionix API](https://www.nutritionix.com/business/api)**: Comprehensive food database
- **[ExerciseDB API](https://rapidapi.com/justin-WFnsXH_t6/api/exercisedb)**: Exercise information and calorie data
- **[FoodData Central](https://fdc.nal.usda.gov/api-guide.html)**: USDA food composition database

## 🚀 Deployment

### Frontend Deployment

The application is ready for deployment to any static hosting provider:

```bash
npm run build
```

Deploy the `dist` folder to:
- **Vercel**: Connect your GitHub repo for automatic deployments
- **Netlify**: Drag and drop the `dist` folder or connect via Git
- **GitHub Pages**: Use GitHub Actions for automated deployment

### Database Deployment

Supabase handles database hosting automatically. Your database is production-ready with:
- Automatic backups
- SSL encryption
- Row-level security
- Real-time subscriptions

## 🔒 Security Features

- **Row Level Security (RLS)**: Users can only access their own data
- **JWT Authentication**: Secure token-based authentication
- **Input Validation**: All forms include proper validation
- **CORS Protection**: Configured for secure API access
- **Environment Variables**: Sensitive data stored securely

## 🎨 Design System

### Color Palette
- **Primary Blue**: #2563EB (buttons, links, primary actions)
- **Success Green**: #16A34A (positive metrics, success states)
- **Warning Orange**: #EA580C (calories, energy metrics)
- **Error Red**: #DC2626 (errors, delete actions)
- **Neutral Gray**: #6B7280 (text, borders, backgrounds)

### Typography
- **Headings**: Inter font family, bold weights
- **Body Text**: Inter font family, regular weight
- **Code**: Monospace font for technical elements

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

### Development Guidelines

- Follow the existing code structure and naming conventions
- Add TypeScript types for all new features
- Include proper error handling and loading states
- Test on both desktop and mobile devices
- Maintain the existing design system and color palette

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

If you encounter any issues:

1. Check the [Issues](https://github.com/yourusername/health-fitness-tracker/issues) page
2. Create a new issue with detailed description
3. Include error messages and steps to reproduce

## 🙏 Acknowledgments

- [Supabase](https://supabase.com) for the backend infrastructure
- [Tailwind CSS](https://tailwindcss.com) for the styling system
- [Recharts](https://recharts.org) for data visualization
- [Lucide](https://lucide.dev) for the icon system
- [Pexels](https://pexels.com) for stock photography

---

**Built with ❤️ for the fitness community**
