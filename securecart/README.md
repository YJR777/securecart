# SecureCart - Django E-Commerce Project

## Project Overview
SecureCart is a secure e-commerce platform built using **Django and PostgreSQL**.  
It follows secure coding practices and ensures **safe authentication, data handling, and transactions**.

---

## Installation Guide

### 1️ Clone the Repository
```bash
git clone https://github.com/yourusername/securecart.git
cd securecart
```

### 2 Install Dependencies
Before running the project, install the required dependencies:

```bash
pip install -r requirements.txt
```

If you experience issues, manually install the essential packages:

```bash
pip install django psycopg2-binary django-environ  
pip install djangorestframework djangorestframework-simplejwt  
pip install django-secure  
pip install django-axes  
```

### 3 Set Up PostgreSQL

- Ensure PostgreSQL is installed
- Create a database:

```sql
CREATE DATABASE securecart;
CREATE USER securecart_user WITH PASSWORD 'your_password'; -- Replace this with your PSQL password
GRANT ALL PRIVILEGES ON DATABASE securecart TO securecart_user;
```

### 4 Configure Environment Variables

- Rename `.env.example` to `.env` and update credentials:
```bash
cp .env.example .env
```
- Edit `.env` to match your PostgreSQL credentials.
- Ensure that your `.env` file includes:

```env
SECRET_KEY="your_secret-key"
DEBUG=True
DB_NAME=securecart
DB_USER=postgres
DB_PASSWORD=your_database_password
DB_HOST=localhost
DB_PORT=5432
EMAIL_HOST=localhost
EMAIL_PORT=1025
EMAIL_USE_TLS=False
EMAIL_USE_SSL=False
EMAIL_HOST_USER=
EMAIL_HOST_PASSWORD=
```

### 5 Run migrations
```bash
python manage.py makemigrations # ONLY IF NO MIGRATIONS EXISTS
python manage.py migrate
python manage.py migrate axes
```

### 6 Create a Superuser
```bash
python manage.py createsuperuser
```

### 7 Start the Development Server
```bash
python manage.py runserver
```

---

## Features list

### **Core Features**
- User Authentication (Login/Register/Logout)
- Password Reset Functionality
- Shopping Cart (Add, Remove, Update Items)
- Checkout & Dummy Payment Integration
- Product Listings & Dummy Data
- User-Specific Cart (Stored in Database)
- Dynamic Navigation (Login/Logout Button)

### **Security Features**
- CSRF Protection Enabled
- Input Validation & Form Security
- Secure Password Storage (Django Authentication)
- Restricted Access to Authenticated Users
- Session Management & Expiry Controls
- Secure Payment Flow (Dummy Checkout)

### **Design & UX Refinements**
- Unified Base Template (Footer Position Fix)
- Removed Contact Us Section (Not Required)
- Improved Dummy Product Listings
- Adjusted Login & Registration UI

### **Admin Features** 
- Admin Dashboard for Managing Products & Orders
- Secure Order Management Panel
- Role-Based Access Controls

---

## Security Checklist
### **Authentication & Authorization**
- Django’s built-in authentication system
- User passwords hashed using PBKDF2 (default in Django)
- Login required for sensitive operations (cart, checkout)
- Logout functionality implemented

### **Data Validation & Protection**
- CSRF tokens implemented on all forms
- Input validation (e.g., ensuring product IDs exist)
- Sessions secured to prevent hijacking

### **Secure Payment Processing**
- Dummy payment gateway (no real transactions)
- Future: Implement Stripe/PayPal with SSL encryption

### **Database Security**
- User cart stored in the database (not in session)
- Secure ORM queries (avoid raw SQL injection risks)
- Database migrations structured properly

---

## Notes for Tutor
- The project includes a **dummy checkout** for testing.
- The admin panel is accessible at `/admin` (requires superuser login).
- The password reset feature sends emails to the console (no real emails sent).

---

## Future Improvements
- **Secure Online Payments** → Implement real transactions via **Stripe/PayPal**.
- **User Activity & Logs** → Implement a **logging system** to track admin and customer actions.
- **Order Management Workflow** → Add **status tracking (Pending, Shipped, Delivered)** and automated notifications.

---

**Author:** Yemi  
**Date:** February 2025  
**Project:** SecureCart - Django E-Commerce Assignment
 