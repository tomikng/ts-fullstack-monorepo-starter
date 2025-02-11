<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

  <p align="center">A progressive <a href="http://nodejs.org" target="_blank">Node.js</a> framework for building efficient and scalable server-side applications.</p>
    <p align="center">
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/v/@nestjs/core.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/l/@nestjs/core.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/dm/@nestjs/common.svg" alt="NPM Downloads" /></a>
<a href="https://circleci.com/gh/nestjs/nest" target="_blank"><img src="https://img.shields.io/circleci/build/github/nestjs/nest/master" alt="CircleCI" /></a>
<a href="https://coveralls.io/github/nestjs/nest?branch=master" target="_blank"><img src="https://coveralls.io/repos/github/nestjs/nest/badge.svg?branch=master#9" alt="Coverage" /></a>
<a href="https://discord.gg/G7Qnnhy" target="_blank"><img src="https://img.shields.io/badge/discord-online-brightgreen.svg" alt="Discord"/></a>
<a href="https://opencollective.com/nest#backer" target="_blank"><img src="https://opencollective.com/nest/backers/badge.svg" alt="Backers on Open Collective" /></a>
<a href="https://opencollective.com/nest#sponsor" target="_blank"><img src="https://opencollective.com/nest/sponsors/badge.svg" alt="Sponsors on Open Collective" /></a>
  <a href="https://paypal.me/kamilmysliwiec" target="_blank"><img src="https://img.shields.io/badge/Donate-PayPal-ff3f59.svg" alt="Donate us"/></a>
    <a href="https://opencollective.com/nest#sponsor"  target="_blank"><img src="https://img.shields.io/badge/Support%20us-Open%20Collective-41B883.svg" alt="Support us"></a>
  <a href="https://twitter.com/nestframework" target="_blank"><img src="https://img.shields.io/twitter/follow/nestframework.svg?style=social&label=Follow" alt="Follow us on Twitter"></a>
</p>
  <!--[![Backers on Open Collective](https://opencollective.com/nest/backers/badge.svg)](https://opencollective.com/nest#backer)
  [![Sponsors on Open Collective](https://opencollective.com/nest/sponsors/badge.svg)](https://opencollective.com/nest#sponsor)-->

# Backend Application

This is the backend service for Fullstack Monorepo Starter project, built with NestJS and Prisma.

## Getting Started

### Prerequisites
- Node.js (v18 or higher)
- PNPM package manager
- PostgreSQL database

### Installation

1. From the root directory, install dependencies:
```bash
pnpm install
```

2. Set up your environment variables:
```bash
cp .env.example .env
```
Edit the `.env` file with your database credentials and other configuration.

3. Run database migrations:
```bash
pnpm prisma migrate dev
```

4. Start the development server:
```bash
pnpm dev
```

The API will be available at `http://localhost:3001`

## Development Guide

### Project Structure
```
apps/backend/
├── src/
│   ├── modules/         # Feature modules
│   ├── common/          # Shared code
│   ├── config/          # Configuration
│   └── main.ts         # Application entry point
├── prisma/             # Database schema and migrations
└── test/              # Test files
```

### Adding New Features

1. Create a new module:
```bash
pnpm nest generate module features/your-feature
```

2. Generate components:
```bash
pnpm nest generate controller features/your-feature
pnpm nest generate service features/your-feature
```

### Database Management

1. Update Prisma schema (`packages/database/prisma/schema.prisma`)
2. Generate Prisma client:
```bash
pnpm prisma generate
```

3. Create a migration:
```bash
pnpm prisma migrate dev --name your_migration_name
```

### API Documentation
- Swagger documentation is available at `/api/docs` when running in development mode
- Keep API documentation up to date using Swagger decorators

### Testing
```bash
# Unit tests
pnpm test

# E2E tests
pnpm test:e2e

# Test coverage
pnpm test:cov
```

### Best Practices
1. Follow NestJS architectural patterns
2. Use DTOs for request/response validation
3. Implement proper error handling
4. Write unit tests for services
5. Use guards for authentication/authorization
6. Follow RESTful API conventions

### Adding New Dependencies
1. Add backend-specific dependencies:
```bash
pnpm add -w @nestjs/something
```

2. Add development dependencies:
```bash
pnpm add -Dw @types/something
```

## Environment Variables

Key environment variables needed:
- `DATABASE_URL`: PostgreSQL connection string
- `JWT_SECRET`: Secret for JWT tokens
- `PORT`: API port (default: 3001)

## Troubleshooting

1. Database connection issues:
   - Verify PostgreSQL is running
   - Check database credentials in `.env`
   - Ensure migrations are up to date

2. Prisma issues:
   - Run `pnpm prisma generate` after schema changes
   - Clear Prisma cache: `pnpm prisma generate --force`

3. Module resolution errors:
   - Check import paths
   - Verify module is properly registered in `app.module.ts`

## Deployment

For production deployment:
1. Build the application:
```bash
pnpm build
```

2. Start in production mode:
```bash
pnpm start:prod
```

For more deployment options, check the [NestJS deployment documentation](https://docs.nestjs.com/deployment).

## Resources

- [NestJS Documentation](https://docs.nestjs.com)
- [Prisma Documentation](https://www.prisma.io/docs)
- [Project Wiki](internal-wiki-link)

## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

## Stay in touch

- Author - [Kamil Myśliwiec](https://twitter.com/kammysliwiec)
- Website - [https://nestjs.com](https://nestjs.com/)
- Twitter - [@nestframework](https://twitter.com/nestframework)

## License

Nest is [MIT licensed](https://github.com/nestjs/nest/blob/master/LICENSE).
