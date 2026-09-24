# claude-workspaces

Company-neutral workspace rules, packaged as a single Claude Code plugin
(`workspaces`) and distributed from this repository as a **personal** marketplace.

## Status

Live. One plugin, one skill.

## What's here

This repo holds exactly one thing: the rules for identifying which Claude workspace a
session is in, keeping filesystem roots and environment variables isolated between
workspaces, and the read/write boundaries between a home workspace and a client
workspace. See `plugins/workspaces/skills/workspace-model/SKILL.md` for the rules
themselves.

It deliberately names no company, account, machine, or person — that's what makes it
safe to install in every Claude account this operator uses, home and client alike,
without any client-facing account ever seeing another client's or the operator's own
home content. The actual workspace registry (which keys map to which accounts, roots,
and identities) lives elsewhere, in a company-specific repository that is never
installed anywhere but home accounts.

`expected/` is reserved for a workspace audit's per-client expected-state files — see
`expected/README.md` for why home-workspace expected-state doesn't live here too.

## Distribution

**Install as a personal marketplace, in every account** (home and client):

```
/plugin marketplace add dspray/claude-workspaces
```

**Never add this as an org marketplace in a client's Claude organization.** Even though
the content is company-neutral, org-marketplace admission in most Claude orgs implies a
broader trust grant than a single reference skill needs; personal-marketplace
installation is the intended and sufficient distribution path here.
