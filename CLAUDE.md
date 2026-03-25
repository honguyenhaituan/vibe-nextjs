# CLAUDE.md

This file is automatically loaded by Claude Code at the start of every session.

## What This Project Is

A Next.js starter template for non-technical users who build with AI. The primary workflow:
the user describes what they want in plain English, and Claude builds it. Claude should
never ask the user to run commands — run them yourself.

## Stack

- **Next.js 16** (App Router) — file-based routing under `src/app/`
- **React 19** with TypeScript
- **Tailwind CSS v4** — utility-first, no `tailwind.config.*` file; imported via `@import "tailwindcss"` in `globals.css`
- **pnpm** — always use `pnpm`, never `npm` or `yarn`
- **PWA** via `@ducanh2912/next-pwa`

## File Map

| File                  | Purpose                                  |
| --------------------- | ---------------------------------------- |
| `src/app/page.tsx`    | Main entry page — start all UI work here |
| `src/app/layout.tsx`  | Global layout, fonts, metadata           |
| `src/app/globals.css` | Global styles and Tailwind import        |
| `src/app/manifest.ts` | PWA manifest                             |

## Dev Workflow

```bash
pnpm dev          # Start dev server at http://localhost:3000
pnpm build        # Production build (run before deploying)
pnpm lint:fix     # Auto-fix lint issues
pnpm format       # Format all files with Prettier
pnpm type-check   # TypeScript type checking
```

Always run `pnpm lint:fix && pnpm format` before committing.

## Commit Conventions

Use [Conventional Commits](https://www.conventionalcommits.org):
`feat:` · `fix:` · `docs:` · `style:` · `refactor:` · `chore:`

Husky + commitlint enforce this on every commit.

## Available Skills

Check `.agents/skills/` for capabilities Claude can invoke:

| Skill                         | Use for                              |
| ----------------------------- | ------------------------------------ |
| `shadcn`                      | Adding shadcn/ui components          |
| `frontend-design`             | UI/UX design guidance                |
| `deploy-to-vercel`            | Deploying to Vercel                  |
| `next-best-practices`         | Next.js patterns and conventions     |
| `ui-ux-pro-max`               | Advanced design system references    |
| `vercel-composition-patterns` | React component composition patterns |
| `vercel-react-best-practices` | React performance and best practices |
| `web-design-guidelines`       | Web design guidelines and standards  |

## Deployment

When the user asks to deploy or publish the app:

1. Run `pnpm build` — fix any errors before proceeding
2. Use the `deploy-to-vercel` skill

## Working With Non-Technical Users

- Translate plain English descriptions into code — never ask the user to explain technical details
- Ask clarifying questions only when truly ambiguous; default to sensible choices
- After every change, tell the user what you built and how to see it (URL, what to look for)
- Never ask the user to run a command — run it yourself
- When adding a new page that links from navigation, create the nav component if it doesn't exist yet
- If a feature requires a new dependency (e.g., a database, auth), confirm with the user before introducing it
