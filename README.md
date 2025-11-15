# ServiMap

A comprehensive platform for finding and connecting with local service providers. Built with React, Node.js, Express, and Prisma.

## Features

- **Interactive Map**: Find services near you with an intuitive map interface
- **User Authentication**: Secure login and registration system
- **Service Listings**: Browse and create service listings by category
- **Real-time Messaging**: Communicate with service providers
- **Provider Profiles**: Detailed profiles with ratings and reviews
- **Admin Dashboard**: Complete administrative control
- **Multi-language Support**: English and Spanish translations
- **Responsive Design**: Works on desktop and mobile devices

## Tech Stack

### Backend
- **Node.js** with Express.js
- **Prisma** ORM with PostgreSQL
- **JWT** authentication
- **bcrypt** password hashing
- **Winston** logging
- **Socket.io** real-time messaging
- **Rate limiting** and security middleware

### Frontend
- **React** with Material-UI
- **Leaflet** interactive maps
- **Axios** HTTP client
- **i18next** internationalization
- **React Router** navigation

## Getting Started

### Prerequisites
- Node.js (v16 or higher)
- PostgreSQL database
- npm or yarn

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/servimap.git
   cd servimap
   ```

2. **Backend Setup**
   ```bash
   cd backend
   npm install
   cp .env.example .env
   # Edit .env with your database URL and other settings
   npx prisma migrate dev
   npx prisma db seed
   npm run dev
   ```

3. **Frontend Setup**
   ```bash
   cd frontend
   npm install
   npm start
   ```

4. **Open your browser**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:4000

## Environment Variables

### Backend (.env)
```env
DATABASE_URL="postgresql://username:password@localhost:5432/servimap_db"
JWT_SECRET="your-secret-key"
JWT_ACCESS_EXPIRE="15m"
JWT_REFRESH_EXPIRE="7d"
NODE_ENV="development"
PORT=4000
FRONTEND_URL="http://localhost:3000"
SMTP_HOST="smtp.gmail.com"
SMTP_PORT=587
SMTP_USER="your-email@gmail.com"
SMTP_PASS="your-app-password"
```

### Frontend (.env)
```env
REACT_APP_API_URL="http://localhost:4000/api"
```

## Database Schema

The application uses Prisma ORM with the following main models:
- **User**: Authentication and user profiles
- **ProviderProfile**: Extended information for service providers
- **ServiceListing**: Service offerings with location data
- **Message**: Real-time messaging system
- **Review**: User reviews and ratings
- **AuditLog**: Administrative logging

## API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/refresh` - Refresh access token
- `POST /api/auth/logout` - User logout

### Users
- `GET /api/users/me` - Get current user profile
- `PUT /api/users/me` - Update user profile
- `PUT /api/users/change-password` - Change password

### Listings
- `GET /api/listings/search` - Search service listings
- `GET /api/listings/:id` - Get listing details
- `POST /api/listings` - Create new listing (providers only)
- `PUT /api/listings/:id` - Update listing
- `DELETE /api/listings/:id` - Delete listing

### Messages
- `GET /api/messages/conversations` - Get user conversations
- `GET /api/messages/conversations/:id` - Get conversation messages
- `POST /api/messages` - Send message

### Admin (Admin only)
- `GET /api/admin/stats` - Dashboard statistics
- `GET /api/admin/users` - User management
- `GET /api/admin/listings` - Listing management
- `GET /api/admin/reports` - Report management

## Testing Accounts

After running the database seed, you can use these test accounts:

- **Admin**: admin@servimap.com / admin123
- **Provider**: provider@servimap.com / provider123
- **Client**: client@servimap.com / client123
- **Sample Providers**: [name]@servimap.com / test123

## Project Structure

```
servimap/
├── backend/
│   ├── prisma/
│   │   ├── schema.prisma
│   │   └── seed.js
│   ├── src/
│   │   ├── middleware/
│   │   ├── routes/
│   │   └── server.js
│   ├── package.json
│   └── .env.example
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── context/
│   │   ├── services/
│   │   └── i18n/
│   └── package.json
└── README.md
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, email support@servimap.com or create an issue in the repository.
