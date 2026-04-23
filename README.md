# Electron React Vite Tailwind shadcn Template

Production-ready starter for desktop apps with Electron + React + Vite + Tailwind CSS v4 + shadcn/ui.

## Screenshot

Add your screenshot file at `.github/assets/screenshot.png` and it will render here:

![Template screenshot](.github/assets/screenshot.png)

## Stack

- Electron
- React + TypeScript
- Vite (electron-vite)
- Tailwind CSS v4
- shadcn/ui (Radix + Nova)

## Features

- Preconfigured `@` alias for renderer source
- shadcn/ui ready (`components.json` included)
- tweakcn-based theme tokens in global CSS
- Light/Dark compatible token system
- Minimal welcome screen to bootstrap new projects fast

## Quick Start

```bash
pnpm install
pnpm dev
```

## Scripts

```bash
pnpm dev
pnpm lint
pnpm typecheck
pnpm build
pnpm build:win
pnpm build:mac
pnpm build:linux
```

## Add shadcn Components

```bash
pnpm dlx shadcn@latest add button
pnpm dlx shadcn@latest add card dialog input
```

If `shadcn init` fails framework detection in Electron root, skip `init` and use `add` directly.

## Template Notes

- Renderer app lives in `src/renderer` (not a plain single-root Vite layout).
- Alias `@` maps to `src/renderer/src` via `electron.vite.config.ts`, `tsconfig.json`, and `tsconfig.web.json`.
- Global theme tokens are in `src/renderer/src/assets/main.css`.
- Dark mode is class-based (`.dark` on `html`).

## Troubleshooting

### `shadcn init` cannot detect framework

- Cause: Electron structure is not a standard web-only root.
- Fix: keep `components.json` and run `pnpm dlx shadcn@latest add <component>`.

### Vite plugin type mismatch in editor

- Symptom: `No overload matches this call` in `electron.vite.config.ts`.
- Cause: stale duplicated Vite type instances in `node_modules`.
- Fix: delete `node_modules`, run `pnpm install`, restart TypeScript Server.

### Ignored build scripts warning in pnpm

- This template works without approving optional scripts.
- If needed, manage approvals with `pnpm approve-builds`.

## Recommended VS Code Extensions

- ESLint
- Prettier
- Tailwind CSS IntelliSense
