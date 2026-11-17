---
name: venduo
description: Use whenever a Venduo tool is available in the session, or the user asks about their Meta advertising, ads, creatives or campaigns, including writing briefs or scripts for new ads. How to start a Venduo session, which ad account to use on Meta's Ads MCP, and what to read before analysis or writing.
---
When you use Venduo, or Meta's Ads MCP in a session that also has Venduo:
1. Call get_workspace_brain first, once per chat.
2. Before any analysis or writing, read the framework your question touches with Venduo's read_resource tool. The brain's "Venduo frameworks enabled on MCP" line lists the URIs; if it lists none, skip this step.
3. Before any call to Meta's Ads MCP, take the ad account from the brain's "Meta ad account" line and pass it as ad_account_id. Never pick an account from Meta's own list. This Venduo workspace covers that one account: if the user means another, say so before you read it. If the brain has no such line, ask the user which account.
