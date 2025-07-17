# 🎬 Films Library

A comprehensive Ruby on Rails 7 films library management system for organizing and managing your movie collection with multi-language support.

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
- **Multi-language Support**: English and Ukrainian locales
- **Health Check**: Built-in Rails health check endpoint

## 🏗️ Architecture

- **Backend**: Ruby on Rails 7.1.3 with Ruby 3.1.2
- **Database**: PostgreSQL with migrations and seeds
- **Frontend**: Hotwire (Turbo & Stimulus) with modern JavaScript
- **Authentication**: Devise for users and admin users
- **Admin Panel**: ActiveAdmin for content management
- **Internationalization**: Rails i18n with English and Ukrainian support
- **Asset Pipeline**: Sprockets with SCSS support
- **Testing**: Rails testing framework with system tests

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
git clone <repository-url>
cd films-library
```

2. **Install dependencies:**
```bash
bundle install
```

3. **Configure database:**
```bash
# Update config/database.yml with your PostgreSQL credentials
# Default configuration:
# - Host: localhost
# - Username: postgres
# - Password: 123123
# - Database names: postgres_development, postgres_test, postgres_production
```

4. **Set up the database:**
```bash
# Create PostgreSQL database
bundle exec rails db:create

# Run migrations
bundle exec rails db:migrate

# Seed with sample data (optional)
bundle exec rails db:seed
```

5. **Create admin user:**
```bash
# Start Rails console
bundle exec rails console

# Create admin user for ActiveAdmin
AdminUser.create!(email: 'admin@example.com', password: 'password', password_confirmation: 'password')
```

6. **Start the application:**
```bash
# Start the Rails server
bundle exec rails server

# The application will be available at:
# http://localhost:3000
```

## 🎯 Usage

### User Interface
- **Home Page**: `http://localhost:3000` - Welcome page with film listings
- **Films**: Browse, search, and view individual films
- **Authors**: View films by specific authors
- **Genres**: Browse films by genre categories
- **User Authentication**: Sign up/login to comment on films
- **Multi-language**: Switch between English (`/en`) and Ukrainian (`/uk`) locales

### Admin Interface
- **Admin Panel**: `http://localhost:3000/admin` - ActiveAdmin dashboard
- **Manage**: Films, Authors, Genres, Users, Comments
- **Login**: Use the admin credentials created during setup

### API Endpoints
- **Health Check**: `GET /up` - Application health status
- **Films**: CRUD operations with nested comments
- **Search**: `GET /search` - Search films by various criteria
- **Locale Support**: All routes support `/:locale` prefix

## 🗂️ Database Schema

### Core Models
- **Film**: Title, description, year, poster (Active Storage)
- **Author**: Name, bio, films relationship
- **Genre**: Name, description, films relationship (many-to-many)
- **User**: Devise authentication, comments
- **Comment**: User comments on films
- **AdminUser**: ActiveAdmin authentication

### Relationships
- Films ↔ Authors (belongs_to/has_many)
- Films ↔ Genres (many-to-many through FilmGenre)
- Films ↔ Comments (has_many)
- Users ↔ Comments (has_many)

## 🚀 Deployment

### Production Setup
1. Set up PostgreSQL production database
2. Configure environment variables for production
3. Run migrations: `bundle exec rails db:migrate RAILS_ENV=production`
4. Precompile assets: `bundle exec rails assets:precompile`
5. Start server: `bundle exec rails server -e production`

### Docker Support
```bash
# Build and run with Docker
docker build -t films-library .
docker run -p 3000:3000 films-library
```

### Key Gems
- **Rails**: 7.1.3 - Web framework
- **Devise**: User authentication
- **ActiveAdmin**: Admin interface
- **pg**: PostgreSQL adapter
- **Hotwire**: Turbo & Stimulus for modern frontend
- **Image Processing**: Active Storage variants

