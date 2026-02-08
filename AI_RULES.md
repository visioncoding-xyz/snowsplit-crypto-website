# AI Rules & Guidelines

This document outlines the technical stack and coding standards for this project. All AI-generated code must adhere to these rules.

## Tech Stack

- **Framework:** Next.js 16+ (App Router)
- **Language:** TypeScript
- **UI Library:** React 19+
- **Styling:** Tailwind CSS 4+ (Utility-first)
- **Component Primitives:** Radix UI (Headless, accessible primitives)
- **Component System:** shadcn/ui (Copy-paste component architecture)
- **Icons:** Lucide React
- **Animations:** `tailwindcss-animate` & CSS Keyframes
- **Theming:** `next-themes` (Dark/Light mode support)
- **Forms:** React Hook Form + Zod validation
- **Charts:** Recharts

## Development Rules

### 1. Component Architecture
- **Location:** Generic UI components belong in `components/ui/`. Feature-specific components belong in `components/` or feature-specific subfolders.
- **Pattern:** Use the shadcn/ui pattern. Components should be built using Radix UI primitives where applicable.
- **Client vs Server:** Default to Server Components. Add `"use client"` directive only when interactivity (state, hooks, event listeners) is required.

### 2. Styling
- **Tailwind First:** Use Tailwind CSS utility classes for all styling.
- **CSS Variables:** Use the CSS variables defined in `app/globals.css` (e.g., `bg-primary`, `text-muted-foreground`) to ensure theme compatibility.
- **Responsiveness:** Build mobile-first. Use `md:`, `lg:` prefixes for larger screens.
- **Animations:** Use `animate-in`, `fade-in`, `slide-in` classes from `tailwindcss-animate` for entry animations.

### 3. Icons
- **Library:** Use `lucide-react` exclusively.
- **Import:** Import specific icons: `import { Check, Copy } from "lucide-react"`.

### 4. File Structure
- **App Router:** Pages go in `app/`.
- **Hooks:** Custom hooks go in `hooks/` and must be named `use-*.ts` or `use-*.tsx`.
- **Utils:** Helper functions go in `lib/utils.ts`.

### 5. Best Practices
- **Type Safety:** No `any`. Define interfaces/types for all component props.
- **Accessibility:** Ensure buttons have accessible labels (use `<span className="sr-only">` for icon-only buttons).
- **Clean Code:** Keep components small (< 200 lines). Extract logic into hooks or smaller components if files grow too large.