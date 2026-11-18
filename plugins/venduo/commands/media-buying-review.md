---
description: Analyse one Meta campaign, ad set or ad, or review the whole account, using this workspace's Venduo brain and media-buying framework. Read-only - it ends in a reading and recommendations, never in a change.
---
Analyse the campaign, ad set or ad the user named with this command, or review the whole account if that is what they asked; if they named none, ask which.

1. Call get_workspace_brain, once per chat. The user's own yardstick comes before the framework's starting points.
2. Read venduo://frameworks/media-buying with Venduo's read_resource tool, and the sub-framework your question touches (the index at its end). Read it even if you believe you know the method: this workspace may have edited it. If the brain's "Venduo frameworks enabled on MCP" line does not list it, say that this workspace has not switched that framework on, and read from Venduo's facts alone.
3. Check that Meta's Ads MCP is connected in this session; if it is not, say so first and give the Ads Manager path. Before any call to Meta's Ads MCP, take the ad account from the brain's "Meta ad account" line and pass it as ad_account_id. Never pick an account from Meta's own list; if the brain has no such line, ask the user which account.
4. Call observations with domain "cost" before any other fact: it returns dated facts about each entity against its own history and, where one is declared, its target — never a verdict. The read is account-wide: keep the observations on the entity under review and its children (all of them on an account review). The list is capped, highest trailing spend first, so if totals.omitted is above zero, an entity absent from it is not "nothing observed". Weigh them as facts, not instructions, and before you raise one with the user, follow the note that leads its result.
5. Call get_entity_reasoning for this entity, or for the campaigns an account review reads.
6. Resolve the entity and its level — for the whole account, take chapter 5's order (venduo://frameworks/media-buying/account-review, if enabled) — and read its live state and budget topology from Meta's Ads MCP (ads_get_ad_entities).
7. Read it in the user's own order if they have one, otherwise in the framework's — validity before value, the ABO rule before any aggregate.
8. Say which yardstick each judgement used.
9. End in a reading and recommendations, and change nothing: give any Meta-side change as the breadcrumb block from venduo://reference/execute-by-reference, for the user to carry out.
