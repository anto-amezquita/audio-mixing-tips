# 0001 — Next.js on Vercel, consuming @amezquita/design-system

## Status

Accepted

## Context

The site is one page holding 100 static entries, with client-side search, filtering and local-storage favourites. There is no backend, no auth and no data that changes after build.

That workload would run on almost anything. The deciding factor was not capability but reuse: `@amezquita/design-system` already exists, is published to npm, and was made fully portable in v0.1.3. amezquita.dk consumes it. Every hour spent picking colours and spacing here is an hour not spent on content.

A second consideration is that this repo doubles as a portfolio piece. A second independent project consuming the same package is evidence the package works, in a way a single consumer is not.

## Decision

Next.js with the App Router and TypeScript in strict mode, statically generated, deployed on Vercel from `main`. `@amezquita/design-system` supplies tokens and components; local components exist only where the package has no equivalent.

No backend, no database, no environment variables. Introducing any of those requires a new ADR.

## Alternatives considered

- **Astro** — better suited to a content site of this shape, and would ship less JavaScript. Rejected because the design system is React, and the cost of proving it works in a second React app outweighs the bundle saving on a page this small.
- **A single hand-written HTML file** — genuinely sufficient for v1, and the fastest possible route to something usable. Rejected because it forfeits the design-system reuse, the build-time content validation, and the portfolio value, and because the content model is meant to outlive this version.
- **Vite plus React Router** — no static generation, so content would render client-side. Loses the "all 100 entries in the HTML" property that section 3 of `docs/architecture.md` depends on.
- **Netlify or Cloudflare Pages instead of Vercel** — equivalent for this use. Vercel chosen because it's the path of least resistance for Next.js and matches the existing setup.

## Consequences

### Positive

- The visual layer is inherited, not designed. Work goes into content and retrieval.
- Static output means no runtime failure modes: content errors break the build instead of the page.
- A second real consumer of the design system, which surfaces portability bugs in the package.
- Deploys are a push to `main`.

### Negative

- More JavaScript than this page needs. Acceptable at 100 entries; worth revisiting if the library grows several times over.
- The build is coupled to the design system. If the package breaks, this site can't build — see Phase 1 of the spec, which stops there if the package doesn't resolve.
- Next.js is a large dependency to maintain for a site with one route.

## Related files

- `docs/architecture.md` — sections 1, 4 and 8
- `specs/2026-09-29-mixing-tips-reference.md` — sections 7 and 11
- `docs/product-north-star.md` — section 8, business goals
