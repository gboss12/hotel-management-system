# Hotel Management System - Complete Project Documentation

## 🎉 Project Status: COMPLETE & RUNNING

---

## 📋 Project Overview

A full-stack hotel management system built with Laravel (Backend) and React (Frontend).

### Technology Stack
- **Backend**: Laravel 11 + MySQL
- **Frontend**: React 18 + React Router
- **Database**: MySQL (XAMPP)
- **Authentication**: Laravel Sanctum
- **Currency**: Ethiopian Birr (ETB)

---

## 🗄️ Database Information

**Database Name**: `hotel_management`

**Location**: XAMPP MySQL Server
- Host: 127.0.0.1
- Port: 3306
- Username: root
- Password: (empty)

**SQL Export File**: `hotel_management.sql` (in project root)

### Database Tables (15 tables):
1. `roles` - User roles (Manager, Receptionist, Reservation Agent, Guest)
2. `users` - System users
3. `personal_access_tokens` - API authentication tokens
4. `room_types` - 6 room types with images
5. `rooms` - 43 rooms across 6 floors
6. `reservations` - Booking records
7. `payments` - Payment transactions (Cash, Telebirr, CBE Birr, M-Pesa)
8. `menu_categories` - Food, Soft Drink, Alcoholic Drink
9. `menu_items` - 27 items with images
10. `orders` - Food/drink orders
11. `order_items` - Order line items
12. `pricing_rules` - Dynamic pricing
13. `cache`, `cache_locks` - System cache
14. `sessions` - User sessions
15. `jobs`, `job_batches`, `failed_jobs` - Queue system

---

## 📊 Data Summary

### Room Types (6 types, 43 rooms total):
1. **Single Room** - ETB 50/night (10 rooms: 101-110)
2. **Double Room** - ETB 80/night (10 rooms: 201-210)
3. **Suite** - ETB 150/night (5 rooms: 301-305)
4. **Deluxe Room** - ETB 120/night (10 rooms: 401-410)
5. **Family Room** - ETB 180/night (5 rooms: 501-505)
6. **Presidential Suite** - ETB 300/night (3 rooms: 601-603)

### Menu Items (27 items total):
- **Food** (11 items): Grilled Salmon, Caesar Salad, Beef Burger, Grilled Chicken, Beef Steak, Pasta Carbonara, Fish and Chips, Vegetable Curry, Burger Deluxe, Pizza Margherita, Sushi Platter
- **Soft Drinks** (8 items): Coca Cola, Orange Juice, Mineral Water, Lemonade, Iced Tea, Smoothie, Coffee, Hot Chocolate
- **Alcoholic Drinks** (8 items): Red Wine, Beer, Whiskey, White Wine, Champagne, Vodka, Rum, Cocktail

### User Roles (4 roles):
1. **Manager** - Full system access
2. **Receptionist** - Check-in/out, guest management
3. **Reservation Agent** - Booking management
4. **Guest** - Limited access (auto-created during booking)

---

## 🚀 Running the Project

### Prerequisites:
- XAMPP (Apache + MySQL running)
- PHP 8.2+
- Composer
- Node.js 18+
- npm

### Start Servers:

**Backend (Laravel)**:
```bash
cd hotel-management-backend
php artisan serve
```
- Runs on: http://localhost:8000

**Frontend (React)**:
```bash
cd hotel-management-frontend
npm start
```
- Runs on: http://localhost:3000

---

## 🌐 Application URLs

### Public Guest Interface (No Login Required):
- **Home**: http://localhost:3000/
- **Rooms**: http://localhost:3000/rooms
- **Booking**: http://localhost:3000/booking
- **Menu**: http://localhost:3000/menu
- **Contact**: http://localhost:3000/contact

### Staff Portal (Login Required):
- **Staff Login**: http://localhost:3000/staff/login
- **Dashboard**: http://localhost:3000/staff/dashboard
- **Reservations**: http://localhost:3000/staff/reservations
- **Rooms**: http://localhost:3000/staff/rooms
- **Reports**: http://localhost:3000/staff/reports
- **Users**: http://localhost:3000/staff/users

