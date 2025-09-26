# Copilot Instructions for NeuroSathi

## Project Overview
NeuroSathi is a full-stack web application built with Next.js (frontend) and FastAPI (backend). The codebase is organized for modularity and scalability, with clear separation between UI components, business logic, and server-side functionality.

## Architecture & Key Directories
- **client/src/components/ui/**: Reusable UI components (e.g., calendar, button, dialog). Follow composable React patterns and Tailwind CSS for styling.
- **client/src/components/**: Feature modules (ai-chatbot, booking-system, meditation-center, etc.) are self-contained and may use UI primitives from `ui/`.
- **client/src/pages/**: Page-level components for routing and layout. Use Next.js conventions for navigation and data fetching.
- **client/src/hooks/**: Custom React hooks for shared logic (e.g., authentication, toast notifications).
- **client/src/lib/**: Utility functions and shared logic (e.g., protected routes, query client setup).
- **server/**: FastAPI backend entry points, routes, authentication, and storage logic. Integrates with frontend via REST APIs.
- **shared/schema.ts**: Shared data models and types for frontend-backend consistency.

## Developer Workflows
- **Build/Run Frontend**: Use Vite for local development. Main entry: `client/src/main.tsx`. Build config: `vite.config.ts`, `tailwind.config.ts`.
- **Build/Run Backend**: FastAPI server code in `server/`. Start with `server/index.ts` or `server/vite.ts`.
- **Styling**: Tailwind CSS is configured via `tailwind.config.ts` and `postcss.config.js`.
- **TypeScript**: Strict typing enforced via `tsconfig.json`.

## Patterns & Conventions
- **Component Structure**: Prefer function components. Use props for configuration. Co-locate styles and tests (if any) with components.
- **State Management**: Use React Query (`lib/queryClient.ts`) for data fetching and caching.
- **Routing**: Use Next.js page conventions. Protect routes via `lib/protected-route.tsx`.
- **API Communication**: Frontend communicates with backend via REST endpoints defined in `server/routes.ts`.
- **Authentication**: Centralized in `server/auth.ts` and `hooks/use-auth.tsx`.
- **Toast/Notifications**: Use `hooks/use-toast.ts` and `components/ui/toast.tsx`.

## Integration Points
- **External Libraries**: Tailwind CSS, React Query, Vite, FastAPI.
- **Shared Types**: Use `shared/schema.ts` for consistent data models.

## Example: Adding a New Feature
1. Create a new component in `client/src/components/`.
2. Use UI primitives from `ui/` and hooks from `hooks/`.
3. Define any new API endpoints in `server/routes.ts`.
4. Update shared types in `shared/schema.ts` if needed.

## Tips for AI Agents
- Always check for shared logic in `lib/` and `hooks/` before duplicating code.
- Follow the established folder structure for new features.
- Use TypeScript types from `shared/schema.ts` for API payloads.
- Reference `vite.config.ts` and `tailwind.config.ts` for build/styling issues.

---

Please review these instructions. If any section is unclear or missing important project-specific details, let me know so I can refine further.