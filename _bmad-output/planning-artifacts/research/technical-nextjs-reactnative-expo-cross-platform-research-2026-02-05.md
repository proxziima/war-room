---
stepsCompleted: [1, 2, 3, 4]
inputDocuments: []
workflowType: 'research'
lastStep: 5
status: 'completed'
research_type: 'technical'
research_topic: 'Next.js Web App + React Native/Expo iOS App — Unified Architecture for Interactive Pixel Art'
research_goals: 'Evaluate stack fitness, deep dive into architecture patterns for unified backend, UI consistency across web and mobile, state management, scalability, and pixel art/sprite rendering feasibility'
user_name: 'Vinicius'
date: '2026-02-05'
web_research_enabled: true
source_verification: true
---

# Research Report: technical

**Date:** 2026-02-05
**Author:** Vinicius
**Research Type:** technical

---

## Research Overview

This technical research evaluates whether a **Next.js + React Native/Expo** stack can power an interactive pixel art application with sprite support, serving both web and iOS from a unified codebase. Research was conducted on 2026-02-05 using live web sources with multi-source verification. The report covers technology stack analysis, integration patterns, architectural design, and implementation roadmap with cost/risk assessment. **Verdict: The stack is a strong fit, scoring 7-9/10 across all evaluation criteria.**

---

<!-- Content will be appended sequentially through research workflow steps -->

## Technical Research Scope Confirmation

**Research Topic:** Next.js Web App + React Native/Expo iOS App — Unified Architecture for Interactive Pixel Art
**Research Goals:** Evaluate stack fitness, deep dive into architecture patterns for unified backend, UI consistency across web and mobile, state management, scalability, and pixel art/sprite rendering feasibility

**Technical Research Scope:**

- Architecture Analysis - design patterns, unified backend, monorepo structure
- Implementation Approaches - code sharing, pixel art/sprite rendering on web and native
- Technology Stack - frameworks, libraries, rendering engines for both platforms
- Integration Patterns - shared APIs, type safety, real-time protocols
- Performance Considerations - rendering performance, state management, scalability

**Research Methodology:**

- Current web data with rigorous source verification
- Multi-source validation for critical technical claims
- Confidence level framework for uncertain information
- Comprehensive technical coverage with architecture-specific insights

**Scope Confirmed:** 2026-02-05

## Technology Stack Analysis

### Programming Languages

**TypeScript** is the undisputed language for this entire stack. Both Next.js and React Native/Expo have first-class TypeScript support, and using a single language across web, mobile, and backend maximizes code sharing and developer productivity.

