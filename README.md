# 📂 Projects

1. [🎬 MovieDiary](#-moviediary): Android movie diary app
2. [🚔 Crime Reporting System](#-crime-reporting-system): database project (Database II)

---

# 🎬 MovieDiary

MovieDiary is an Android app for movie lovers. Discover films, search by title or genre, explore movie details, build your own watched / watchlist / favorites lists, and keep a personal diary with ratings and reviews.

Movie data is provided by [The Movie Database (TMDB)](https://www.themoviedb.org/).


## 👥 Team

- Mariam Atwi
- Rim Fahes
- Mariam Fnesh
- Layla Saleh

## 📸 Screenshots

See the full app walkthrough in [`MovieDiary-Screenshots.pdf`](./MovieDiary-Screenshots.pdf).

## ✨ Features

### Home
- **Films**: horizontal sections such as *Popular this week*, *Action picks*, *Thrillers you may like*, *Comedy night* and *Family Movies*, with a "see all" grid view
- **Reviews**: community reviews from TMDB for popular movies, with star ratings and "Read full review"
- **Journal**: movie news and articles

### Search
- Search movies by title
- Filter by one or more genres using chips (Action, Adventure, Animation, Comedy, Crime...)

### Movie Details
- Backdrop, poster, release year, runtime and rating
- Play trailer button
- Director, overview and cast
- Similar movies
- Add to **Watched**, **Watchlist** or **Favorites** from the menu (login required)

### Add to Diary
- Search any movie and open the *Add to Diary* dialog
- Give it a star rating, write a review and mark it as a favorite

### Diary
- See all your reviews in one place
- Delete a review with a confirmation dialog

### Profile & Accounts
- Guest mode, with a prompt to log in when modifying lists
- Sign up (username, email, password with validation) and log in
- Profile page with your **top 4 recent favorites** and **Watched / To Watch / Favorites** tabs

## 🛠️ Tech Stack

| Area | Technology |
|---|---|
| Platform | Android |
| Language | Java |
| UI | XML layouts, Material Components, Bottom Navigation |
| Networking | Retrofit 2 + Gson |
| Images | Glide |
| Local database | Room |
| Data source | TMDB API |

## 🔮 Future Improvements

- Secure password storage or a real backend such as Firebase Auth
- Cloud sync for diary entries
- Move to Kotlin and MVVM

## 📌 Note

The source code is not published in this repository. This repo only showcases the app through screenshots and documentation.

---

# 🚔 Crime Reporting System

A database-driven web application that lets residents report crimes and lets police departments receive, categorize, assign and respond to those reports. Built as the final project for **I3306: Database II** at the **Lebanese University, Faculty of Sciences** (Computer Science, 2025-2026).

## 👥 Team

- Mariam Atwi
- Hoda Shour
- Fatima Assaad

## 🏗️ Architecture

The system follows a client-server, three-tier design:

| Layer | Role |
|---|---|
| **User client** | PHP + HTML + CSS interface with secure login, sessions and role-based dashboards |
| **Application server** | Business logic and validation |
| **Database server** | Storage, integrity constraints, triggers, transactions, security and backup (DBMS: Microsoft SQL Server) |

## 👤 User Roles

| Role | What they can do |
|---|---|
| **Administrator** | Full control: manage all reports, users, system settings and crime categories |
| **Resident** | Submit crime reports with details and image evidence, and track their own report history and status |
| **Policeman** | View assigned cases, update case status, and record and review response actions |
| **Supervisor** | Monitor all reports and assign cases to officers based on availability and workload (read-only on investigation details) |

## 🗃️ Database Design

Modeled with an Entity Relationship Diagram and mapped to a relational schema in third normal form.

📄 See the full diagram on page 1 of [`CrimeReport-Screenshots.pdf`](./CrimeReport-Screenshots.pdf).

**Main tables:** `Resident`, `Addresses`, `CrimeReport`, `CrimeCategory`, `Policeman`, `ResponseAction`

Key rules:
- Residents are identified by SSN, can have multiple addresses and can submit multiple reports
- Each report belongs to one resident, is received by one policeman and has a category and a status
- Statuses: Open, Closed, Pending, Under Investigation, Critical
- A report can lead to one or more response actions (Investigation, Arrest, Scene Secured, Patrol Check...)
- Images are stored as file paths, not binary data, for better performance
- Constraints: primary keys, foreign keys, check constraints (e.g. minimum policeman salary of 1000)

## ⚙️ Database Features Implemented

- DDL scripts (tables and constraints)
- DML scripts (inserts, updates, deletes) and a set of relevant queries
- Stored procedures and functions
- Transactions
- Cursors
- Views
- Triggers enforcing business rules
- Role-based security (users, roles and permissions)

## 📸 Application Screenshots

📄 **[View the ERD and all application screenshots (PDF)](./CrimeReport-Screenshots.pdf)**

The PDF has one titled page per screen:

| Role | Screens |
|---|---|
| **Login** | Login page |
| **Admin** | Dashboard, manage crime reports |
| **Resident** | Resident portal, report a crime |
| **Policeman** | Dashboard, my assigned cases, case details & investigation, update case status, response actions, add response action, action history |
| **Supervisor** | Dashboard, review all reports, assign cases to officers |
| **Tests** | Invalid login message, report submitted successfully, case assigned successfully |

## 🛠️ Tech Stack

| Area | Technology |
|---|---|
| Database | Microsoft SQL Server (T-SQL) |
| Modeling | PowerDesigner (ERD) |
| Backend / UI | PHP, HTML, CSS |

## 📄 Full Project Report

The complete report (architecture, business requirements, ERD, schema mapping, DDL/DML scripts, queries, stored procedures, functions, transactions, cursors, views and security roles) is available here: **[I3306-CrimeReport-doc.docx](./I3306-CrimeReport-doc.docx)**

