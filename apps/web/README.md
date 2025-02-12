# Web Application

This is the frontend application of Fullstack Monorepo Starter project built with Next.js and shadcn/ui components.

## Getting Started

### Prerequisites
- Node.js (v18 or higher)
- PNPM package manager

### Installation
1. From the root directory, install dependencies:
```bash
pnpm install
```

2. Start the development server:
```bash
pnpm dev
```

The application will be available at `http://localhost:3000`

## Development Guide

### Adding New Pages
1. Create new pages in the `app` directory following Next.js 13+ conventions
2. Use the page.tsx format for your routes
3. Group related routes in folders

### Adding shadcn Components

1. To add a new shadcn component, use the CLI from the web directory:
```bash
pnpm dlx shadcn@canary add [COMPONENT]
```

Example:
```bash
pnpm dlx shadcn@canary add card
pnpm dlx shadcn@canary add button scroll-area
```

Available components can be found at [shadcn/ui components](https://ui.shadcn.com/docs/components)

### Project Structure
```
apps/web/
├── app/                # Next.js app directory
├── components/         # React components
│   ├── ui/            # shadcn components
│   └── custom/        # Custom components
├── lib/               # Utility functions
├── styles/            # Global styles
└── public/            # Static assets
```

### Best Practices
1. Use TypeScript for all new components and pages
2. Follow the existing component structure
3. Use shadcn components when available instead of creating new ones
4. Utilize the shared UI package from the monorepo when applicable

### Styling
- Use Tailwind CSS for styling
- Follow the project's color scheme and design tokens
- Customize shadcn components in the `components/ui` directory

### State Management
- Use React hooks for local state
- For global state, follow the established patterns in the project

### Testing
Run tests with:
```bash
pnpm test
```

## Troubleshooting
Common issues and their solutions:

1. shadcn component not working:
   - Ensure all dependencies are installed
   - Check if the component is properly imported
   - Verify the component is added to your tailwind.config.js

2. Styling issues:
   - Clear the .next cache: `pnpm clean`
   - Rebuild the application: `pnpm build` 
