# Featurewise product context

## Purpose and users

Featurewise will review existing feature descriptions, tickets and specifications to find missing, ambiguous or contradictory decisions before implementation. It will use relevant sources and decisions to suggest clarifications and corrections with verifiable evidence.

Users are developers, tech leads, product managers, product owners and designers preparing a handoff. Reviews use the material and access available in their AI host, without requiring a specific document format or project structure.

## Architecture and firm decisions

The final product combines a review skill, MCP tools and a Console that opens inside the host. Codex is the first target. AI analysis runs in the host using its model, tools and authorized access.

- **Skill:** guide the review and report supported problems, decisions needing clarification and review limits. Findings include sources, consequences and possible actions. Zero findings is valid and does not certify readiness.
- **MCP:** handle all Console data operations, including reads and changes initiated from the UI. Browser automation, direct database access and alternative Console API calls must not bypass this contract; internal service APIs remain possible.
- **Service:** apply authorization, validation, domain rules and persistence. Each record has one authoritative source; future local/service synchronization requires an explicit contract.
- **Console:** display the same authoritative reviews, findings, evidence, feedback and decisions available to the agent. Navigation and purely visual filters remain UI state.

Feedback on a finding and confirmation of a decision are separate actions. Accepting a finding does not approve its proposed solution. Model suggestions require confirmation before becoming decisions.

Basic review must work without a Console, Featurewise account or backend. Persistence and memory are optional for users; indexing, retrieval and decision memory remain central product capabilities.

Private records stay separate from voluntary shared contributions. No mandatory telemetry or automatic sharing; host and service data flows mean account-free does not imply offline.

The plugin is open source under MIT and uses one canonical Markdown methodology with verified host adaptations. New plugin components use Python. The Console stays in a separate repository; its stack and the service stack depend on actual reuse, without requiring a Python rewrite.

## Development path

The repository currently contains documentation only. Implementation is limited to the first skill experiment; the remaining blocks describe planned work.

| Block | Result to verify |
| --- | --- |
| 1. Skill and first plugin | Install and test in Codex. Produce useful, repeatable reviews with minimal structured results and verifiable references. Compare with a good ordinary request to the same agent, without a Console or Featurewise account. |
| 2. MCP and integrated Console | Start immediately after the verified skill. Reuse the Console selectively and build the minimal service. Save a review when requested, inspect it in the UI, record feedback and a confirmed decision, and retrieve the same records through MCP. |
| 3. Indexing, retrieval and decision memory | Update sources and measure retrieval. Later reviews apply relevant, current decisions with correct scope and validity, handle superseded decisions and use feedback appropriately. Indexes remain rebuildable derived data. |
| 4. Consolidation, compatibility and collaboration | Improve reliability and evaluations, verify external use and other hosts, and add collaboration and synchronization as needed. Shared insights require voluntary contributions and supporting evidence. |

Block 2 begins by inspecting the Console repository and testing UI opening, context exchange and an MCP call in the chosen Codex version. Existing components and UI compatibility must be verified before reuse or integration claims. Retrieving individual records in this block precedes contextual memory in block 3.

Initial evaluations cover contradictions, incomplete context, answers already in sources, no supported problems, and supplied current/superseded decisions. Keep inputs, access, model and budget comparable; hide expected answers from the reviewer. Preserve Console-free review evidence separately from block 2 integration checks.

## Open choices

Report schema, Python distribution, MCP tools, storage, source segmentation, ranking, embeddings, service authentication and UI distribution remain open. Choose through bounded experiments and repository inspection.

The October 2, 2026 decision overrides only the handoff points it explicitly updates; other guidance remains valid. Changes to the approved sequence require discussion.
