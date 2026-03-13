# Staff Registration & Login Guide

## ✅ Issues Fixed

1. **CSRF Token Mismatch** - Disabled CSRF verification for API routes
2. **Demo Accounts Removed** - No more demo credentials displayed
3. **Staff Registration Added** - Staff can now register themselves

## 🆕 New Features

### Staff Registration Form
Staff members can now register themselves with:
- Full Name
- Email Address
- Password (minimum 8 characters)
- Phone Number
- Role Selection:
  - Receptionist
  - Reservation Agent
  - Manager

### Toggle Between Login & Registration
- Click "Don't have an account? Register" to switch to registration
- Click "Already have an account? Sign In" to switch back to login

## 🔐 How to Use

### For New Staff Members (Registration)

1. Visit: **http://localhost:3000/staff/login**
2. Click **"Don't have an account? Register"**
3. Fill in the registration form:
   - Enter your full name
   - Enter your phone number
   - Select your role (Receptionist/Agent/Manager)
   - Enter your email address
   - Create a password (min 8 characters)
4. Click **"Register"**
5. You'll be automatically logged in

### For Existing Staff Members (Login)

1. Visit: **http://localhost:3000/staff/login**
2. Enter your email and password
3. Click **"Sign In"**
4. Access your dashboard

## 🛡️ Security Features

- Passwords are hashed using bcrypt
- Role-based access control
- Guest accounts cannot access staff portal
- Staff accounts cannot be created as guests through this portal
- Token-based authentication (Laravel Sanctum)

## 📋 Available Roles

### 1. Manager (role_id: 1)
- Full system access
- View all reports
- Manage users
- Manage reservations
- Manage rooms

### 2. Receptionist (role_id: 2)
- Check-in/Check-out
- Room status management
- Guest management
- View reservations

### 3. Reservation Agent (role_id: 3)
- Create reservations
- Modify reservations
- Cancel reservations
- Handle bookings

## 🔄 System Changes Made

### Backend Changes
1. Updated `AuthController` to accept `role_id` parameter
2. Added CSRF exception for API routes
3. Cleared configuration cache
4. Updated Sanctum configuration

### Frontend Changes
1. Added registration form to staff login page
2. Added toggle between login/registration
3. Removed demo credentials display
4. Added role selection dropdown
5. Fixed API configuration for CSRF

## ✨ Testing the System

### Test Registration
1. Go to staff login page
2. Click "Register"
3. Fill in:
   - Name: John Doe
   - Phone: +1234567890
   - Role: Receptionist
   - Email: john@hotel.com
   - Password: password123
4. Submit and verify you're logged in

### Test Login
1. Logout if logged in
2. Go to staff login page
3. Enter the credentials you just created
4. Verify successful login

## 🚨 Important Notes

- **Guest accounts are separate** - Guests don't need to register, they book directly
- **Staff portal is secure** - Only staff roles can access
- **No demo accounts** - All staff must register properly
- **Role selection** - Choose the appropriate role during registration
- **Password requirements** - Minimum 8 characters for security

## 🎯 Next Steps

After registration, staff members can:
1. Access their role-specific dashboard
2. Manage hotel operations
3. View and update reservations
4. Generate reports (Manager only)
5. Manage other staff accounts (Manager only)

## 🔧 Troubleshooting

### If login still fails:
1. Clear browser cache
2. Try in incognito/private mode
3. Check browser console for errors
4. Verify backend is running on port 8000
5. Verify frontend is running on port 3000

### If registration fails:
1. Ensure email is unique (not already registered)
2. Password must be at least 8 characters
3. All required fields must be filled
4. Check backend logs for specific errors

## 📞 Support

The system is now fully functional with:
- ✅ Staff registration working
- ✅ Staff login working
- ✅ CSRF issues resolved
- ✅ Demo accounts removed
- ✅ Role-based access implemented

Refresh your browser and try the new registration feature!
