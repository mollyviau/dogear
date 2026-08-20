# Dog Ear

A reading tracker for people who want more than a catalogue.

> **Status: in active development.** Not yet released. The app runs locally but is pre-alpha — expect breaking changes, incomplete features, and schema churn.

## Why this exists

Most reading trackers are catalogues. You log what you finished, you rate it out of five, and the app hands you a shelf. That works if your goal is a record. It doesn't help with the harder question, which is what to read next.

Dog Ear is built around that question. It uses your reading history and stated interests to generate recommendations and build reading lists you'd actually follow, rather than surfacing whatever is popular this month. The name is the gesture it's designed around — marking something to come back to.

It's also built to be fast. Existing options are slow to open, slow to search, and heavy with social features most readers don't use. Dog Ear aims to be quick enough that logging a book takes less effort than not bothering.

## Status
Currently at the planning and setup stage. The sections below describe
what Dog Ear is being built to do, not what it does today.


**Planned Features**
- AI-assisted recommendations based on reading history
- Generated reading lists around themes and goals
- Book search and library management
- Reading status tracking
- Reading statistics and progress views
- Import from existing services

## Tech stack

| Layer | Choice |
|---|---|
| Framework | React Native + Expo |
| Routing | Expo Router |
| Language | TypeScript |
| Backend | Supabase (Postgres, auth) |
| Server state | TanStack Query |
| Client state | Zustand |
| Styling | NativeWind |

**A note on the state split.** TanStack Query owns anything that comes from the server — the library, book data, recommendations — including caching and revalidation. Zustand holds only local UI state that never needs to persist. Keeping that boundary strict is what stops the two from drifting out of sync, which was the main source of bugs in an earlier iteration.

## Getting started

### Prerequisites

- Node.js 18 or later
- A Supabase project
- Expo Go on a physical device, or an iOS/Android simulator

### Setup

```bash
git clone https://github.com/YOUR-USERNAME/dogear.git
cd dogear
npm install
```

Copy the example environment file and fill in your Supabase credentials:

```bash
cp .env.example .env
```

```
EXPO_PUBLIC_SUPABASE_URL=your-project-url
EXPO_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
```

<!-- TODO: add any other required keys, e.g. the AI provider -->

### Running

```bash
npx expo start
```

Scan the QR code with Expo Go, or press `i` / `a` to open a simulator.

### Database

<!-- TODO: document how to set up the schema — migrations, SQL file, or Supabase dashboard steps -->

## Project structure

```
app/          Expo Router routes
components/   Shared UI components
lib/          Supabase client, API helpers
stores/       Zustand stores
types/        Shared TypeScript types
```

<!-- TODO: adjust to match your actual tree -->

## Roadmap

- [ ] Core library and tracking flow
- [ ] Recommendation engine
- [ ] Reading list generation
- [ ] Statistics view
- [ ] Beta release

## License

Copyright © 2026 Molly Viau. All rights reserved.

This source is published for reference and review. It is not licensed for reuse, modification, or redistribution.

## Contact

Built by Molly Viau — [mollyviau.com](https://mollyviau.com) · [contact@mollyviau.com](mailto:contact@mollyviau.com)

