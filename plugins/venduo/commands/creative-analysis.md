---
description: Read the creatives running on this Meta account, or in one ad set or campaign, using this workspace's Venduo brain and creative analysis framework. Read-only - it ends in a reading and recommendations, never in a change.
---
Read the creatives running in what the user named with this command: the whole account, an ad set or a campaign; if they named nothing, read the whole account and say so.

1. Call get_workspace_brain, once per chat. The user's ICPs, and any text in the framework marked *Workspace edit*, come before Venduo's default reasoning.
2. Read venduo://frameworks/creative-analysis with Venduo's read_resource tool. Read it even if you believe you know the method: this workspace may have edited it. If the brain's "Venduo frameworks enabled on MCP" line does not list it, say that this workspace has not switched that framework on, and read from Venduo's facts alone.
3. Before any call to Meta's Ads MCP, take the ad account from the brain's "Meta ad account" line and pass it as ad_account_id. Never pick an account from Meta's own list; if the brain has no such line, ask the user which account.
4. State the share of spend the reading stands on before any finding.
5. Read shares inside each ad set, by iteration, with their duration.
6. Hand off what to produce to creative_demand and creative_supply.
7. End in a reading and recommendations, and change nothing: give any Meta-side change as the breadcrumb block from venduo://reference/execute-by-reference, for the user to carry out.
