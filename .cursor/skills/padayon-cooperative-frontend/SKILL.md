---
name: padayon-cooperative-frontend
description: >-
  Senior full-stack patterns for Padayon Multipurpose Cooperative web and
  landing work using Vue 3, TypeScript, Tailwind CSS, and shadcn/ui
  (shadcn-vue) with mobile-first responsive design and ESLint. Use when building
  or changing the Padayon site, landing page, coop branding UI, or when the user
  mentions Padayon, Southwest Cebu cooperative, or this repository’s frontend.
---

# Padayon Cooperative — Frontend Skill

## When to apply

Use this skill for all UI/UX and frontend implementation for **Padayon Multipurpose Cooperative** (public site, landing page, marketing sections, member-facing surfaces). Standard stack: **Vue 3 + TypeScript + Tailwind + shadcn/ui (shadcn-vue)**—align with repo conventions if the project already pins specific versions or folder layout.

## Stack (senior defaults)

- **Vue 3**: Composition API and `<script setup lang="ts">`. Use `defineProps` / `defineEmits` with explicit types; extract reusable logic into **composables** (`use*`).
- **TypeScript**: Strict, explicit types for props, emits, API shapes, and composable return values. Avoid `any`; use `unknown` + narrowing when needed.
- **Tailwind CSS**: Utility-first; extend theme and CSS variables in line with **shadcn-vue** (colors, radius, typography) so primitives stay consistent. Mobile-first breakpoints (`sm:`, `md:`, `lg:`).
- **shadcn/ui (shadcn-vue)**: Use the **Vue** port ([shadcn-vue](https://www.shadcn-vue.com/))—add components with the project CLI into the agreed directory (typically `components/ui`). Treat components as **owned source**: compose and adapt locally rather than reimplementing the same primitives ad hoc. Prefer shadcn primitives for interactive UI (buttons, dialogs, forms, dropdowns, etc.) and keep branding via tokens + layout in page/section components.
- **Components**: Small, focused SFCs for pages and domains; name files clearly (`TheHeader.vue`, or project convention). Keep pages thin; move logic to composables or stores only when shared state is required.
- **ESLint**: Configured under `web/` (`eslint.config.js`). After adding or updating frontend files, run **`npm run lint`** from `web/`; use **`npm run lint:fix`** to auto-fix where possible. Treat a clean lint (or user-approved exceptions) as part of “done.”

## Responsive and accessibility

- **Mobile-first**: Layout and typography for small screens first; enhance for larger breakpoints.
- **Touch**: Adequate hit targets (~44px minimum where interactive), no hover-only critical actions.
- **Semantics**: Correct heading order, landmarks (`header`, `main`, `nav`, `footer`), labels for forms, visible focus states (do not remove focus rings without an equivalent).
- **Performance**: Lazy-load heavy sections/routes where sensible; optimize images (formats, dimensions, `loading="lazy"` where appropriate); avoid large client-only bundles without reason.

## Brand and copy (source of truth)

Use this consistently across hero, about, and footer.

**Legal / positioning name**: Padayon Multipurpose Cooperative — aligns with Cooperative Development Authority (CDA) naming; scope may include lending, retail/investments, livelihood programs.

**Meaning**: “Padayon” = keep going, move forward, persevere (movement-oriented brand, not generic corporate).

**Recommended tagline**: **Padayon sa Kauswagan** (Continue toward progress) — strong mix of local and aspirational. Alternates: “Moving Forward Together”; “Padayon. Walay Hunong.” (No stopping.)

**Mission**  
To empower members through accessible financial services, sustainable livelihood opportunities, and a strong culture of cooperation—guiding every member to move forward with dignity and resilience.

**Vision**  
A progressive and self-sustaining cooperative in Southwest Cebu where every member thrives, grows, and succeeds together.

**Core values** (use as pillars or icon rows):

| Value | Gloss |
|-------|--------|
| Padayon | Perseverance — keep moving forward despite challenges |
| Bayanihan | Unity — grow through cooperation |
| Integridad | Integrity — honesty and accountability |
| Paglambo | Growth — continuous improvement |
| Pag-alagad | Service — members first |

Tone: hopeful, dignified, community-rooted; bilingual (Cebuano/English) labels acceptable where it serves the audience—keep primary CTAs and legal clarity clear.

## Landing / site structure (suggested)

Implement in a order that matches design, but typically:

1. **Hero** — name, tagline, primary CTA (e.g. become a member / contact), optional secondary CTA.
2. **Services / programs** — lending, retail/investments, livelihood (cards or sections).
3. **About** — mission, vision, Southwest Cebu context.
4. **Values** — five core values.
5. **Trust / CDA** — short note on compliance and member protection (wording vetted by stakeholders).
6. **Contact / location** — address, hours if any, form or contact channels.
7. **Footer** — legal name, quick links, social if applicable.

## Implementation checklist

- [ ] **`npm run lint`** passes in `web/` after the change (or documented waiver).
- [ ] Layout works at 320px width without horizontal scroll (except intentional full-bleed media).
- [ ] Typography scales across breakpoints; readable line length on large screens.
- [ ] Interactive states: hover, focus, active, disabled for buttons and links.
- [ ] Forms: validation feedback, accessible errors, no placeholder-only labels.
- [ ] SEO basics: meaningful `title`/`meta` description per route; semantic headings.

## Additional reference

For extended examples or future assets, see [reference.md](reference.md).