_Primary Language: TypeScript — shared across all layers (web, mobile, API, shared packages)_
_Runtime: Node.js for backend/build tooling; Hermes for React Native on iOS_
_Type Safety: End-to-end type safety achievable from database to UI via shared types in monorepo_
_Performance: Hermes engine (React Native) provides optimized bytecode compilation for mobile; V8/Node.js for server_
_Source: [React Native 2026 Overview](https://www.euroshub.com/blogs/react-native-2026-whats-new-and-what-to-expect)_

### Development Frameworks and Libraries

**Core Frameworks:**

| Layer | Technology | Role |
|-------|-----------|------|
| Web App | **Next.js 15+ (App Router)** | Server Components, Server Actions, API Routes, SSR/SSG |
| Mobile App | **React Native + Expo SDK 54+** | iOS native app with managed workflow |
| Shared Navigation | **Solito** | Unified navigation API across Next.js and React Native |
| Shared UI | **Tamagui** or **NativeWind** | Cross-platform styling with platform parity |
| Graphics/Pixel Art | **React Native Skia (@shopify/react-native-skia)** | GPU-accelerated 2D rendering, sprite sheets, Atlas API |
| Graphics (Web) | **HTML5 Canvas / PixiJS / Skia (WASM)** | Sprite rendering on web platform |
| Animation | **React Native Reanimated** | Thread-optimized animations at 60fps+ |

**NativeWind vs Tamagui for UI Consistency:**
- **NativeWind** (~403k weekly downloads): Brings Tailwind CSS utility classes to React Native. Best if the team already knows Tailwind. Explosive growth in 2025-2026.
- **Tamagui** (~75k weekly downloads): Designed from the ground up as a truly universal UI system with an optimizing compiler. More comprehensive cross-platform parity but steeper learning curve.

_Monorepo Tooling: Turborepo or Nx for build orchestration, caching, and affected-change detection_
_Expo SDK 52+ auto-configures Metro for monorepos — no manual Metro configuration needed_
_Source: [Expo Monorepo Docs](https://docs.expo.dev/guides/monorepos/), [Tamagui](https://tamagui.dev/), [NativeWind in Top 10 RN UI Libraries 2026](https://blog.logrocket.com/best-react-native-ui-component-libraries/)_

### Pixel Art & Sprite Rendering Engine

This is a critical area for the project's feasibility:

**React Native Skia — Atlas API (Mobile):**
- The `Atlas` component renders multiple instances of the same texture/sprite sheet with varying transformations (position, rotation, scale)
- GPU-accelerated via Skia's C++ backend — achieves consistent **60fps** (120fps on ProMotion displays)
- Hooks like `useRectBuffer` and `useRSXformBuffer` efficiently animate sprite positions and transformations
- Sprite sheets load a single image into memory, cycling through portions per frame — far more efficient than loading individual frame images
- **Known limitation**: Very large sprite sheets (>4096px) may cause issues on some devices ([GitHub Issue #2907](https://github.com/Shopify/react-native-skia/issues/2907))

**Web (Next.js) Rendering Options:**
- **HTML5 Canvas API**: Simple pixel art rendering, good for static or low-animation scenes
- **PixiJS**: Battle-tested 2D WebGL renderer for sprite sheets and interactive scenes — best option for complex pixel art on web
- **React Native Skia (WASM)**: Skia now supports web via WebAssembly, enabling shared rendering code across platforms

_Confidence: HIGH — Skia Atlas for sprites is production-proven (Shopify uses it extensively)_
_Source: [React Native Skia Atlas Docs](https://shopify.github.io/react-native-skia/docs/shapes/atlas/), [Sprite Animation with Skia + Reanimated](https://kf106.medium.com/animating-a-sprite-in-expo-react-native-using-react-native-skia-and-reanimated-7db0d4f579ec), [Skia Game Changer 2026](https://medium.com/@expertappdevs/skia-game-changer-for-react-native-in-2026-f23cb9b85841)_

### Database and Storage Technologies

**ORM Options for Next.js Backend:**

| ORM | Strengths | Best For |
|-----|-----------|----------|
| **Drizzle ORM** | Serverless-ready by design, no Rust binaries, SQL-transparent, lightweight | Edge/serverless, Vercel deployment, performance-critical |
| **Prisma ORM (v6.16+)** | Mature ecosystem, excellent DX, now supports client engine (no Rust) | Full-featured apps, complex relations, team familiarity |

**Database Options:**
- _Relational_: **PostgreSQL** (via Vercel Postgres, Neon, Supabase) — best for structured game data, user accounts, pixel art project metadata
- _Real-time_: **Supabase Realtime** or **Convex** — for collaborative pixel art editing
- _In-Memory/Cache_: **Redis (Upstash)** — serverless Redis for session management, real-time state, caching
- _File/Asset Storage_: **Vercel Blob**, **Cloudflare R2**, or **AWS S3** — for sprite sheets, exported pixel art images

_Recommendation: Drizzle ORM + PostgreSQL (Neon or Supabase) for serverless-optimized deployment_
_Source: [Prisma vs Drizzle 2026](https://medium.com/@thebelcoder/prisma-vs-drizzle-orm-in-2026-what-you-really-need-to-know-9598cf4eaa7c), [Drizzle + Vercel](https://orm.drizzle.team/docs/tutorials/drizzle-with-vercel-edge-functions), [Prisma Serverless Deploy](https://www.prisma.io/docs/orm/prisma-client/deployment/serverless/deploy-to-vercel)_

### State Management

**Recommended Pattern: Zustand + TanStack Query (federated state)**

| State Type | Tool | Scope |
|------------|------|-------|
| **Server/Async State** | **TanStack Query (React Query)** | API data fetching, caching, background refetching — works on both Next.js and React Native |
| **Client/UI State** | **Zustand** | Lightweight global store for UI state, pixel art canvas state, tool selection, undo/redo stacks |
| **Server State (Next.js only)** | **React Server Components** | Direct database access from server, no client-side state needed for SSR content |

- Zustand is the current default tech stack choice — small bundle, no boilerplate, works identically on web and native
- TanStack Query handles all async data (fetching art projects, user data, shared canvases) with automatic caching
- Clean separation prevents overfetching and keeps the UI reactive
- **Pixel art canvas state** (pixel grid, layers, current tool, undo history) fits perfectly in Zustand's mutable store pattern

_Confidence: HIGH — This is the dominant pattern in the React ecosystem for 2025-2026_
_Source: [Scalable State Management](https://medium.com/@fadli99xyz/mastering-scalable-state-management-in-next-js-with-tanstack-query-zustand-and-typescript-ecc0205db12e), [Federated State Patterns](https://dev.to/martinrojas/federated-state-done-right-zustand-tanstack-query-and-the-patterns-that-actually-work-27c0), [React State Management 2025](https://www.developerway.com/posts/react-state-management-2025)_

### Development Tools and Platforms

_IDE: VS Code / Cursor with TypeScript, ESLint, Prettier_
_Build System: Turborepo (incremental builds, remote caching) or Nx (affected detection, task orchestration)_
_Metro Bundler: Auto-configured by Expo SDK 52+ for monorepos — 3x faster cold startup (2025 improvements)_
_Testing: Vitest (unit), Playwright (web E2E), Detox or Maestro (mobile E2E)_
_Type Checking: TypeScript strict mode, shared types across packages_
_Linting: Biome or ESLint + Prettier for consistent formatting_
_Source: [Expo Monorepos](https://docs.expo.dev/guides/monorepos/), [React Native Wrapped 2025](https://www.callstack.com/blog/react-native-wrapped-2025-a-month-by-month-recap-of-the-year)_

### Cloud Infrastructure and Deployment

| Platform | Use Case |
|----------|----------|
| **Vercel** | Next.js deployment (SSR, Edge Functions, API Routes, Serverless) |
| **Expo EAS** | iOS builds, OTA updates, app store submission |
| **Neon / Supabase** | Serverless PostgreSQL with connection pooling |
| **Upstash** | Serverless Redis for caching and real-time features |
| **Vercel Blob / Cloudflare R2** | Asset storage for sprite sheets and exported art |
| **GitHub Actions** | CI/CD pipeline orchestrating both web and mobile builds |

_Serverless-First: Both Vercel and Expo EAS are serverless, scaling automatically with zero infra management_
_Edge Computing: Vercel Edge Functions for low-latency API responses globally_
_OTA Updates: Expo EAS Update pushes JS bundle updates without app store re-submission_
_Source: [Vercel + Prisma Guide](https://vercel.com/kb/guide/nextjs-prisma-postgres), [Expo 2026](https://metadesignsolutions.com/expo-2026-the-best-way-to-build-cross-platform-apps/)_

### Technology Adoption Trends

_Migration Pattern: The ecosystem is converging on universal React — write once, render natively on each platform_
_Emerging: React Native Skia replacing traditional Canvas/SVG for all graphics-heavy use cases_
_Emerging: Expo SDK 54 with isolated dependencies improving monorepo reliability_
_Growing: NativeWind overtaking Tamagui in adoption for cross-platform styling (Tailwind familiarity)_
_Growing: Drizzle ORM gaining ground over Prisma in serverless/edge environments_
_Stable: Zustand + TanStack Query as the dominant state management combination_
_Legacy Declining: Redux, Styled Components, and Expo "bare workflow" seeing reduced adoption_
_Source: [React Stack Patterns 2026](https://www.patterns.dev/react/react-2026/), [State of React Native 2024](https://results.stateofreactnative.com/en-US/animations/)_

## Integration Patterns Analysis

### API Design Patterns

**Primary Pattern: tRPC — End-to-End Type-Safe RPC**

For a monorepo with Next.js and React Native/Expo sharing a backend, **tRPC** is the strongest pattern. It provides end-to-end type safety without code generation — the React Native client imports router types directly from the Next.js server, and TypeScript enforces the contract at compile time.

_How it works: Define tRPC routers in a shared `packages/api` package. Both the Next.js web app and Expo mobile app consume the same typed procedures. Any API change instantly propagates type errors to all consumers._

| Pattern | Use Case | Fit for This Stack |
|---------|----------|-------------------|
| **tRPC** | Typed RPC between TS clients and server | **Best fit** — monorepo, same language, zero code generation |
| **REST (Route Handlers)** | Public APIs, webhook endpoints, third-party integrations | Good for external-facing endpoints |
| **GraphQL** | Complex data graphs, multiple client types | Overkill for same-language monorepo |
| **Server Actions** | Next.js web-only mutations | Web only — React Native cannot use Server Actions |

**Backend for Frontend (BFF) Pattern:**
Next.js Route Handlers can act as a BFF proxy — consolidating external microservices behind a single endpoint, handling authentication, transforming data, and passing requests to upstream APIs. Your React Native app makes fetch requests to `/api/*` endpoints just like the web app.

_Confidence: HIGH — tRPC + Next.js + Expo monorepo is a well-documented pattern with production boilerplates_
_Source: [tRPC](https://trpc.io/), [Next.js 15 + Expo + tRPC + Turborepo Boilerplate](https://github.com/smcroissant/boilerplate-next-expo-trpc), [Turborepo Monorepo Guide 2025](https://medium.com/@beenakumawat002/turborepo-monorepo-in-2025-next-js-react-native-shared-ui-type-safe-api-%EF%B8%8F-6194c83adff9), [Building APIs with Next.js](https://nextjs.org/blog/building-apis-with-nextjs)_

### Communication Protocols

**HTTP/HTTPS (Primary):**
All tRPC and REST calls use standard HTTP/HTTPS. Next.js Route Handlers support GET, POST, PUT, PATCH, DELETE, HEAD, OPTIONS. React Native's `fetch` API is identical to the web — same code can be shared.

**WebSocket (Real-Time Collaboration):**
For interactive pixel art with potential multiplayer/collaboration features, WebSocket is essential. However, Next.js API Routes are not designed for long-lived WebSocket connections. The recommended approaches:

| Approach | Pros | Cons |
|----------|------|------|
| **Supabase Realtime** | Built-in Broadcast, Presence, DB change listeners; works on web + React Native | Vendor lock-in to Supabase |
| **Pusher / Ably** | Managed WebSocket service, SDKs for both platforms | Paid per connection |
| **Socket.IO + Custom Server** | Full control, mature library | Requires separate server process |
| **Liveblocks / PartyKit** | Purpose-built for collaborative apps (presence, conflict resolution) | Specialized tooling |

**Supabase Realtime** is particularly strong here because it provides Broadcast (for cursor positions, tool selections), Presence (show who's online editing), and database change listeners (sync pixel changes) — all over WebSockets, with SDKs that work on both Next.js and React Native.

_Source: [Supabase Realtime Multiplayer](https://supabase.com/blog/supabase-realtime-with-multiplayer-features), [Collaborative Whiteboard with Next.js + Supabase](https://getstream.io/blog/collaborative-nextjs-whiteboard/), [Supabase Realtime React Native](https://www.restack.io/docs/supabase-knowledge-supabase-realtime-react-native)_

### Data Formats and Shared Validation

**Zod — Single Source of Truth for Data Contracts:**

In a monorepo, Zod schemas in a shared `packages/validation` package serve as the single source of truth for all data contracts. Both the Next.js backend and the React Native client validate against the same schemas.

```
packages/
  validation/          # Zod schemas — shared between all apps
    src/
      pixel-art.ts     # PixelArtProject schema
      user.ts          # User schema
      canvas.ts        # Canvas state schema
apps/
  web/                 # Next.js — imports from @repo/validation
  mobile/              # Expo — imports from @repo/validation
```

_Benefits:_
- `z.infer<typeof schema>` automatically generates TypeScript types from runtime validators
- Same validation runs on server (Route Handlers) and client (form inputs) — no drift
- tRPC integrates natively with Zod for input/output validation
- Runtime safety at API boundaries + compile-time type checking everywhere

_Data Formats: JSON over HTTP for all API communication. Binary formats (protobuf/msgpack) are unnecessary for this use case._
_Source: [Sharing Types with Zod Across Monorepo](https://leapcell.io/blog/sharing-types-and-validations-with-zod-across-a-monorepo), [Next.js API Validation with Zod](https://medium.com/@lucarestagno/how-to-validate-your-next-js-api-with-zod-and-typescript-51fa637c6231)_

### System Interoperability — Unified Auth

**Clerk — Cross-Platform Authentication:**

Clerk provides first-class SDKs for both **Next.js** and **Expo/React Native**, making it the ideal unified auth solution:

| Platform | SDK | Features |
|----------|-----|----------|
| **Next.js** | `@clerk/nextjs` | Middleware auth, Server Component support, protected API routes |
| **Expo** | `@clerk/clerk-expo` | Native auth flows, browser-based OAuth with deep linking, passkeys |

_Shared auth benefits:_
- Same user accounts work across web and mobile — single Clerk dashboard
- Short-lived JWTs (60s default) for stateless API auth on both platforms
- Multi-factor authentication, device tracking, bot detection out of the box
- Organization management for multi-tenant scenarios (e.g., shared pixel art teams)
- tRPC procedures can verify Clerk JWTs server-side — same auth middleware for web and mobile requests

_Alternative: Supabase Auth — if already using Supabase for database/realtime, its built-in auth avoids another service dependency_
_Source: [Clerk Expo Quickstart](https://clerk.com/docs/expo/getting-started/quickstart), [Clerk Expo SDK Reference](https://clerk.com/docs/reference/expo/overview), [Expo Auth Guide](https://docs.expo.dev/guides/using-clerk/), [Clerk Next.js Auth](https://clerk.com/nextjs-authentication)_

### Event-Driven Integration for Pixel Art

**Real-Time Pixel Art Sync Architecture:**

For collaborative pixel art editing, an event-driven pattern is critical:

1. **User draws pixels** → Local state updated immediately (optimistic update in Zustand)
2. **Pixel change event broadcast** → Supabase Realtime Broadcast sends delta to all connected clients
3. **Other clients receive** → Apply pixel delta to their local canvas state
4. **Periodic persistence** → Batch pixel changes and persist to PostgreSQL (debounced writes)
5. **Presence channel** → Show active collaborators, cursor positions, selected tools

_Event Types:_
- `pixel:draw` — Individual pixel or stroke changes (x, y, color, layer)
- `canvas:undo` / `canvas:redo` — Undo/redo operations broadcast
- `user:cursor` — Real-time cursor position broadcast
- `user:join` / `user:leave` — Presence events

_Conflict Resolution: Last-write-wins at the pixel level is sufficient for pixel art (unlike text, pixel conflicts are rare and visually obvious)_

_Source: [Real-time Collaboration with Yjs + Next.js](https://medium.com/@connect.hashblock/from-zero-to-real-time-building-a-live-collaboration-tool-with-yjs-and-next-js-e82eadccd828), [Supabase Realtime Docs](https://supabase.com/docs/guides/realtime)_

### Integration Security Patterns

**Layered Security Architecture:**

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **Auth** | Clerk (JWT) | Identity verification, short-lived tokens |
| **API Validation** | Zod schemas | Runtime input validation at every API boundary |
| **Transport** | HTTPS / WSS | Encrypted communication |
| **Rate Limiting** | Vercel Edge Middleware or Upstash Ratelimit | Prevent abuse on public endpoints |
| **CORS** | Next.js middleware | Control which origins can access API routes |
| **Row-Level Security** | Supabase RLS | Database-level access control per user/project |

_tRPC middleware chains can enforce auth checks, rate limits, and input validation at the procedure level — applied consistently for both web and mobile requests._
_Source: [Next.js Authentication Guide](https://nextjs.org/docs/app/guides/authentication), [Next.js API Security Guide 2025](https://artoonsolutions.com/nextjs-api-guide/)_

## Architectural Patterns and Design

### System Architecture Pattern: Serverless Monorepo with Platform-Specific Rendering

The recommended architecture is a **Turborepo monorepo with a serverless-first backend**, platform-specific rendering layers, and a shared core:

```
war-room/
├── apps/
│   ├── web/                    # Next.js 15+ App Router
│   │   ├── app/                # Pages, layouts, Server Components
│   │   ├── components/         # Web-specific UI (Canvas/PixiJS renderer)
│   │   └── next.config.ts
│   └── mobile/                 # Expo SDK 54+ (React Native)
│       ├── app/                # Expo Router screens
│       ├── components/         # Native-specific UI (Skia renderer)
│       └── app.config.ts
├── packages/
│   ├── api/                    # tRPC routers — shared backend logic
│   ├── db/                     # Drizzle ORM schemas + migrations
│   ├── validation/             # Zod schemas — single source of truth
│   ├── ui/                     # Shared UI components (NativeWind/Tamagui)
│   ├── canvas-core/            # Platform-agnostic pixel art logic
│   │   ├── state/              # Canvas state, layers, undo/redo
│   │   ├── tools/              # Pen, eraser, fill, selection
│   │   └── types/              # Sprite, layer, color types
│   └── config/                 # Shared configs (TS, ESLint, Tailwind)
├── turbo.json
└── package.json
```

**Key architectural decisions:**

| Decision | Choice | Rationale |
|----------|--------|-----------|
| Monorepo tool | Turborepo | Incremental builds, remote caching, simpler than Nx for this scale |
| Backend | Next.js Route Handlers + tRPC | Serverless, auto-scaling, no separate backend server |
| Database | Drizzle + PostgreSQL (Neon) | Serverless-native, edge-compatible, SQL-transparent |
| Realtime | Supabase Realtime | Managed WebSockets, Broadcast + Presence out of the box |
| Auth | Clerk | Cross-platform SDKs, managed auth, JWT-based |
| Rendering (web) | PixiJS or Skia WASM | GPU-accelerated 2D sprite rendering in browser |
| Rendering (mobile) | React Native Skia Atlas | GPU-accelerated sprite sheets at 60fps native |

_Architecture type: Server-first, Client-Islands — Server Components handle data fetching, SEO, and static content, while interactive pixel art canvases are client-side "islands" of interactivity._
_Source: [Next.js Architecture 2026 — Server-First, Client-Islands](https://www.yogijs.tech/blog/nextjs-project-architecture-app-router), [Modern Full Stack Architecture Next.js 15+](https://softwaremill.com/modern-full-stack-application-architecture-using-next-js-15/)_

### Design Principles and Best Practices

**Platform-Agnostic Core + Platform-Specific Renderers:**

The most critical architectural principle is separating **what** the pixel art editor does from **how** it renders:

```
packages/canvas-core/        ← Pure TypeScript logic (no React, no platform deps)
  ├── PixelGrid.ts           ← 2D array operations, color math
  ├── LayerManager.ts         ← Layer stack, visibility, blend modes
  ├── ToolEngine.ts           ← Pen, eraser, fill, selection algorithms
  ├── UndoRedoManager.ts      ← Command pattern + history stack
  └── SpriteSheetPacker.ts    ← Sprite atlas generation logic

apps/web/components/
  └── PixiCanvas.tsx          ← PixiJS renderer consuming canvas-core state

apps/mobile/components/
  └── SkiaCanvas.tsx          ← React Native Skia renderer consuming same state
```

This follows the **hexagonal architecture** (ports & adapters) principle — the domain logic has zero dependencies on frameworks. The rendering layer is an "adapter" that plugs into the core.

_Benefits:_
- Canvas-core is 100% testable with pure unit tests (no mocking React or Skia)
- New renderers (e.g., Electron desktop) can be added without touching core logic
- Business rules (max canvas size, layer limits, color palettes) live in one place

_Source: [Clean Architecture in React](https://alexkondov.com/full-stack-tao-clean-architecture-react/), [Hexagonal Architecture Frontend](https://www.dimitri-dumont.fr/en/blog/hexagonal-architecture-front-end)_

### Pixel Art Canvas State Architecture

**Undo/Redo: Command Pattern + Delta Compression**

For a pixel art editor, the undo/redo system is architecturally critical:

| Approach | Memory | Speed | Complexity |
|----------|--------|-------|-----------|
| **Full snapshot per action** | Very high (entire grid per operation) | Fast undo | Simple |
| **Command pattern (deltas)** | Low (only changed pixels stored) | Fast undo | Moderate |
| **Command + periodic snapshots** | Balanced (deltas + checkpoints) | Fast for recent, acceptable for deep undo | Best tradeoff |

**Recommended: Command Pattern with periodic snapshots**

```
UndoStack: [
  { type: 'draw', pixels: [{x:5, y:3, oldColor:'#000', newColor:'#f00'}] },
  { type: 'fill', pixels: [{x:0,y:0,...}, {x:1,y:0,...}, ...] },
  SNAPSHOT_MARKER,   ← Full grid state every N operations
  { type: 'draw', pixels: [{x:10, y:7, oldColor:'#fff', newColor:'#00f'}] },
]
```

- Each command stores only the delta (changed pixels with old + new values)
- Undo replays the inverse; redo replays forward
- Periodic full snapshots (every ~50 operations) enable fast deep-undo without replaying entire history
- Zustand store holds the current canvas state + undo/redo stacks

_Source: [Pixel Art Editor Undo/Redo Patterns](https://dev.to/theabbie/how-to-create-a-pixel-art-editor-using-html5-canvas-i7p), [Command Pattern for Undo/Redo — HN Discussion](https://news.ycombinator.com/item?id=15388154)_

### Scalability and Performance Patterns

**Serverless Auto-Scaling (Backend):**

| Concern | Solution | Scale Behavior |
|---------|----------|---------------|
| API requests | Vercel Serverless Functions | Auto-scales horizontally per request |
| Static pages | Vercel Edge Network (CDN) | Globally cached, near-zero latency |
| Database connections | Neon serverless driver (HTTP) | Connection pooling, no cold-start connection limits |
| Real-time channels | Supabase Realtime | Managed WebSocket infrastructure, scales per channel |
| Asset storage | Vercel Blob / Cloudflare R2 | CDN-distributed, scales infinitely |
| Auth | Clerk | Managed SaaS, scales independently |

**Next.js Caching Strategy for Pixel Art Gallery:**

| Page Type | Rendering | Caching |
|-----------|-----------|---------|
| Gallery / browse | SSG + ISR (revalidate: 60s) | Static pages refreshed every 60s |
| Individual art piece | ISR + on-demand revalidation | Cached until artist publishes update |
| User profile | SSR | Fresh on every request |
| Pixel art editor | Client-side only | No server rendering — pure client interactive canvas |
| API endpoints | No cache (dynamic) | Stateless serverless functions |

**Mobile Performance:**
- Expo EAS builds produce optimized native binaries with Hermes bytecode precompilation
- React Native Skia renders on the GPU thread, not the JS thread — UI remains responsive during complex rendering
- Reanimated runs animations on the UI thread — no JS bridge bottleneck
- Sprite sheet Atlas batches draw calls — rendering 1000 sprites is nearly as fast as rendering 1

_Confidence: HIGH — Vercel serverless + Supabase Realtime is a proven production stack that scales from 0 to millions of requests_
_Source: [Next.js Caching & Revalidation 2026](https://medium.com/@chandansingh73718/caching-revalidation-in-next-js-isr-fetch-cache-real-production-patterns-7433354a2591), [Vercel at Scale in Production](https://geekyants.com/blog/building-to-scale-my-experience-with-nextjs-and-vercel-in-production), [Serverless Functions Comparison 2026](https://research.aimultiple.com/serverless-functions/)_

### Offline-First Architecture (Mobile)

**Local-First Pattern for Pixel Art on iOS:**

For a pixel art editor, offline capability is essential — artists should be able to draw without an internet connection:

| Layer | Technology | Purpose |
|-------|-----------|---------|
| Local DB | **Expo SQLite** (via Drizzle ORM) | Store pixel art projects, layers, palettes locally |
| State sync | **Outbox event model** | Queue changes locally, sync when online |
| Cache | **TanStack Query** `persistQueryClient` | Cache API responses for offline gallery browsing |
| Assets | **Expo FileSystem** | Cache sprite sheets and exported images locally |

_Sync architecture:_
1. All edits write to local SQLite first (instant, offline-capable)
2. Changes queue in an outbox table with idempotency keys
3. When online, outbox events push to server → server persists to PostgreSQL
4. Pull latest changes from server → merge into local DB
5. Conflict resolution: Last-write-wins per pixel (same as realtime strategy)

_Benefits: Zero-latency drawing (no network round-trip), resilient to connection drops, seamless sync when back online_
_Source: [Expo Local-First Architecture Guide](https://docs.expo.dev/guides/local-first/), [Offline-First Expo with Drizzle ORM + SQLite](https://medium.com/@detl/building-an-offline-first-production-ready-expo-app-with-drizzle-orm-and-sqlite-f156968547a2)_

### Data Architecture Patterns

**Database Schema Strategy:**

```
PostgreSQL (Neon) — Server Database
├── users              # Clerk user references
├── projects           # Pixel art projects (name, dimensions, created_at)
├── layers             # Layers per project (order, name, visibility, blend_mode)
├── pixel_data         # Compressed pixel data per layer (JSONB or binary)
├── palettes           # Color palettes (shared and per-project)
├── sprites            # Sprite definitions (name, frames, animation config)
├── collaborators      # Project sharing / team access
└── asset_urls         # References to exported images in blob storage

Expo SQLite — Local Mobile Database (mirrors server schema)
├── projects_local     # Synced + local-only projects
├── layers_local       # Layer data with sync status
├── pixel_data_local   # Pixel data (source of truth while editing)
└── outbox             # Pending sync events
```

_Pixel data storage: For canvas sizes up to 256x256, a flattened JSONB array of color values is efficient. For larger canvases, binary compression (e.g., run-length encoding) stored as bytea reduces storage by 60-80% for pixel art (which has many adjacent same-color pixels)._

_Source: [Expo SQLite Complete Guide](https://medium.com/@aargon007/expo-sqlite-a-complete-guide-for-offline-first-react-native-apps-984fd50e3adb)_

### Deployment and Operations Architecture

**CI/CD Pipeline:**

```
GitHub Actions
├── On PR:
│   ├── Turborepo → affected:lint + affected:typecheck + affected:test
│   ├── Vercel Preview Deployment (web)
│   └── Expo EAS Preview Build (mobile — on demand)
├── On merge to main:
│   ├── Vercel Production Deployment (web — automatic)
│   ├── Drizzle DB migrations (if schema changed)
│   └── Expo EAS Build → App Store submission (on release tag)
└── On hotfix:
    └── Expo EAS Update (OTA JS bundle push — no App Store review)
```

**Monitoring & Observability:**
- Vercel Analytics + Speed Insights for web performance
- Sentry for error tracking (both web and React Native SDKs)
- Supabase Dashboard for database and realtime metrics
- Expo EAS Insights for mobile crash reporting and OTA update tracking

_Source: [Expo 2026 Cross-Platform Guide](https://metadesignsolutions.com/expo-2026-the-best-way-to-build-cross-platform-apps/), [Next.js + Vercel High-Performance Guide 2026](https://finlyinsights.com/build-high-performance-site-with-next-js-and-vercel/)_

## Implementation Approaches and Technology Adoption

### Technology Adoption Strategy: Incremental Build-Up

**Recommended Phase Approach (not big-bang):**

| Phase | Focus | Duration (est.) | Deliverable |
|-------|-------|-----------------|-------------|
| **Phase 1 — Foundation** | Monorepo scaffolding, shared packages, auth, basic DB | 2-3 weeks | Working monorepo with auth on web + mobile |
| **Phase 2 — Canvas Core** | Platform-agnostic pixel art engine, undo/redo, tools | 2-4 weeks | `canvas-core` package with unit tests |
| **Phase 3 — Web Renderer** | Next.js app with PixiJS/Canvas pixel art editor | 2-3 weeks | Functional web pixel art editor |
| **Phase 4 — Mobile Renderer** | Expo app with Skia Atlas renderer, same canvas-core | 2-3 weeks | Functional iOS pixel art editor |
| **Phase 5 — Backend & Sync** | tRPC API, project persistence, cloud save/load | 1-2 weeks | Projects saved to PostgreSQL, synced across platforms |
| **Phase 6 — Realtime & Polish** | Supabase Realtime collaboration, offline-first, sprites | 2-3 weeks | Multiplayer editing, sprite animations, offline mode |

**Why incremental:** Each phase produces a testable deliverable. Phase 2 (canvas-core) is the highest-risk area — isolating it early validates the core product feasibility before investing in platform renderers.

_Source: [Turborepo + React Native + Next.js Production Guide 2025](https://medium.com/better-dev-nextjs-react/setting-up-turborepo-with-react-native-and-next-js-the-2025-production-guide-690478ad75af), [Universal React Monorepo Guide](https://www.gurselcakar.com/monorepo)_

### Development Workflows and Tooling

**Daily Development Workflow:**

```
# Start all apps in parallel (Turborepo)
pnpm dev                        # Starts Next.js + Expo + tRPC dev servers

# Web development
pnpm --filter web dev           # Next.js dev server on localhost:3000

# Mobile development
pnpm --filter mobile start      # Expo dev server → iOS Simulator via Expo Go

# Shared packages (auto-rebuild on change)
pnpm --filter canvas-core dev   # Watch mode — changes reflect in both apps
```

**Key Tooling Decisions:**

| Tool | Purpose | Why |
|------|---------|-----|
| **pnpm** | Package manager | Faster than npm/yarn, strict dependency hoisting, workspace protocol |
| **Turborepo** | Build orchestrator | Incremental builds, remote caching (free for teams), simple config |
| **TypeScript strict mode** | Type safety | Catches bugs at compile time across the entire monorepo |
| **Biome** | Linting + formatting | Single tool replaces ESLint + Prettier, 100x faster |
| **Vitest** | Unit/integration tests | Fast, native ESM, Jest-compatible API |
| **Playwright** | Web E2E tests | Cross-browser, reliable, auto-waiting |
| **Maestro** | Mobile E2E tests | Simple YAML-based flows, integrates with Expo EAS Workflows |

_Expo SDK 52+ auto-detects monorepo — no manual Metro configuration needed. Turborepo caches build artifacts remotely, so CI runs finish in minutes._
_Source: [Expo Monorepo Docs](https://docs.expo.dev/guides/monorepos/), [Turborepo Next.js Guide](https://turborepo.dev/docs/guides/frameworks/nextjs)_

### Testing and Quality Assurance

**Testing Pyramid for Cross-Platform Pixel Art App:**

```
                    ┌─────────┐
                    │  E2E    │  Maestro (mobile) + Playwright (web)
                   ─┤  Tests  ├─  Smoke tests for critical flows
                  / └─────────┘ \
                 /                \
               ┌───────────────────┐
               │  Integration      │  tRPC procedure tests, Drizzle queries
               │  Tests            │  API + DB integration with test containers
               └───────────────────┘
              /                      \
            ┌─────────────────────────┐
            │  Unit Tests             │  canvas-core logic, Zod schemas,
            │  (largest layer)        │  undo/redo, tool algorithms, state
            └─────────────────────────┘
```

| Layer | Tool | What It Tests |
|-------|------|--------------|
| **Unit** | Vitest | `canvas-core` (pixel grid ops, undo/redo, fill algorithm, layer math) — pure logic, no React |
| **Component** | React Testing Library | Shared UI components, form validation, tool palettes |
| **Integration** | Vitest + Drizzle test utils | tRPC routers against a test PostgreSQL, auth middleware |
| **E2E Web** | Playwright | Full drawing flow, save/load, gallery browsing, auth |
| **E2E Mobile** | Maestro | Drawing on iOS, offline mode, sync, navigation |

_Critical: The `canvas-core` package being pure TypeScript (no React) means 80%+ of core logic tests run in milliseconds with zero DOM/native mocking._
_Source: [React Native Testing Overview](https://reactnative.dev/docs/testing-overview), [Expo E2E Tests with Maestro](https://docs.expo.dev/eas/workflows/examples/e2e-tests/), [Testing React Native TV 2026](https://www.callstack.com/blog/testing-react-native-tv-apps)_

### Cost Optimization and Resource Management

**Monthly Cost Breakdown (Production Estimates):**

| Service | Plan | Cost/month | What You Get |
|---------|------|-----------|--------------|
| **Vercel** | Pro | $20 + usage | Next.js hosting, serverless, CDN, preview deploys |
| **Expo EAS** | Production | $99 | iOS builds, OTA updates, priority queuing |
| **Neon** | Launch | $5-19 | Serverless PostgreSQL, scale-to-zero, 10GB storage |
| **Supabase** | Pro | $25 | Realtime, Auth (if not using Clerk), 8GB storage |
| **Clerk** | Pro | $25 | Auth for up to 10K MAU, both web + mobile |
| **Sentry** | Developer | $0-26 | Error tracking for web + mobile |
| **Apple Developer** | Annual | $8.25/mo ($99/yr) | iOS App Store submission |
| | **Total** | **~$200-225/mo** | Full production stack |

**Free Tier Development Stack (for building/prototyping):**

| Service | Free Tier Limits |
|---------|-----------------|
| **Vercel** | Hobby — personal projects, limited builds |
| **Expo EAS** | Free — 1 iOS build/day, 1000 OTA updates/mo |
| **Neon** | Free — 0.5GB storage, 100 compute-hours/mo |
| **Supabase** | Free — 500MB storage, 50K MAU, 2 Realtime channels |
| **Clerk** | Free — 10K MAU, all auth methods |
| **Total** | **$0/mo** (development only, not production) |

**Cost Optimization Tips:**
- Use ISR/SSG aggressively to minimize serverless invocations (gallery pages)
- Neon scale-to-zero avoids paying for idle database time
- Expo EAS Update (OTA) avoids expensive full iOS builds for JS-only changes
- Batch pixel persistence writes to reduce database operations
- Use Vercel Image Optimization for gallery thumbnails instead of self-hosting

_Source: [Vercel Pricing](https://vercel.com/pricing), [Expo EAS Pricing](https://expo.dev/pricing), [Neon Pricing 2026](https://vela.simplyblock.io/articles/neon-serverless-postgres-pricing-2026/), [Vercel Cost Optimization Guide](https://pagepro.co/blog/vercel-hosting-costs/)_

### Risk Assessment and Mitigation

| Risk | Severity | Likelihood | Mitigation |
|------|----------|------------|------------|
| **Large sprite sheets (>4096px) fail on Skia Atlas** | Medium | Medium | Tile sprite sheets into 2048x2048 chunks; test early on target devices |
| **Canvas performance degrades on older iPhones** | Medium | Low | Skia runs on GPU — profile on iPhone 11 as baseline; limit canvas to 512x512 on lower devices |
| **Monorepo tooling complexity** | Medium | Medium | Use proven Turborepo template; Expo SDK 52+ auto-configures Metro |
| **WebSocket connection limits at scale** | Low | Low | Supabase Realtime manages infrastructure; implement reconnection logic |
| **Vendor lock-in (Vercel/Supabase/Clerk)** | Low | Continuous | Architecture uses standard interfaces (HTTP, PostgreSQL, JWT) — each service replaceable |
| **React Native breaking changes** | Medium | Low | Pin Expo SDK version; Expo manages RN compatibility |
| **App Store rejection** | Medium | Low | Follow Apple HIG; use Expo EAS review guidelines; no private API usage |
| **State sync conflicts in multiplayer** | Low | Medium | Last-write-wins per pixel; visual conflicts are obvious and self-correcting |
| **Excessive re-renders causing jank** | Medium | Medium | Skia renders on GPU thread (not JS); Reanimated on UI thread; profile with React DevTools |

_Most critical risk: The pixel art rendering engine (`canvas-core` + platform renderers) is the highest-uncertainty area. Mitigate by building a proof-of-concept in Phase 2 before committing to the full platform._
_Source: [React Native Challenges](https://mobidev.biz/blog/react-native-app-development-guide), [Skia Rendering Issue #987](https://github.com/Shopify/react-native-skia/issues/987)_

## Technical Research Recommendations

### Stack Verdict: Is This Stack the Right Fit?

**YES — with caveats.**

| Criterion | Assessment | Score |
|-----------|-----------|-------|
| **Can it handle pixel art with sprites?** | YES — Skia Atlas (mobile) + PixiJS/Canvas (web) are GPU-accelerated and production-proven | 9/10 |
| **Unified backend serving both platforms?** | YES — Next.js Route Handlers + tRPC serve both web and mobile from one codebase | 9/10 |
| **UI consistency across web and mobile?** | GOOD — NativeWind/Tamagui for shared styling; platform-specific renderers for canvas | 7/10 |
| **State management scalability?** | YES — Zustand + TanStack Query is the dominant, lightweight pattern | 9/10 |
| **Can it scale?** | YES — Serverless auto-scaling at every layer (Vercel, Neon, Supabase, Clerk) | 9/10 |
| **Offline capability?** | YES — Expo SQLite + outbox pattern for local-first mobile editing | 8/10 |
| **Developer experience?** | EXCELLENT — TypeScript end-to-end, hot reload on both platforms, monorepo code sharing | 9/10 |
| **Cost efficiency?** | GOOD — Free tier for development; ~$200/mo for production | 8/10 |

**Caveats:**
1. The canvas rendering layer **cannot be shared** between web and mobile — you'll need platform-specific renderers (PixiJS for web, Skia for mobile). The core logic (pixel grid, tools, undo/redo) is shared.
2. Very large canvases (>512x512) will need careful optimization on mobile — memory and GPU constraints differ by device.
3. Real-time collaboration adds significant complexity — consider it a Phase 6 stretch goal, not a launch requirement.

### Implementation Roadmap

```
Week 1-3:   FOUNDATION
            ├── Turborepo monorepo + pnpm workspaces
            ├── Next.js 15 App Router (apps/web)
            ├── Expo SDK 54 (apps/mobile)
            ├── Clerk auth (both platforms)
            ├── Drizzle + Neon PostgreSQL (packages/db)
            ├── tRPC setup (packages/api)
            └── Zod shared schemas (packages/validation)

Week 4-7:   CANVAS CORE (highest risk — build PoC first)
            ├── packages/canvas-core (pure TypeScript)
            ├── PixelGrid, LayerManager, ToolEngine
            ├── Command pattern undo/redo
            ├── SpriteSheet types and animation logic
            └── Comprehensive unit test suite

Week 8-10:  PLATFORM RENDERERS
            ├── Web: PixiJS or Canvas renderer in apps/web
            ├── Mobile: Skia Atlas renderer in apps/mobile
            ├── Touch/mouse input handling per platform
            └── Performance profiling on target devices

Week 11-12: PERSISTENCE & SYNC
            ├── Save/load projects via tRPC
            ├── Cloud storage for exported images
            ├── Expo SQLite local-first (mobile)
            └── Gallery pages with ISR caching

Week 13-15: POLISH & LAUNCH
            ├── Sprite animation preview
            ├── Color palettes, export formats
            ├── App Store submission via Expo EAS
            ├── E2E tests (Playwright + Maestro)
            └── Monitoring (Sentry + Vercel Analytics)

Week 16+:   STRETCH GOALS
            ├── Supabase Realtime multiplayer
            ├── Collaborative editing
            ├── Community gallery / social features
            └── Android support (Expo — already cross-platform)
```

### Technology Stack Recommendations (Final)

| Layer | Recommended | Alternative |
|-------|------------|-------------|
| **Monorepo** | Turborepo + pnpm | Nx (if team prefers) |
| **Web Framework** | Next.js 15+ App Router | — |
| **Mobile Framework** | Expo SDK 54+ | — |
| **API Layer** | tRPC v11 | REST Route Handlers (for external APIs) |
| **Database** | Drizzle ORM + Neon PostgreSQL | Prisma + Supabase (if preferring Supabase ecosystem) |
| **Auth** | Clerk | Supabase Auth (if all-in on Supabase) |
| **Realtime** | Supabase Realtime | Liveblocks, Pusher |
| **State (client)** | Zustand | Jotai |
| **State (server)** | TanStack Query | SWR |
| **Validation** | Zod v4 | — |
| **UI Styling** | NativeWind (Tailwind) | Tamagui |
| **Rendering (mobile)** | React Native Skia + Reanimated | — |
| **Rendering (web)** | PixiJS or Skia WASM | HTML5 Canvas (simpler, less performant) |
| **Testing** | Vitest + Playwright + Maestro | Jest + Detox |
| **CI/CD** | GitHub Actions + Vercel + EAS | — |
| **Monitoring** | Sentry + Vercel Analytics | — |

### Skill Development Requirements

For an intermediate developer (your profile), the key areas to invest in:

| Skill Area | Priority | Resources |
|------------|----------|-----------|
| React Native Skia (Atlas, sprites) | **Critical** | [Skia Docs](https://shopify.github.io/react-native-skia/docs/shapes/atlas/), [Sprite Animation Tutorial](https://kf106.medium.com/animating-a-sprite-in-expo-react-native-using-react-native-skia-and-reanimated-7db0d4f579ec) |
| tRPC with Next.js + Expo | High | [tRPC Docs](https://trpc.io/), [Boilerplate](https://github.com/smcroissant/boilerplate-next-expo-trpc) |
| Turborepo monorepo setup | High | [Production Guide](https://medium.com/better-dev-nextjs-react/setting-up-turborepo-with-react-native-and-next-js-the-2025-production-guide-690478ad75af) |
| Drizzle ORM | Medium | [Drizzle Docs](https://orm.drizzle.team/) |
| Zustand state management | Medium | [Zustand GitHub](https://github.com/pmndrs/zustand) |
| PixiJS for web canvas | Medium | [PixiJS Docs](https://pixijs.com/) |

### Success Metrics and KPIs

| Metric | Target | Measurement |
|--------|--------|-------------|
| Canvas rendering FPS (mobile) | >= 60fps | React Native Perf Monitor |
| Canvas rendering FPS (web) | >= 60fps | Chrome DevTools |
| API response time (p95) | < 200ms | Vercel Analytics |
| Time to Interactive (web) | < 2s | Lighthouse |
| App startup time (iOS) | < 1.5s | Expo EAS Insights |
| Code sharing ratio | >= 60% | Lines of code in packages/ vs apps/ |
| Undo/redo latency | < 16ms (1 frame) | Custom profiling |
| Offline draw-to-sync | < 5s after reconnect | Custom metric |
| Test coverage (canvas-core) | >= 90% | Vitest coverage report |
