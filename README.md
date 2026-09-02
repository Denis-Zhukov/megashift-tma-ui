# MegaShift TMA UI

Telegram Mini App for managing work shifts. Employees can plan and track shifts and view salary statistics.

> The backend lives in a sibling repo: [megashift-tma-server](https://github.com/ZhukovLabs/megashift-tma-server)

## Tech stack

- **Next.js 16** — framework
- **React 19** — UI
- **TypeScript** — typing
- **Tailwind CSS 4** + DaisyUI — styling
- **Zustand** — state management
- **React Query** — server state
- **React Hook Form + Zod** — forms and validation
- **TMA SDK** — Telegram integration
- **next-intl** — internationalization (ru/en)
- **Framer Motion** — animations

## Project structure

```
├── app/                    # Next.js App Router pages
│   ├── (authenticated)/    # Protected routes
│   │   ├── schedule/       # Shift calendar
│   │   ├── shifts/         # Shift management
│   │   ├── statistics/     # Stats and charts
│   │   └── settings/       # Profile settings
│   ├── onboarding/         # Onboarding
│   └── layout.tsx          # Root layout
├── components/             # UI components
├── entities/               # Domain entities
│   ├── user/               # User
│   ├── currency/           # Currencies
│   └── salary/             # Salary
├── hooks/                  # Custom React hooks
├── store/                  # Zustand stores
├── lib/                    # Utilities (axios, react-query)
└── i18n/                   # Internationalization
```

## Installation

```bash
npm install
```

## Running

```bash
npm run dev
```

## Scripts

- `npm run dev` — development
- `npm run build` — production build
- `npm run start` — production start
- `npm run lint` — linting

## Docker

```bash
# Build
docker build -t planner .

# Run
docker run -p 3000:3000 planner
```

## Environment variables

Create a `.env.local`:

```
# API URL (required)
NEXT_PUBLIC_API_URL=

# Optional
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

## Available languages

- 🇷🇺 Russian (default)
- 🇬🇧 English

## Development

The project follows a feature-based architecture. When adding new functionality:

1. Create components in `components/`
2. Add types to the corresponding entity in `entities/`
3. Use Zustand for local state
4. Use React Query for server state
