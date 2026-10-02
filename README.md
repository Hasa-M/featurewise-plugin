# Featurewise

Featurewise is being built to review existing feature descriptions, tickets and specifications in the AI host you already use. It aims to identify missing, ambiguous or contradictory decisions, consult relevant context, and propose clarifications and corrections backed by verifiable evidence.

It is intended for developers and tech leads, as well as PMs, POs and designers preparing an implementation handoff.

## Current status

As of October 2, 2026, this repository contains project documentation and an [MIT license](LICENSE). There is no implemented skill or installable plugin here yet, and no executed review evaluation or host compatibility evidence. No review, MCP, Console, indexing or memory capability is currently verified.

The current implementation scope is the first skill experiment: an initial review method, minimal structured results, packaging for a real Codex trial, and evaluation against a good ordinary request to the same agent. Installation instructions will follow a verified installation; planned features below are not available capabilities.

## Product direction

1. **Skill and first plugin:** a useful, repeatable review with verifiable references, a real Codex trial and a few comparable evaluation cases. The basic review must work without a Console or Featurewise account.
2. **MCP and integrated Console:** immediately after the first working, verified skill. Inspect and selectively reuse the separate Console repository, verify UI support in the chosen Codex version, and implement the minimal service and a complete feature review/decision flow.
3. **Indexing, retrieval and decision memory:** updateable sources, measured context retrieval, applicable decisions and feedback, and handling of superseded decisions. These remain central product capabilities.
4. **Consolidation, compatibility and collaboration:** reliability, verified use in other hosts, and collaboration and synchronization as needed.

The final product combines a skill, MCP tools and a Console that opens inside the host. AI analysis runs in the host. Operations on Console data go through MCP; the service validates and authorizes them and persists authoritative records, while the UI displays those same records. Purely visual navigation and filters stay in the UI. Feedback on a finding and confirmation of a decision are separate actions.

Codex is the first target, but compatibility of its specific UI surface remains to be tested. Support for a protocol or packaging format alone does not prove the integrated experience works. Basic review is intended to remain available without the integrated service; this does not imply offline execution.

## Development

See [product context](docs/product-context.md) for the approved decisions, open choices and evidence required for each block, and [AGENTS.md](AGENTS.md) for development rules. The review methodology will be canonical across host adaptations. New plugin software components will use Python; that choice does not require rewriting the Console in Python.
