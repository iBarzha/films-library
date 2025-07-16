# 🎬 Films Library

A comprehensive Ruby-based films library management system for organizing and managing your movie collection.

## ✨ Features

- **Film Management**: Add, update, delete, and search films with detailed information
- **Author Management**: Track film directors and creators
- **Genre Classification**: Organize films by multiple genres (many-to-many relationship)
- **User Authentication**: Secure login/registration system with Devise
- **Admin Interface**: Beautiful ActiveAdmin panel for content management
- **Comment System**: Users can comment and discuss films
- **Advanced Search**: Search by title, author, year, genre
- **PostgreSQL Database**: Robust database support for production
- **File Uploads**: Active Storage for film posters and media
- **Responsive Design**: Modern Rails 7 with Hotwire (Turbo & Stimulus)

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- **Ruby**: 3.1.2 (exact version required)
- **Bundler**: Latest version
- **PostgreSQL**: 12+ for database
- **Node.js**: For asset compilation
- **Git**: For version control

### Check your Ruby version:
```bash
ruby --version
```

### Install Bundler if not already installed:
```bash
gem install bundler
```

## 🚀 Installation

1. **Clone the repository:**
```bash
git clone https://github.com/iBarzha/films-library.git
cd films-library
```

2. **Install dependencies:**
```bash
bundle install
```

3. **Set up the database:**
```bash
# Create PostgreSQL database
bundle exec rails db:create

# Run migrations
bundle exec rails db:migrate

# Seed with sample data (optional)
bundle exec rails db:seed
```

4. **Create admin user:**
```bash
# Start Rails console
bundle exec rails console

# Create admin user for ActiveAdmin
AdminUser.create!(email: 'admin@example.com', password: 'password', password_confirmation: 'password')
```

5. **Set up environment variables:**
```bash
# Copy the example environment file (if exists)
cp .env.example .env

# Edit the .env file with your configuration
nano .env
```