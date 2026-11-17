---
description: Read creative demand against supply for this Meta account, or one slice of it, over a horizon, using this workspace's Venduo brain and creative-pipeline framework. Read-only - it ends in a reading and recommendations, never in a change.
---
Plan creative production for the slice the user named with this command; if they named none, for this ad account.
Use the forward horizon they named with it; if they named none, use 30 days unless the question implies another.

1. Call get_workspace_brain, once per chat. Take the declared context (ICPs, currency) from it.
2. Read venduo://frameworks/creative-pipeline with Venduo's read_resource tool — Venduo's framework for this question, which carries the arithmetic the tools do not. Read it even if you believe you know the method: this workspace may have edited it. If the brain's "Venduo frameworks enabled on MCP" line does not list it, say that this workspace has not switched that framework on, and read from Venduo's facts alone.
3. Before any call to Meta's Ads MCP, take the ad account from the brain's "Meta ad account" line and pass it as ad_account_id. Never pick an account from Meta's own list; if the brain has no such line, ask the user which account.
4. Resolve the question to ONE slice and ONE horizon (framework §2). If a named slice matches nothing, say so rather than widening it.
5. Call creative_demand and creative_supply over that SAME slice.
6. Compute both demand readings — throughput and carriers, each with the divisor framework §3 names for it, never the plain median — and the gap against supply (framework §8).
7. Answer in the shape framework §10 gives: slice, horizon and basis, the coverage line (always), the statistic you divided by named by its field, ONE assumption, the numbers as a range, and what would change the answer.
8. End in a reading and recommendations, and change nothing: give any Meta-side change as the breadcrumb block from venduo://reference/execute-by-reference, for the user to carry out.

Do not ask a clarifying question unless the answer materially changes on it and the account offers no default (framework §10).