---

## 🎨 Design Features

### Visual Design:
- Modern purple gradient theme (#667eea to #764ba2)
- Professional images for all rooms and menu items
- Smooth animations and hover effects
- Responsive design for all screen sizes
- Beautiful "Why Choose Us" section with real images

### User Experience:
- Guest booking without registration (4-step process)
- Multi-step booking: Guest Info → Booking Details → Payment → Confirmation
- Real-time room availability checking
- Ethiopian payment methods integration
- Staff registration and role-based access

---

## 💳 Payment Methods

All payments in Ethiopian Birr (ETB):
1. **Cash** - Manual payment
2. **Telebirr** - Mobile payment
3. **CBE Birr** - Commercial Bank of Ethiopia
4. **M-Pesa** - Mobile money

---

## 👥 Actor Capabilities

### Manager:
- View and analyze reports (occupancy, revenue, ADR, statistics)
- Set and modify room rates, pricing, promotions
- Manage staff accounts (create, update, deactivate, assign permissions)
- Oversee all reservations
- Manage hotel operations
- Monitor financial transactions

### Receptionist:
- Perform check-in/check-out
- Assign rooms to reservations
- Update room status
- Handle walk-in guests
- Resolve guest issues
- Coordinate with housekeeping

### Reservation Agent:
- Create new reservations
- Modify existing reservations
- Cancel reservations and process refunds
- Handle special requests and group bookings
- Send confirmation details

### Guest:
- Search room availability
- Make, modify, view, and cancel reservations
- Perform online payment
- View hotel details, rooms, prices, amenities
- Provide special requests
- Receive booking confirmations

---

## 📁 Project Structure

```
G-Hotel management system/
├── hotel-management-backend/     # Laravel Backend
│   ├── app/
│   │   ├── Http/Controllers/Api/
│   │   └── Models/
│   ├── database/
│   │   ├── migrations/
│   │   └── seeders/
│   ├── routes/
│   └── .env
├── hotel-management-frontend/    # React Frontend
│   ├── src/
│   │   ├── components/
│   │   │   ├── Guest/
│   │   │   ├── Staff/
│   │   │   └── Auth/
│   │   ├── services/
│   │   └── App.js
│   └── package.json
└── hotel_management.sql          # Database Export
```

---

## 🔧 Configuration Files

### Backend (.env):
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=hotel_management
DB_USERNAME=root
DB_PASSWORD=
```

### Frontend (api.js):
```javascript
const API_URL = 'http://localhost:8000/api';
```

---

## ✅ All Features Implemented

- ✅ Full CRUD operations for all entities
- ✅ User authentication and authorization
- ✅ Role-based access control
- ✅ Room booking system with availability checking
- ✅ Multi-step booking process
- ✅ Ethiopian payment gateway integration
- ✅ Menu ordering system
- ✅ Reporting and analytics
- ✅ Staff management
- ✅ Dynamic pricing rules
- ✅ Professional images for rooms and menu
- ✅ Responsive design
- ✅ Beautiful UI with animations

---

## 📝 Important Notes

1. **XAMPP MySQL must be running** before starting the backend
2. **Import hotel_management.sql** into phpMyAdmin first time
3. **Both servers must run** for full functionality
4. **Guest bookings** create user accounts automatically
5. **Staff must register** through the registration form
6. All **prices are in ETB** (Ethiopian Birr)

---

## 🎯 Quick Start Guide

1. Start XAMPP (Apache + MySQL)
2. Import `hotel_management.sql` in phpMyAdmin
3. Open terminal 1: `cd hotel-management-backend && php artisan serve`
4. Open terminal 2: `cd hotel-management-frontend && npm start`
5. Visit http://localhost:3000

---

## 📞 Support

For any issues or questions, refer to the documentation files:
- `QUICK_START.md`
- `SYSTEM_OVERVIEW.md`
- `STAFF_REGISTRATION_GUIDE.md`

---

**Project Created**: March 2026
**Status**: Production Ready ✅
**Version**: 1.0.0

---

## 🎊 Congratulations!

Your hotel management system is complete and fully functional!
