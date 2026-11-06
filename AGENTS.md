# AGENTS.md

Guide for AI agents and contributors working on this remix of the Hacker Noon email template.

## Context

This is a legacy React-based email template starter from the LLazyEmail organization (circa 2022). The long-term goal is a unified, great email template generator.

**Prefer the modern pipeline:**
- Use `@llazyemail/generate-template` for catalog → render → write.
- Inject render functions (React Email, Lit, plain functions, MJML, etc.) rather than reimplementing pipelines.
- See sibling repos: `postmark-transactional-template-simple`, `_playing_with_lit`, `generate-template`, `hn_email_template`.

## Current stack

- React + Rollup + Jest + Storybook (legacy)
- Babel config present

## Tasks to move this forward

1. Migrate components to TypeScript.
2. Add a `generate-template.config.ts` that registers this template via `createGenerator`.
3. Render to HTML using React Email or `@react-email/components` and compare against original.
4. Add tests that assert rendered HTML structure / size < 102kb.
5. Adopt `LLazyEmail/email-template-workflows` for PR artifacts.
6. Align with the main `hn_email_template` patterns where possible.

## Invariants

- Do not break existing Storybook stories or Jest tests without updating them.
- Keep email client compatibility in mind (inline styles, table layout, no modern CSS).
- Prefer small, focused PRs.

## Related

- Org overview: https://github.com/LLazyEmail
- Docs: https://docs.llazyemail.com
- Shared CI: https://github.com/LLazyEmail/email-template-workflows
