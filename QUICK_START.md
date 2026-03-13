# Quick Start Guide

## Step-by-Step Setup

### 1. Start XAMPP
- Open XAMPP Control Panel
- Start Apache and MySQL services

### 2. Create Database
- Open phpMyAdmin: `http://localhost/phpmyadmin`
- Create new database: `hotel_management`

### 3. Start Backend (Terminal 1)
```bash
cd hotel-management-backend
php artisan serve
```
Keep this terminal running. Backend will be at `http://localhost:8000`

### 4. Start Frontend (Terminal 2)
```bash
cd hotel-management-frontend
npm start
```
Keep this terminal running. Frontend will open at `http://localhost:3000`

### 5. Login
Use any of these accounts:
- Manager: manager@hotel.com / password
- Receptionist: receptionist@hotel.com / password
- Agent: agent@hotel.com / password
- Guest: guest@hotel.com / password

## Testing the System

### As Guest:
1. Login with guest@hotel.com
2. Go to Reservations
3. Click "New Reservation"
4. Select room type, dates, number of guests
5. Create reservation
6. Click "Pay" to process payment (choose cash/card/online)

### As Receptionist:
1. Login with receptionist@hotel.com
2. Go to Room Management
3. Change room status (available → occupied → dirty → available)
4. Go to Reservations to check-in/check-out guests

### As Manager:
1. Login with manager@hotel.com
2. View Reports to see occupancy, revenue, ADR, no-shows
3. Manage users (create, deactivate staff)
4. Oversee all reservations

### Menu & Orders:
1. Go to Menu & Orders
2. Browse food and drinks (categorized: Food, Soft Drinks, Alcoholic Drinks)
3. Add items to cart
4. Enter reservation ID
5. Place order

## Troubleshooting

### Backend Issues:
- **Database connection error**: Check XAMPP MySQL is running
- **Migration error**: Run `php artisan migrate:fresh --seed`
- **Port 8000 in use**: Use `php artisan serve --port=8001`

### Frontend Issues:
- **API connection error**: Ensure backend is running on port 8000
- **CORS error**: Check `config/cors.php` allows `http://localhost:3000`
- **Port 3000 in use**: React will prompt to use another port

### Common Fixes:
```bash
# Reset database
cd hotel-management-backend
php artisan migrate:fresh --seed

# Clear Laravel cache
php artisan config:clear
php artisan cache:clear

# Reinstall frontend dependencies
cd hotel-management-frontend
rm -rf node_modules
npm install
```

## Features to Test

✅ User authentication (login/register/logout)
✅ Room availability checking
✅ Reservation creation and management
✅ Payment processing (manual: cash, digital: card/online)
✅ Room status updates
✅ Menu ordering (Food, Soft Drinks, Alcoholic Drinks)
✅ Reports and analytics
✅ User management (manager only)
✅ Role-based access control

## Next Steps

1. Customize room types and pricing
2. Add more menu items
3. Configure real payment gateway (Stripe/PayPal)
4. Add email notifications
5. Implement booking confirmations
6. Add more reports and analytics
