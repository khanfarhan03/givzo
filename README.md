# Givzo

A Vite + React + TypeScript starter/project scaffold using shadcn/ui + Radix primitives, Tailwind CSS, and common modern libraries (React Router, TanStack Query, Firebase, SendGrid, Zod). This repository provides a front-end application built with Vite and TypeScript and is preconfigured for fast local development and production builds.

I inspected the repository (package.json, vite/tailwind/tsconfig files) to assemble this README. If you'd like, I can open a PR to replace the existing README.md with this file.

## Features

- Vite + React + TypeScript
- Tailwind CSS (with animations & typography plugin)
- Radix UI primitives and shadcn-style components
- React Router for routing
- TanStack Query for server state
- Firebase client integration
- SendGrid for transactional emails (client/server wiring expected as needed)
- Form handling (react-hook-form + zod validation)
- Utility libraries: clsx, date-fns, lucide-react icons, recharts, embla carousel, etc.

## Tech stack / notable dependencies

- Framework: React 18
- Bundler: Vite
- Language: TypeScript
- Styling: Tailwind CSS
- UI: Radix + shadcn patterns
- State / Data: @tanstack/react-query
- Auth/Backend: firebase
- Email: @sendgrid/mail
- Validation: zod
- Dev tooling: eslint, typescript, vite-plugin-react-swc

(See package.json for the full dependency list.)

## Quickstart

Prerequisites
- Node.js (recommended 18+)
- npm, pnpm or yarn (or Bun — repo contains bun.lockb)
- Git

Install dependencies
- npm
  - npm install
- pnpm
  - pnpm install
- yarn
  - yarn install
- bun
  - bun install

Run development server
- npm run dev
- The app will be served by Vite (typically at http://localhost:5173 unless configured otherwise).

Build for production
- npm run build
- Preview a production build locally:
  - npm run preview

Linting
- npm run lint

## Environment / Configuration

This project likely depends on environment variables for services such as Firebase and SendGrid. Create a `.env` file at the project root (not committed) and add keys similar to:

```
# Example (names may vary in code—check source files)
VITE_FIREBASE_API_KEY=your_firebase_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_firebase_auth_domain
VITE_FIREBASE_PROJECT_ID=your_firebase_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_firebase_storage_bucket
VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
VITE_FIREBASE_APP_ID=your_app_id

SENDGRID_API_KEY=your_sendgrid_api_key
```

Note: Vite-exposed variables intended for client use must be prefixed with `VITE_`. Secrets for server-side usage (like SendGrid API keys) should be kept on a backend and never exposed client-side.

## Project layout (high level)

- index.html — Vite entry HTML
- vite.config.ts — Vite configuration
- src/ — application source (React + TypeScript components, routes, styles)
- tailwind.config.ts — Tailwind configuration
- postcss.config.js — PostCSS config
- tsconfig.json / tsconfig.app.json — TypeScript configs
- package.json — scripts & dependency list

Adjust paths above if your code lives in a different structure.

## Scripts

Defined in package.json:
- dev — start Vite dev server
- build — build production assets
- build:dev — build with development mode
- preview — serve production build locally
- lint — run ESLint

Use the appropriate package manager prefix if you use pnpm/yarn/bun.

## Deployment

This app builds a static bundle that can be deployed to most static hosts:
- Vercel, Netlify, Cloudflare Pages, Surge, GitHub Pages, or any static file hosting
- For SSR or server-side needs, adapt accordingly (e.g., add server endpoints for SendGrid/Firebase Admin operations)

General steps:
1. Set environment variables in your host (Firebase config for client; any server secrets in backend)
2. Build: `npm run build`
3. Deploy the `dist` (or Vite's output) folder per your hosting provider's instructions

## Contributing

Contributions, issues, and feature requests are welcome.

Suggested process:
1. Fork the repo
2. Create a feature branch (git checkout -b feature/your-feature)
3. Commit changes with clear messages
4. Open a pull request explaining the change

Please follow the existing code style and run linting before submitting changes.

## Notes / TODOs

- Confirm exact environment variable names used in the source (search for `process.env` or `import.meta.env`).
- Add a .env example with the exact keys.
- Add CI (GitHub Actions) for lint/build checks if desired.
- If server-side email sending or secure Firebase admin tasks are required, implement a backend to hold secrets.

## License

Add a license file if you want this project published under a specific license (MIT is common). Currently, no license file is present.

## Maintainer / Contact

Repository: [khanfarhan03/givzo](https://github.com/khanfarhan03/givzo)  
Maintainer: khanfarhan03

---
