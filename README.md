# Hotel Management System

A comprehensive hotel management system built with Laravel (backend) and React (frontend).

## Features

### User Roles
- **Manager**: Full system access, reports, user management, pricing
- **Receptionist**: Check-in/out, room assignment, guest management
- **Reservation Agent**: Create/modify reservations, handle bookings
- **Guest**: View/make reservations, order food/drinks

### Core Functionality
- Room reservation and availability checking
- Multiple room types (Single, Double, Suite)
- Check-in/Check-out management
- Room status tracking (available, occupied, dirty, maintenance)
- Payment processing (cash, card, online via payment gateway)
- Food & beverage menu with categories:
  - Food
  - Soft Drinks
  - Alcoholic Drinks
- Order management
- Reports & Analytics:
  - Occupancy rate
  - Revenue tracking
  - Average Daily Rate (ADR)
  - No-show statistics
- User management
- Seasonal pricing and promotions

## Tech Stack

### Backend
- Laravel 12
- MySQL (XAMPP)
- Laravel Sanctum (API authentication)

### Frontend
- React
- React Router
- Axios

## Installation

### Prerequisites
- PHP 8.2+
- Composer
- Node.js & npm
- XAMPP (MySQL)

### Backend Setup

1. Navigate to backend directory:
```bash
cd hotel-management-backend
```

2. Install dependencies:
```bash
composer install
```

3. Create database in XAMPP:
- Start XAMPP and run MySQL
- Create database named `hotel_management`

4. Configure environment:
- The `.env` file is already configured for XAMPP
- Database settings:
  - DB_CONNECTION=mysql
  - DB_HOST=127.0.0.1
  - DB_PORT=3306
  - DB_DATABASE=hotel_management
  - DB_USERNAME=root
  - DB_PASSWORD=

5. Run migrations and seed data:
```bash
php artisan migrate:fresh --seed
```

6. Start Laravel server:
```bash
php artisan serve
```

Backend will run on `http://localhost:8000`

### Frontend Setup

1. Navigate to frontend directory:
```bash
cd hotel-management-frontend
```

2. Install dependencies:
```bash
npm install
```

3. Start development server:
```bash
npm start
```

Frontend will run on `http://localhost:3000`

## Default Users

After seeding, you can login with:

- **Manager**
  - Email: manager@hotel.com
  - Password: password

- **Receptionist**
  - Email: receptionist@hotel.com
  - Password: password

- **Reservation Agent**
  - Email: agent@hotel.com
  - Password: password

- **Guest**
  - Email: guest@hotel.com
  - Password: password

## Database Structure

### Main Tables
- `roles` - User roles and permissions
- `users` - System users (staff and guests)
- `room_types` - Room categories with pricing
- `rooms` - Individual room inventory
- `reservations` - Booking records
- `payments` - Payment transactions
- `menu_categories` - Food/drink categories
- `menu_items` - Menu items
- `orders` - Food/drink orders
- `order_items` - Order details
- `pricing_rules` - Seasonal pricing and promotions

## API Endpoints

### Authentication
- POST `/api/register` - Register new user
- POST `/api/login` - Login
- POST `/api/logout` - Logout
- GET `/api/me` - Get current user

### Reservations
- GET `/api/reservations` - List reservations
- POST `/api/reservations` - Create reservation
- PUT `/api/reservations/{id}` - Update reservation
- DELETE `/api/reservations/{id}` - Cancel reservation
- POST `/api/reservations/check-availability` - Check room availability

### Rooms
- GET `/api/rooms` - List all rooms
- GET `/api/room-types` - List room types
- PUT `/api/rooms/{id}` - Update room status

### Menu & Orders
- GET `/api/menu/categories` - Get menu categories
- GET `/api/menu/items` - Get menu items
- POST `/api/orders` - Create order

### Payments
- POST `/api/payments` - Process payment
- POST `/api/payments/{id}/refund` - Refund payment

### Reports (Manager only)
- GET `/api/reports/occupancy` - Occupancy rate
- GET `/api/reports/revenue` - Revenue report
- GET `/api/reports/adr` - Average Daily Rate
- GET `/api/reports/no-shows` - No-show statistics

### Users (Manager only)
- GET `/api/users` - List users
- POST `/api/users` - Create user
- PUT `/api/users/{id}` - Update user
- DELETE `/api/users/{id}` - Deactivate user

## Payment Gateway Integration

The system includes a payment gateway simulation. For production:
1. Integrate with Stripe, PayPal, or other payment providers
2. Update `PaymentController::processWithGateway()` method
3. Add proper PCI compliance measures
4. Implement 3D Secure authentication

## Usage

1. Start XAMPP and ensure MySQL is running
2. Start Laravel backend: `php artisan serve`
3. Start React frontend: `npm start`
4. Access the application at `http://localhost:3000`
5. Login with one of the default users
6. Navigate through the dashboard to access different features

## License

This project is open-source and available for educational purposes.
