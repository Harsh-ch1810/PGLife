# 🏠 PG Life

**Happiness per Square Foot** — A full-stack web application to help students find and shortlist paying guest accommodations across major Indian cities.

---

## 📸 Screenshots

### 🏠 Home Page
![Home Page](screenshots/home.png)

### 🏙️ Property Listing
![Property Listing](screenshots/property-list.png)

### 👤 User Dashboard
![Dashboard](screenshots/dashboard.png)

### 📝 Signup
![Signup](screenshots/signup.png)

---

## ✨ Features

- 🔍 **City-based Search** — Search PG accommodations by city name
- 🏙️ **Major Cities** — Quick-access browsing for Delhi, Mumbai, Bengaluru, and Hyderabad
- 🔐 **User Authentication** — Secure signup and login with password hashing
- 👤 **User Dashboard** — View and edit your profile details
- ❤️ **Interested Listings** — Mark properties you're interested in and track them
- 📊 **Ratings** — Properties rated on cleanliness, food, and safety
- 🔽 **Sort & Filter** — Sort listings by highest or lowest rent
- 🛏️ **Amenities** — Detailed amenity info (WiFi, AC, Parking, CCTV, Geyser, etc.)
- 💬 **Testimonials** — Real reviews from previous residents
- 👫 **Gender Filter** — Properties categorized as Male, Female, or Unisex

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | HTML5, CSS3, Bootstrap 4 |
| Backend | PHP |
| Database | MySQL |
| JavaScript | jQuery, Vanilla JS |

---

## 🗂️ Project Structure

```
PGLIFE/
├── img/
│   ├── amenities/          # SVG icons for amenities
│   └── *.png               # City images, UI assets
├── includes/               # PHP include files (DB connection, header, footer)
├── js/
│   ├── bootstrap.min.js
│   ├── common.js
│   ├── dashboard.js
│   ├── jquery.js
│   ├── property_detail.js
│   └── property_list.js
├── screenshots/            # UI screenshots for README
├── index.php               # Home page
├── property_list.php       # Listings page (by city)
├── property_detail.php     # Individual property page
├── dashboard.php           # User profile & dashboard
├── logout.php              # Session logout
└── README.md
```

---

## 🗃️ Database Schema

The application uses a relational MySQL database with the following tables:

```
users                        — Registered user accounts
cities                       — Available cities
properties                   — PG property listings (linked to cities)
amenities                    — Amenity types (WiFi, AC, Geyser, etc.)
properties_amenities         — Many-to-many: properties ↔ amenities
testimonials                 — User reviews for properties
interested_users_properties  — Users who marked interest in a property
```

### Entity Relationship Overview

```
cities ──< properties >──< properties_amenities >── amenities
                  │
                  ├──< testimonials
                  │
users ────────────┘ (via interested_users_properties)
```

---

## 🚀 Getting Started

### Prerequisites

- PHP >= 7.0
- MySQL >= 5.7
- A local server environment: [XAMPP](https://www.apachefriends.org/) / [WAMP](https://www.wampserver.com/) / [MAMP](https://www.mamp.info/)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/pglife.git
   ```

2. **Move to your server's root directory**
   ```bash
   # For XAMPP
   mv pglife /xampp/htdocs/pglife
   ```

3. **Set up the database**
   - Open [phpMyAdmin](http://localhost/phpmyadmin)
   - Create a new database named `pglife`
   - Import the schema: `Module 4 Assignment Solution - SQL queries.sql`
   - Import the seed data: `dummy_data.sql`

4. **Configure DB connection**
   ```php
   $conn = mysqli_connect("localhost", "root", "", "pglife");
   ```

5. **Run the app**
   ```
   http://localhost/pglife/
   ```

---

## 📋 Dummy Data Included

| Table | Records |
|-------|---------|
| Cities | 4 (Delhi, Mumbai, Bengaluru, Hyderabad) |
| Properties | 5 |
| Amenities | 13 |
| Users | 4 |
| Testimonials | 10 |
| Interested Users | 11 |

---

## 🔑 Sample Login

| Email | Password |
|-------|----------|
| `anuj.kalbalia@gmail.com` | `password` |
| `shadab@gmail.com` | `password` |

> Passwords are SHA1-hashed in the database.

---

## 🤝 Contributing

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

<p align="center">Made with ❤️ for students looking for a home away from home</p>
