# ReservApp

A subscription-based reservation system built with Next.js 14.

## Tech Stack

- **Framework:** Next.js 14 (App Router)
- **Language:** TypeScript (strict mode)
- **Styling:** Tailwind CSS
- **Database:** PostgreSQL with Prisma ORM
- **Authentication:** JWT + Session-based auth
- **Payments:** MercadoPago
- **Email:** Resend
- **Cache:** Redis
- **Validation:** Zod

## Getting Started

### Prerequisites

- Node.js 18.17 or later
- PostgreSQL database
- Redis server (optional, for caching)

### Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd res-app
```

2. Install dependencies:

```bash
npm install
```

3. Set up environment variables:

```bash
cp .env.example .env
```

4. Update the `.env` file with your configuration values.

5. Set up the database:

```bash
# Generate Prisma client
npm run db:generate

# Run migrations
npm run db:migrate
```

6. Run the development server:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Environment Variables

| Variable | Description |
|----------|-------------|
| `DATABASE_URL` | PostgreSQL connection string |
| `JWT_SECRET` | Secret key for JWT token signing |
| `SESSION_SECRET` | Secret key for session encryption |
| `MERCADOPAGO_ACCESS_TOKEN` | MercadoPago API access token |
| `MERCADOPAGO_PUBLIC_KEY` | MercadoPago public key for frontend |
| `MERCADOPAGO_WEBHOOK_SECRET` | Secret for validating MercadoPago webhooks |
| `RESEND_API_KEY` | Resend API key for sending emails |
| `EMAIL_FROM` | Default sender email address |
| `REDIS_URL` | Redis connection string |
| `NEXT_PUBLIC_APP_URL` | Public URL of the application |
| `TZ` | Timezone (default: America/Santiago) |

## Development Commands

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Start production server
npm run start

# Run ESLint
npm run lint

# Format code with Prettier
npx prettier --write .

# Database commands
npm run db:generate   # Generate Prisma client
npm run db:migrate    # Run migrations
npm run db:push       # Push schema changes (dev only)
npm run db:studio     # Open Prisma Studio GUI
```

## Project Structure

```
├── prisma/
│   └── schema.prisma       # Database schema
├── src/
│   ├── app/                # Next.js App Router pages and layouts
│   ├── components/
│   │   ├── ui/             # Reusable UI components (shadcn/ui)
│   │   └── features/       # Feature-specific components
│   ├── lib/
│   │   ├── db.ts           # Prisma client singleton
│   │   ├── services/       # Business logic services
│   │   └── validations/    # Zod validation schemas
│   └── types/              # TypeScript type definitions
```

## License

Private - All rights reserved.
