# Featurewise product context

## Purpose and users

Featurewise is intended to review existing feature descriptions, tickets and specifications in the AI host the user already uses. Its purpose is to identify missing, ambiguous or contradictory decisions that could misdirect implementation, retrieve relevant context and applicable decisions, and propose clarifications or corrections with verifiable evidence and explicit limits.

Users include developers and tech leads, plus PMs, POs and designers preparing or refining a handoff. The initial audience already uses a supported host; access to repositories, tools and connected sources must not be assumed. The first review requires no prescribed document format or Featurewise project structure. Featurewise is not a project manager or a readiness certification system.

## Current state and decision authority

As of October 2, 2026, this repository contains documentation and an MIT license. No skill implementation, installation evidence or executed review evaluations are present. The current implementation scope is the first skill experiment; MCP, Console and service implementation are outside that scope.

The October 2, 2026 product decision takes precedence over the handoff only where it explicitly updates it. All other handoff guidance remains valid. These references establish product direction, not completed capabilities.

## Firm decisions and component boundaries

- The final product integrates a review skill, MCP tools and a Featurewise Console that can open inside the host. AI analysis runs in the host, using its model, tools and authorized access. Codex is the first target; support for skills, MCP and UI must be verified separately in the actual client version.
- The basic review must remain usable without a Console or Featurewise account or backend. Product-managed persistence and memory are optional for the user, while indexing, retrieval and decision memory remain central capabilities to build.
- The skill owns the review method. Reports distinguish supported problems, decisions needing clarification and review limits, with scope, sources, concrete consequences and possible actions. Missing evidence is not proof of absence; zero findings is valid and does not certify readiness.
- All operations on Console data, including reads and actions initiated from the UI, go through MCP. MCP is the plugin's operational contract; it does not prohibit internal service APIs. The agent must not bypass it through browser automation, direct database access or alternative Console API calls.
- The service applies authorization, validation, domain rules and persistence. The Console displays the same authoritative records available to the agent, linking reviews, findings, evidence, feedback and decisions. Navigation and purely visual filters remain UI state. The UI must not maintain a competing authoritative archive; any future local/service synchronization needs an explicit contract.
- Feedback on a finding and confirmation of a decision are separate actions. Accepting a finding does not approve its proposed solution; a model-extracted proposal does not become a confirmed decision automatically.
- The plugin and Console remain separate repositories. Reuse of the Console frontend is approved for block 2, after inspecting its repository. Existing authentication, backend, database, storage, integrations and pages must not be assumed active or reusable. The service does not restore backend AI inference or orchestration.
- Maintain one canonical review methodology with only the packaging adaptations required by each host. The method is expressed in Markdown; Python is chosen for new plugin software components. Console and service stack choices depend on actual reuse, without requiring a Python rewrite. The plugin is open source under MIT, respecting reused material's licenses and attribution.
- Keep private project/service records separate from any voluntarily contributed shared corpus. No mandatory telemetry or automatic sharing of source material. Account-free review does not imply offline execution or that no data leaves the computer: the host and connected services have their own data flows.

## Development sequence and evidence

| Block | Work and success criteria |
| --- | --- |
| 1. Skill and first plugin | Establish the initial method, minimal structured results with verifiable references, and the packaging needed for a real Codex trial. Compare a useful, repeatable review with a good ordinary request to the same agent using a few evaluation cases. Record observed errors and limits. Preserve evidence that review works without a Console or Featurewise account. |
| 2. MCP and integrated Console | Start immediately after the first working, verified skill, before completing indexing or memory. Inspect the Console repository and selectively reuse it. First verify UI opening in the chosen Codex version, context exchange and an MCP tool call; then build the minimal service and one feature's complete flow. Operations use MCP, UI and agent see the same records, and a saved review and confirmed decision can be retrieved. Feedback and decision confirmation remain distinct. |
| 3. Indexing, retrieval and decision memory | Build updateable sources and measured retrieval, contextual use of feedback and decisions, scope and validity checks, and handling of superseded decisions. Verify that a subsequent review retrieves and applies current, relevant context with supporting references. Indexes are rebuildable derived data; source authority, freshness and access constraints remain explicit. |
| 4. Consolidation, compatibility and collaboration | Improve evaluations and reliability, verify external use and other hosts, and add collaboration and synchronization when actual workflows require them. Shared insights depend on voluntary contributions and adequate evidence. |

The first integrated flow is: identify a feature and its context → run the review in the host → save the result through MCP when requested → inspect findings and evidence in the Console → record feedback and confirmed decisions through MCP. Saving and retrieving individual records in block 2 does not establish contextual or adaptive memory; that work belongs to block 3.

Block 1 evaluations include a supported contradiction, incomplete context, an answer already in the sources, no supported problems, and supplied current/superseded decision variants. Keep input, information access, host/model and budget comparable, and keep expected answers and grading outside the reviewing agent's access. Such fixtures do not establish implemented decision memory. UI opening, MCP access controls and shared-record consistency are block 2 evidence, not prerequisites for the Console-free review trial. Preparation must be distinguished from execution.

## Open choices

The exact report schema, Python runtime distribution, initial MCP tools, physical data schema, storage format, optional local directory, source segmentation, ranking and embedding approach remain open. So do service authentication, database, UI distribution and which Console components can actually be reused. Select them through bounded experiments and observed needs; do not prebuild a universal framework.

Codex UI compatibility is unverified. Protocol or packaging support alone does not establish UI availability or connect authentication, persistence and the agent. Record the chosen host version and actual checks before claiming integration. Changes to the approved block order require explicit discussion; the direction does not authorize deployments, spending or infrastructure changes.
