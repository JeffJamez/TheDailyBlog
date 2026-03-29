# TheDailyBlog - Laravel Livewire RealWorld Application

A production-ready full-stack blogging platform built with Laravel and LiveWire, implementing the RealWorld specification for social blogging functionality.

## Overview

TheDailyBlog is a Medium.com-style social blogging platform that demonstrates professional-grade implementation of:

- User authentication with JWT
- CRUD operations for articles
- Commenting system
- Social features (favorites, follows)
- RESTful API design

## Tech Stack

- **Backend**: Laravel 10+
- **Frontend**: Laravel LiveWire
- **Database**: MySQL/PostgreSQL
- **Authentication**: JWT (with session/cookie option)
- **API**: RESTful with JSON responses

## Features

### Authentication

- User registration and login
- JWT token-based authentication
- Session/cookie authentication option
- Profile management

### Articles

- Create, read, update, delete articles
- Markdown rendering
- Tag-based organization
- Favoriting articles

### Social

- Follow other users
- View personalized feed
- Favorite articles
- Comment on articles

### User Profile

- Edit profile information
- View user's articles
- View favorited articles

## API Endpoints

The application exposes a full REST API at `/api`:

| Method                                  | Endpoint                     | Description       |
| --------------------------------------- | ---------------------------- | ----------------- |
| POST                                    | /api/users                   | Register new user |
| POST                                    | /api/users/login             | User login        |
| GET                                     | /api/user                    | Get current user  |
| PUT                                     | /api/user                    | Update user       |
| GET                                     | /api/articles                | List articles     |
| POST                                    | /api/articles                | Create article    |
| GET                                     | /api/articles/:slug          | Get article       |
| PUT                                     | /api/articles/:slug          | Update article    |
| DELETE                                  | /api/articles/:slug          | Delete article    |
| POST                                    | /api/articles/:slug/favorite | Favorite article  |
| DELETE /api/articles/:slug/favorite     | Unfavorite                   |
| GET /api/articles/:slug/comments        | Get comments                 |
| POST /api/articles/:slug/comments       | Add comment                  |
| DELETE /api/articles/:slug/comments/:id | Delete comment               |
| GET /api/profiles/:username             | Get profile                  |
| POST /api/profiles/:username/follow     | Follow user                  |
| DELETE /api/profiles/:username/follow   | Unfollow                     |
| GET /api/tags                           | List tags                    |

## Project Structure

```
app/
├── Http/
│   ├── Controllers/     # API Controllers
│   └── Livewire/        # LiveWire Components
├── Models/               # Eloquent Models
├── Services/             # Business Logic
└── Providers/           # Service Providers
routes/
├── api.php              # API Routes
└── web.php              # Web Routes
```

## Getting Started

### Prerequisites

- PHP 8.1+
- Composer
- MySQL or PostgreSQL
- Node.js & npm

### Installation

```bash
# Install dependencies
composer install
npm install

# Copy environment file
cp .env.example .env

# Generate application key
php artisan key:generate

# Configure database in .env

# Run migrations
php artisan migrate

# Seed database (optional)
php artisan db:seed

# Start development server
php artisan serve
```

## Design Patterns Demonstrated

- **Repository Pattern**: Data access abstraction
- **Service Layer**: Business logic separation
- **Resource Controllers**: RESTful controller design
- **Form Requests**: Request validation
- **API Resources**: JSON transformation

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
