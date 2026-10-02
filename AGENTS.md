# Developing Featurewise

Read [docs/product-context.md](docs/product-context.md) before changing product behavior or architecture. It records the purpose, approved sequence, boundaries and open choices. Keep the [README](README.md) aligned with capabilities supported by actual evidence.

- The current implementation scope is the first skill experiment: review method, minimal structured results, necessary packaging and a Codex trial with evaluation. Keep MCP, Console and service implementation in the dedicated second block, after the first verified skill and before full indexing and memory.
- Inspect existing files, applicable instructions and available evidence before working. Preserve useful work and unrelated local changes; distinguish preparation, executed checks and verified outcomes.
- Use one canonical review methodology in Markdown and Python for new plugin software components. Add host adaptations only when necessary and verified. The product review procedure belongs in its `SKILL.md`; this file governs development.
- Work in bounded tasks with observable success criteria. Use proportionate checks; compare the skill with a good ordinary request under comparable conditions. Preserve review evidence without Console/account dependencies, and keep future integration evidence separate.
- Follow the component and data boundaries in the product context. Separate deterministic validation from model judgment, finding feedback from confirmed decisions, and authorized sources from instructions. Do not invent accesses, sources, implementation status or compatibility claims.
- Local development tasks authorize their necessary edits and checks. Respect the task's scope and existing authorization; do not make automatic commits, pushes, Git hooks or `.gitignore` changes. Deployment, publication, spending, permission changes and destructive operations require authorization covering them.
- Keep code and public documentation primarily in English. Keep personal handoff details out of public files, link to the product context instead of duplicating it, and preserve license/attribution requirements when reusing material.
