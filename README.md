# Early Warning Academic Monitoring System (EWAMS)

A web-based platform for monitoring student academic performance and identifying at-risk students early in higher education institutions.

## Features

- **Role-Based Access Control**: Administrator, Faculty, Advisor, and Student roles
- **Student Management**: Individual profiles, bulk import via CSV
- **Course & Section Management**: Create courses, sections, assign instructors
- **Grade Recording**: Configurable assessment types, weighted grade calculations
- **Risk Assessment Engine**: Automated risk scoring with color-coded levels
- **Alert System**: Dashboard notifications, email alerts
- **Interactive Dashboards**: Role-specific views with charts and analytics
- **Intervention Tracking**: Record and track student interventions

## Technology Stack

- **Backend**: PHP 8+ (MVC Architecture)
- **Frontend**: HTML5, CSS3, JavaScript
- **Database**: MySQL
- **Authentication**: bcrypt password hashing
- **Charts**: Chart.js

## Prerequisites

- PHP 8.0 or higher
- MySQL 5.7 or higher
- Apache/Nginx web server

## Installation

### 1. Database Setup

1. Create a new MySQL database:
```sql
CREATE DATABASE ewams_db;
```

2. Import the database schema:
```bash
mysql -u root -p ewams_db < database/schema.sql
```

### 2. Configuration

Edit `config/config.php` and update the database credentials:

```php
define('DB_HOST', 'localhost');
define('DB_NAME', 'ewams_db');
define('DB_USER', 'root');
define('DB_PASS', 'your_password');
```

Update the base URL:
```php
define('BASE_URL', 'http://localhost/opencode-php');
```

### 3. Web Server Configuration

#### Using XAMPP/WAMP:
- Place the project in `htdocs` or `www` folder
- Access via: `http://localhost/opencode-php`

#### Using PHP Built-in Server:
```bash
cd opencode-php
php -S localhost:8000
```

## Demo Credentials

You can log in using either the username or email.

| Role | Username | Email | Password |
|------|----------|-------|----------|
| Administrator | admin | admin@edu.com | Password123 |
| Faculty | jsmith | john.smith@edu.com | Password123 |
| Advisor | sjohnson | sarah.johnson@edu.com | Password123 |
| Student | mwilliams | mike.williams@edu.com | Password123 |

Additional test students: emily.brown@edu.com, david.jones@edu.com, jennifer.davis@edu.com, chris.miller@edu.com (password: Password123)

## Project Structure

```
/opencode-php
├── config/              # Configuration files
├── controllers/         # PHP controllers
├── database/            # SQL schema and seeds
├── helpers/             # Helper functions
├── models/              # Database models
├── public/
│   ├── css/           # Stylesheets
│   └── js/            # JavaScript files
├── views/              # HTML views
│   ├── auth/          # Login/Register
│   ├── dashboard/     # Dashboard views
│   ├── layouts/       # Shared layouts
│   └── ...            # Feature views
├── index.php           # Entry point
└── SPEC.md             # Detailed specification
```

## Key Features

### Risk Assessment
The system calculates risk scores based on:
- **Grades** (35%): Current academic performance
- **Attendance** (25%): Class presence
- **Submission Timeliness** (20%): On-time assignment submissions
- **Grade Trend** (20%): Recent vs earlier performance

Risk Levels:
- **Low Risk (Green)**: Score 0-30
- **Moderate Risk (Yellow)**: Score 31-60
- **High Risk (Red)**: Score 61-100

### CSV Import Format
```csv
username,email,first_name,last_name,phone,password
jdoe,john.doe@edu.com,John,Doe,555-0100,changeme123
```

## Security Features

- bcrypt password hashing (cost factor 12)
- Prepared statements for all database queries
- Input sanitization
- Role-based access control
- Session management

## License

This project is for educational purposes.
