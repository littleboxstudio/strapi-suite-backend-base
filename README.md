# Strapi Base Installation for Littlebox Strapi Suite

This is a base installation of Strapi with a database running in Docker, designed for testing purposes. This setup already includes the essential configurations for using the Littlebox Strapi Suite plugin, as per the documentation: [Before Starting](https://strapi-suite.littlebox.pt/before-starting).

## Getting Started

### 1. Configure Environment Variables

Rename the `.env.example` file to `.env`:

```bash
cp .env.example .env
```

> ⚠️ **Warning:** The values provided in `.env.example` are for local testing only. **Never use these values in production** — generate your own secrets (`APP_KEYS`, `API_TOKEN_SALT`, `ADMIN_JWT_SECRET`, `TRANSFER_TOKEN_SALT`, `JWT_SECRET`) and use strong, unique database credentials.

### 2. Start the Database

To start the database using Docker, navigate to the `docker` directory and run:

```bash
cd docker
docker-compose up -d
```

On the **first startup**, the container automatically imports `database/db-base.sql`, which already contains a pre-seeded database (including the admin user listed below). You don't need to set anything up manually.

> ℹ️ **Note:** The SQL is only imported when the database volume is empty (first initialization). If you've already started the container before and want to re-import the data from scratch, reset the volume:
>
> ```bash
> cd docker
> docker-compose down -v
> docker-compose up -d
> ```

### 3. Start Strapi

Return to the root directory and install the dependencies:

```bash
npm install
```

Start the Strapi development server:

```bash
npm run develop
```

### 4. Access Admin Panel

Access the backoffice at: http://localhost:1337/

- **User**: `test@test.com`
- **Password**: `Test123#2026`

## Configuration

### Generating an API Token

To use the Littlebox Strapi Suite, you need to generate an API Token in Strapi:

1.  Access the Strapi admin panel (usually at `http://localhost:1337/admin`).
2.  Go to **Settings** > **Global Settings** > **API Tokens**.
3.  Click **Create new API Token**.
4.  Fill in the details:
    - **Name**: Choose a name (e.g., "Littlebox Suite").
    - **Token type**: Select **Full Access**.
    - **Duration**: Select **Unlimited** (or as needed).
5.  Click **Save** and **copy the generated token** immediately (you won't be able to see it again).

### Environment Variables

The generated API Token must be added to your environment variables.
For more information on the required environment variables, please consult: [Environment Variables](https://strapi-suite.littlebox.pt/frontend/installation#environment-variables).
