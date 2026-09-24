# expected/

This directory holds **client workspaces' expected-state files** — the per-workspace
allowlist (plugin groups, skill counts, versions) an audit publishes so a session-start
freshness check can flag anything not on a client's allowlist. It is deliberately empty
here; a workspace audit populates it when it runs.

**Home workspaces' expected-state files do not live here.** They live in the operator's
own home-side registry repository, alongside the rest of that registry's company-specific
content. Keeping the split this way means nothing home-specific — account names, machine
names, home plugin groups — ever syncs into a client Claude org through this repository,
which is installed as a personal marketplace in every account, client orgs included.

See `plugins/workspaces/skills/workspace-model/SKILL.md`, section 8, for how this
boundary fits the rest of the workspace model.
