# Essai

A clone of [Essay](https://essay.app/) — a writing app built around a structured essay-writing process rather than a blank page.

Essai's premise is that good writing comes from separating the phases most writers conflate: reading, outlining, producing prose, and editing. The app gives each phase its own surface so you can stay in one mode at a time.

## Core building blocks

The app is organized around five primitives, each of which maps to a phase of the workflow:

1. **Reading list** — sources you collect before writing. Becomes the bibliography later.
2. **Outline** — a flat list of 10–15 short sentences that defines the essay's skeleton. Long essays nest sub-outlines under each line.
3. **Paragraphs** — one paragraph per outline line, written long (10+ sentences) and loose. Production mode only — no editing here.
4. **Sentence rewriter** — takes a single sentence and lets you draft multiple alternative versions side by side, then pick the strongest.
5. **Reorder view** — drag paragraphs (and sentences within them) into a better sequence; optionally rebuild the outline from the reordered prose.

Drafts are versioned (first draft → second draft → final), and word counts are tracked per section so you can aim ~25% over target during production and trim down while editing.

## The workflow

The intended loop, end to end:

1. **Pick a topic** and gather sources into the reading list.
2. **Outline** the argument as 10–15 sentences.
3. **Produce** a paragraph under each outline line — fast, no editing.
4. **Rewrite** weak sentences using the multi-version rewriter.
5. **Reorder** paragraphs and sentences for flow.
6. **Reconstruct** a fresh outline from memory of what you wrote, salvage the strong parts, and iterate from step 3.
7. **Finalize** when each editing pass stops improving the text, then export with bibliography.

Production and editing live in separate modes on purpose — the app actively discourages polishing a sentence while you're still drafting.

## Stack

- [Next.js](https://nextjs.org/) 16 (App Router, Turbopack)
- React 19
- TypeScript
- Tailwind CSS v4
- [shadcn/ui](https://ui.shadcn.com/) + Radix / Base UI primitives

## Getting started

Install dependencies and start the dev server:

```bash
pnpm install
pnpm dev
```

Then open [http://localhost:3000](http://localhost:3000).

## Scripts

- `pnpm dev` — start the dev server (Turbopack)
- `pnpm build` — production build
- `pnpm start` — run the production build
- `pnpm lint` — run ESLint
- `pnpm format` — format with Prettier
- `pnpm typecheck` — run TypeScript without emitting

## Adding UI components

```bash
npx shadcn@latest add button
```

Components land in [components/ui/](components/ui/) and can be imported as:

```tsx
import { Button } from "@/components/ui/button";
```

## Project layout

- [app/](app/) — routes and layouts
- [components/](components/) — UI components
- [hooks/](hooks/) — shared React hooks
- [lib/](lib/) — utilities
- [public/](public/) — static assets

## Inspiration

The design and product direction follows [essay.app](https://essay.app/). Essai is a study/clone, not affiliated with the original.
