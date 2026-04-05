# AGENTS.md

This file provides guidance to AI agents when working with code in this repository.

## Project Overview

This is an **Obsidian vault** containing a knowledge base for the **Indian Specialist Recruitment Platform** — a B2B platform for managing end-to-end hiring and relocation of Indian specialists to Russia. The platform coordinates between Russian clients, Russian/Indian recruitment partners, and platform administrators.

All documentation is written in **Russian**. The wiki is maintained by LLM — human rarely edits it directly.

## Repository Structure

- `index.md` — master index with links to all wiki articles (start here)
- `concepts/` — 11 articles on key entities and domain concepts (roles, cabinets, deals, candidates, etc.)
- `processes/` — 11 articles on business processes and workflows (pipeline, status models, registration, etc.)
- `architecture/` — 4 articles on technical architecture (microservices, integrations, screen map)
- `analysis/` — 5 articles on gap analyses, feature requests, MVP scope
- `raw/` — source documents from Docusaurus site (reference only, do not edit)
- `raw/user-flows/` — 18 detailed flow diagrams with Mermaid syntax

## Key Domain Concepts

- **Кабинеты**: 5 role-based dashboards — Admin, Client, Partner Russia, Partner India, Candidate (target)
- **Pipeline сделки**: Пресейл → Квоты → Подбор → Согласование → Оформление → Релокация → Готов к работе
- **Candidate lifecycle**: 13 statuses from Подобран through to Работает
- **РНР**: Work permit process — 16-step regulatory workflow (185-210 days AS IS)
- **MVP scope**: 4 roles, 29 scenarios, 26 screens. Items marked ★ are MVP priority.

## Clickable Prototype

A clickable UI prototype lives at `/Users/daniilrozhkov/claude-prj/indian-migrants-platform-ui/` — a **Nuxt 4 + Nuxt UI** app (Vue 3, TypeScript). Claude Code may freely read and edit files in that directory.

## Working with This Vault

- Use Obsidian-flavored markdown: `[[wikilinks]]`, callouts, YAML frontmatter with `summary` field
- Every article has a `summary` in frontmatter — used for quick LLM navigation without reading full content
- Cross-reference articles with `[[Article Name]]` wikilinks
- Mermaid diagrams are valid Obsidian syntax — preserve them
- When adding new articles: create in the appropriate directory, add wikilinks, update `index.md`
- `raw/` is read-only reference — all edits go into wiki articles

## Working with the Prototype (Nuxt 4 + Nuxt UI)

Before making any UI changes:
1. **Identify the component type** you plan to use (e.g., `USelect`, `UInput`, `UTextarea`, pill buttons, etc.)
2. **Look up its usage rules** in the Context7 MCP documentation for Nuxt UI — check available props, slots, events, and variants
3. **Only then** implement the change — do not guess component APIs

This prevents incorrect component usage and ensures consistency with the Nuxt UI library.
