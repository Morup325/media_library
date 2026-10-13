# Local Setup (Docker & Laravel Sail)

This guide explains how to start the `media_library` project locally using Docker and Laravel Sail.

## Prerequisites
Ensure you have met all requirements listed in [00-prerequisites.md](00-prerequisites.md).

## First Time Setup

1. **Clone the repository and enter the directory:**
   ```bash
   git clone <your-repo-url> media_library
   cd media_library
   ```

2. **Install Composer dependencies:**
   Since you don't have PHP installed locally, use a temporary Docker container to install the vendor packages:
   ```bash
   docker run --rm \
       -u "$(id -u):$(id -g)" \
       -v "$(pwd):/var/www/html" \
       -w /var/www/html \
       laravelsail/php82-composer:latest \
       composer install --ignore-platform-reqs
   ```

3. **Set up the environment variables:**
   ```bash
   cp .env.example .env
   ```

4. **Start the containers:**
   ```bash
   ./vendor/bin/sail up -d
   ```

5. **Generate the application key & run migrations:**
   ```bash
   ./vendor/bin/sail artisan key:generate
   ./vendor/bin/sail artisan migrate
   ```

## Daily Development

To start the environment:
```bash
./vendor/bin/sail up -d
```

To stop the environment:
```bash
./vendor/bin/sail stop
```

To run artisan commands, prefix them with sail:
```bash
./vendor/bin/sail artisan route:list
```