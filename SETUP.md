# 🚀 Chinku Chai Setup Guide

## Prerequisites
- Node.js v16+ ([Download](https://nodejs.org/))
- PostgreSQL ([Download](https://www.postgresql.org/download/))
- Stripe Account ([Sign up](https://stripe.com))
- Git ([Download](https://git-scm.com/))

## Quick Start

### 1️⃣ Clone Repository
```bash
git clone https://github.com/Abisheks802/chinku-chai.git
cd chinku-chai
```

### 2️⃣ Backend Setup

```bash
cd backend

# Install dependencies
npm install

# Create .env file
cp .env.example .env

# Edit .env with your configuration
# - Database credentials
# - JWT secret
# - Stripe keys

# Run migrations (setup database tables)
npm run migrate

# Seed database with sample products
npm run seed

# Start development server
npm run dev
```

The backend will run on `http://localhost:5000`

### 3️⃣ Frontend Setup (in a new terminal)

```bash
cd frontend

# Install dependencies
npm install

# Create .env file
cp .env.example .env

# Edit .env with API URL
# REACT_APP_API_URL=http://localhost:5000

# Start development server
npm start
```

The frontend will run on `http://localhost:3000`

## 📋 Configuration

### Backend .env Setup
```env
NODE_ENV=development
PORT=5000

# PostgreSQL Database
DB_HOST=localhost
DB_PORT=5432
DB_NAME=chinku_chai
DB_USER=postgres
DB_PASSWORD=your_secure_password

# JWT Secret (use a strong random string)
JWT_SECRET=your_super_secret_jwt_key_generate_a_random_string_here

# Stripe Keys (from your Stripe dashboard)
STRIPE_SECRET_KEY=sk_test_your_key_here
STRIPE_PUBLISHABLE_KEY=pk_test_your_key_here
```

### Frontend .env Setup
```env
REACT_APP_API_URL=http://localhost:5000
REACT_APP_STRIPE_PUBLIC_KEY=pk_test_your_key_here
REACT_APP_ENV=development
```

## 🗄️ Database Setup

### Create PostgreSQL Database
```bash
# Connect to PostgreSQL
psql -U postgres

# Create database
CREATE DATABASE chinku_chai;

# Exit
\q
```

### Run Migrations
```bash
cd backend
npm run migrate
```

### Seed Sample Data
```bash
npm run seed
```

This will add:
- 4 premium CTC tea products
- Sample admin user (if needed)

## 🧪 Testing

### Test Backend API
```bash
# Health check
curl http://localhost:5000/api/health

# Get products
curl http://localhost:5000/api/products
```

### Test Frontend
Visit `http://localhost:3000` in your browser

## 📦 Project Structure

```
chinku-chai/
├── backend/
│   ├── src/
│   │   ├── index.ts          # Express server
│   │   ├── routes/           # API endpoints
│   │   └── database/         # Database setup
│   ├── package.json
│   ├── tsconfig.json
│   └── .env.example
├── frontend/
│   ├── src/
│   │   ├── App.tsx           # Main app
│   │   ├── pages/            # React pages
│   │   ├── components/       # Reusable components
│   │   ├── store/            # Redux store
│   │   └── index.css         # Styles
│   ├── public/
│   ├── package.json
│   ├── tailwind.config.js
│   └── .env.example
├── README.md
├── SETUP.md
└── .gitignore
```

## 🛠️ Available Commands

### Backend
```bash
npm run dev      # Development server
npm run build    # Build TypeScript
npm run start    # Production server
npm run migrate  # Run database migrations
npm run seed     # Seed sample data
npm run lint     # Lint code
```

### Frontend
```bash
npm start        # Development server
npm run build    # Production build
npm run test     # Run tests
npm run eject    # Eject from create-react-app
```

## 🔗 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `POST /api/auth/logout` - Logout user

### Products
- `GET /api/products` - Get all products
- `GET /api/products/:id` - Get product details

### Cart
- `GET /api/cart` - Get user cart
- `POST /api/cart` - Add to cart
- `PUT /api/cart/:id` - Update cart item
- `DELETE /api/cart/:id` - Remove from cart

### Orders
- `POST /api/orders` - Create order
- `GET /api/orders` - Get user orders
- `GET /api/orders/:id` - Get order details

## 📚 Technology Stack

- **Frontend**: React 18, TypeScript, Tailwind CSS, Redux Toolkit
- **Backend**: Node.js, Express, TypeScript, PostgreSQL
- **Authentication**: JWT (JSON Web Tokens)
- **Payments**: Stripe API
- **Styling**: Tailwind CSS

## 🐛 Troubleshooting

### Database Connection Error
```bash
# Check PostgreSQL is running
# macOS
brew services list

# Windows
# Check Services in System Settings

# Test connection
psql -U postgres -d chinku_chai
```

### Port Already in Use
```bash
# Backend on different port
PORT=5001 npm run dev

# Frontend on different port
PORT=3001 npm start
```

### Dependencies Issues
```bash
# Clear node_modules and reinstall
rm -rf node_modules package-lock.json
npm install
```

## 📧 Support

For issues or questions:
1. Check existing GitHub issues
2. Create a new GitHub issue with details
3. Include error messages and logs

## 📄 License

MIT License - Free to use for personal and commercial projects

## 🎯 Next Steps

- [ ] Implement complete authentication API
- [ ] Build payment processing with Stripe
- [ ] Add product filtering and search
- [ ] Create admin dashboard
- [ ] Set up email notifications
- [ ] Deploy to production

---

**Happy brewing with Chinku Chai! ☕**
