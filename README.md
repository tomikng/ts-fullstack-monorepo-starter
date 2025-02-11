# Fullstack Monorepo Starter

This is a monorepo for Fullstack Monorepo Starter project containing both frontend and backend applications, along with shared packages.

## Project Structure

```
fullstack-monorepo-starter/
├── apps/
│   ├── web/           # Next.js frontend application
│   └── backend/       # NestJS backend application
│
├── packages/
│   ├── ui/            # Shared UI components
│   ├── database/      # Database schema and utilities
│   ├── config/        # Shared configuration
│   ├── eslint-config/ # ESLint configuration
│   └── typescript-config/ # TypeScript configuration
```

## Prerequisites

- Node.js (v18 or higher)
- PNPM package manager
- PostgreSQL database

## Quick Start

1. Install dependencies:
```bash
pnpm install
```

2. Set up environment variables:
```bash
cp apps/backend/.env.example apps/backend/.env
```

3. Generate Prisma client (required before starting the application):
```bash
pnpm generate:prisma
```

4. Start all applications in development mode:
```bash
pnpm dev
```

This will start:
- Frontend at http://localhost:3000
- Backend at http://localhost:3001
- API documentation at http://localhost:3001/api/docs

## Applications

### Frontend (Web)
The web application is built with Next.js and uses shadcn/ui components. 
[View Web Application Documentation](apps/web/README.md)

### Backend
The backend service is built with NestJS and uses Prisma as the ORM.
[View Backend Documentation](apps/backend/README.md)

## Package Management

This project uses PNPM workspaces. To add dependencies:

1. Add a dependency to a specific app:
```bash
pnpm add <package> --filter <app-name>
```

2. Add a shared dependency to the root:
```bash
pnpm add -w <package>
```

3. Add a development dependency:
```bash
pnpm add -Dw <package>
```

## Development Workflow

1. Start all services:
```bash
pnpm dev
```

2. Run tests across all packages:
```bash
pnpm test
```

3. Build all packages:
```bash
pnpm build
```

4. Lint all packages:
```bash
pnpm lint
```

## Adding New Features

### Frontend
- Follow the [Web Application Guide](apps/web/README.md) for adding new pages and components
- Use shadcn components from the shared UI package
- Follow the established styling patterns with Tailwind CSS

### Backend
- Follow the [Backend Guide](apps/backend/README.md) for adding new modules and endpoints
- Use Prisma for database operations
- Document new endpoints with Swagger decorators

## Best Practices

1. Code Style
   - Follow TypeScript best practices
   - Use ESLint and Prettier configurations
   - Write meaningful commit messages

2. Testing
   - Write unit tests for new features
   - Ensure E2E tests pass before merging
   - Maintain good test coverage

3. Documentation
   - Update README files when adding new features
   - Document API endpoints with Swagger
   - Keep component documentation up to date

## Troubleshooting

Common issues and solutions can be found in the respective application READMEs:
- [Frontend Troubleshooting](apps/web/README.md#troubleshooting)
- [Backend Troubleshooting](apps/backend/README.md#troubleshooting)

## Contributing

1. Create a new branch for your feature
2. Make your changes
3. Run tests and linting
4. Submit a pull request
5. Ensure CI checks pass

## Contact

For any questions, concerns, or bug reports, please feel free to contact:
- Email: tomasnguyen43@gmail.com

## License

This project is MIT licensed. 