# Medication Management System

A comprehensive medication tracking application designed for both patients and caretakers to manage medication schedules, track adherence, and monitor medication intake.

## Features

### Core Features
- **Secure Authentication**: User registration and login with SQLite database
- **Role-Based Access**: Separate dashboards for patients and caretakers
- **Medication Management**: Complete CRUD operations for medications
- **Adherence Tracking**: Monitor medication intake and calculate adherence rates
- **Real-Time Updates**: Live updates when medications are marked as taken
- **Responsive Design**: Works seamlessly on desktop and mobile devices

### Patient Features
- Add, edit, and delete personal medications
- Mark medications as taken with timestamps
- View adherence statistics and progress
- Track medication history and activity logs
- Receive visual feedback for missed medications

### Caretaker Features
- Manage medications for multiple patients
- Monitor patient adherence rates
- Track missed medications with alerts
- View comprehensive patient activity logs
- Assist patients with medication management

## Technology Stack

### Frontend
- **React 18** with TypeScript
- **Tailwind CSS** for styling
- **React Router** for navigation
- **Lucide React** for icons
- **date-fns** for date manipulation
- **Vite** for build tooling

### Backend
- **Node.js** with Express
- **SQLite** database
- **bcrypt** for password hashing
- **jsonwebtoken** for authentication
- **express-validator** for input validation
- **helmet** for security headers
- **cors** for cross-origin requests

## Installation & Setup

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn package manager

### Backend Setup

1. Navigate to the backend directory and install dependencies:
```bash
cd backend
npm install
```

2. Start the backend server:
```bash
npm run dev
```

The backend server will run on `http://localhost:3001`

### Frontend Setup

1. Install frontend dependencies:
```bash
npm install
```

2. Start the development server:
```bash
npm run dev
```

The frontend will run on `http://localhost:5173`

## Usage

### Getting Started

1. **Registration**: Create a new account by selecting either "Patient" or "Caretaker" role
2. **Login**: Sign in with your email and password
3. **Dashboard**: Access your role-specific dashboard with relevant features

### For Patients

1. **Add Medications**: Click "Add Medication" to create new medication entries
2. **Track Intake**: Mark medications as taken using the "Mark as Taken" button
3. **Monitor Progress**: View your adherence rate and medication statistics
4. **Review History**: Check your medication activity log for past entries

### For Caretakers

1. **Manage Patient Medications**: Add and edit medications for patients under your care
2. **Monitor Adherence**: Track patient medication adherence rates
3. **Handle Alerts**: Respond to missed medication notifications
4. **Review Activity**: Monitor patient medication activity and compliance

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login

### Medications
- `GET /api/medications` - Get user medications
- `POST /api/medications` - Add new medication
- `PUT /api/medications/:id` - Update medication
- `DELETE /api/medications/:id` - Delete medication
- `POST /api/medications/:id/taken` - Mark medication as taken
- `GET /api/medications/logs` - Get medication logs
- `GET /api/medications/adherence` - Get adherence statistics

## Testing

Run the test suite:
```bash
npm test
```

The application includes tests for:
- Component rendering and functionality
- Authentication context and user management
- Utility functions and validation logic

## Database Schema

### Users Table
- `id` - Primary key
- `email` - Unique user email
- `password_hash` - Hashed password
- `first_name` - User's first name
- `last_name` - User's last name
- `role` - User role (patient/caretaker)
- `created_at` - Account creation timestamp
- `updated_at` - Last update timestamp

### Medications Table
- `id` - Primary key
- `user_id` - Foreign key to users table
- `name` - Medication name
- `dosage` - Medication dosage
- `frequency` - How often to take
- `instructions` - Additional instructions
- `start_date` - When to start taking
- `end_date` - When to stop taking (optional)
- `is_active` - Whether medication is active
- `created_at` - Creation timestamp
- `updated_at` - Last update timestamp

### Medication Logs Table
- `id` - Primary key
- `medication_id` - Foreign key to medications table
- `user_id` - Foreign key to users table
- `taken_at` - When medication was taken
- `notes` - Optional notes
- `created_at` - Log creation timestamp

## Security Features

- Password hashing with bcrypt
- JWT token-based authentication
- Input validation and sanitization
- Rate limiting to prevent abuse
- Security headers with Helmet
- SQL injection protection
- CORS configuration

## Development Notes

### Code Organization
- Modular component structure
- Separate contexts for state management
- Custom hooks for data fetching
- Reusable utility functions
- Comprehensive error handling

### Performance Considerations
- Optimized re-renders with React hooks
- Efficient data loading strategies
- Responsive design for all devices
- Minimal bundle size with tree shaking

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Ensure all tests pass
6. Submit a pull request

## License

This project is licensed under the MIT License.