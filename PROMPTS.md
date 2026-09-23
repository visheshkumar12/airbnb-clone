# AI-Assisted Development Log

This project was built collaboratively with Claude (Anthropic), as encouraged
by the assignment brief. Below is the real sequence of prompts/instructions
that drove this build, condensed for readability.

.
1. **Clarified assignment context** — confirmed this was a take-home
   assessment; agreed to help build a strong original implementation and
   explained that the reference blocks automated scraping (robots.txt), so
   the clone is built from the provided screenshot + standard Airbnb UI
   conventions, which should be diffed against the live reference manually
   afterward for exact fidelity (spacing, fonts, colors).
2. **Scaffolded the project** — Next.js 14 (App Router) + TypeScript +
   Tailwind CSS, with a Node.js backend expressed as a Next.js API route
   (`/api/listing`).
3. **Built the data layer** — typed `ListingData` model with photos, host,
   amenities, reviews, pricing (`data/listing.ts`), served via the API route.
4. **Built the Listing Page components** — `Header`, `ListingHeader`
   (title/share/save), `PhotoGrid` (5-image hero grid), `OverviewSection`,
   `Amenities` (with "show all" modal), `BookingCard` (sticky, price
   breakdown), `ReviewsSection` (category bars + review cards), `HostSection`,
   `Footer`.
5. **Built the Photo Tour overlay** — full-screen scrollable gallery with a
   thumbnail strip, opened from "Show all photos" or any hero image.
6. **Built the Lightbox overlay** — single-photo viewer with prev/next
   controls, Left/Right arrow-key navigation, Escape to close, and a scale/
   fade transition.
7. **Added accessibility passes** — focus-visible styles, `aria-label`s on
   icon buttons, `role="dialog"` + `aria-modal` + focus management on both
   modals, `prefers-reduced-motion` handling in `globals.css`.
8. **Verified the build** — ran `npm install`, `npm run build`, and a
    production smoke test (`npm run start`) to confirm the page and the
    `/api/listing` route both render/respond correctly; upgraded Next.js to
    the patched `14.2.35` release after the installer flagged a known
    vulnerability in `14.2.5`.
9. **Generated the architecture diagram** — produced
    `architecture-diagram.png` covering frontend, backend, storage, search,
    and deployment scaling for a production-scale marketplace.
10. **Wrote sub-agent/skill configs** — `agent-config/ui-fidelity-reviewer.md`,
    `agent-config/a11y-auditor.md`, and
    `agent-config/airbnb-design-tokens.skill.md` to document the review
    process and reusable design tokens, per the brief's request to include
    these in the submission.
11. **Packaged the deliverable** — zipped the source, diagram, and configs
    for a clean `npm install && npm run dev` in VS Code.

## Known gap to close manually
Because the live reference couldn't be scraped, exact pixel values (font
metrics, precise spacing, exact photo grid proportions, animation timing)
were approximated from Airbnb's known design language and the provided
screenshot rather than measured directly from the reference's computed
styles. Before submitting, open the reference in Chrome DevTools side-by-side
with this app and diff: font sizes, colors, spacing (padding/margin/gap),
border radii, and hover/transition timing — then adjust the Tailwind classes
in the relevant component to close any gaps. This diffing pass is part of
what the assignment is evaluating.
