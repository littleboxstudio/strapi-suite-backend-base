# Strapi Base Installation for Littlebox Strapi Suite

This is a base installation of Strapi with a database running in Docker, designed for testing purposes. This setup already includes the essential configurations for using the Littlebox Strapi Suite plugin, as per the documentation: [Before Starting](https://strapi-suite.littlebox.pt/before-starting).

## Getting Started

### 1. Start the Database

To start the database using Docker, navigate to the `docker` directory and run:

```bash
cd docker
docker-compose up -d
```

### 2. Start Strapi

Return to the root directory and install the dependencies:

```bash
npm install
```

Start the Strapi development server:

```bash
npm run develop
```

### 3. Access Admin Panel

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
