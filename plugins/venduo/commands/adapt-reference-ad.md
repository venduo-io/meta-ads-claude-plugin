---
description: Deconstruct a reference ad in Venduo's creative vocabulary and adapt it for one of this workspace's ICPs, in its brand voice. Read-only - it ends in a brief and a script for the user's own production, and changes nothing on Meta.
---
Adapt the reference ad the user named with this command for this business, for the ICP and in the format they named, if they named either.

1. Call get_workspace_brain, once per chat. It carries the ICPs, and the company and brand context.
   Everything below is written for THIS business, not for advertising in general,
   and the brain is where this business is written down.
   Where the brain carries a `## Messaging (as of …)` section, take the positioning,
   this ICP's row, the objections and the claims from it: a claim that is not in its
   `clearedClaims` is `[NEEDED]`, whatever the brand prose says.
2. Read venduo://creative/vocabulary with Venduo's read_resource tool — the words and the exact values Venduo classifies a creative into; use them verbatim from here on. Read it even if you believe you know the method: this workspace may have edited it. If the brain's "Venduo frameworks enabled on MCP" line does not list it, say that this workspace has not switched that framework on, and read from Venduo's facts alone.
3. Before any call to Meta's Ads MCP, take the ad account from the brain's "Meta ad account" line and pass it as ad_account_id. Never pick an account from Meta's own list; if the brain has no such line, ask the user which account.
4. Resolve the reference:
   - a Venduo creative id or a Meta ad id → `get_creative_extraction`, passing
     either one as `adId` (it resolves both). The answer's `metaAdIds` lists every
     Meta ad that creative runs as, so you can confirm you landed on the one the
     user meant;
   - a Venduo Pick's `pickId` → `venduo_picks` with mode `get`. A pick is another
     brand's ad that Venduo picked as a reference: its `extraction` is read like
     any other, and in step 6 every part that is that brand's own is replaced;
   - a description, a script or a link the user pasted → NO tool call. Work from
     their words, and say that the deconstruction rests on the text you were given
     rather than on anything Venduo has seen;
   - nothing named yet → ask which ad to adapt, and stop there; a reference you cannot resolve → say so and ask.
5. DECONSTRUCT it in the vocabulary: its `concept`, `hookCategory`,
   `messageFramework`, `tone`, how it was made (the facts §7 names, then
   `productionStyle` as their summary), and its sections in order. Give
   the evidence for each call in a few words — what in the ad made you pick it.
   Where the reference does not show one, write `[NEEDED]` rather than a guess.
6. ADAPT it for the ICP the user named, resolved to one of the ICPs the brain declares, and say which; if they named none, for ONE ICP from the brain — name which, and why it is the one this reference suits. Use the brain's own words for that audience.
   Keep what makes the reference work — its `messageFramework` and the shape of
   its hook — and replace everything specific to its advertiser: the claims, the
   proof, the product moment, the audience cue. First check with
   `find_creatives_by_brief` whether this account already runs something close;
   if it does, adapt away from it rather than producing a near-duplicate.
7. WRITE the output in two parts:
   a. THE BRIEF, in the `creativeBrief` fields the vocabulary lists (§8), with
      `framework` and `tone` taking values from the vocabulary's own lists;
   b. THE SCRIPT in the format the user named, or if they named none, in the reference's own format, section by section in the structure §7 gives for that format.
      Give each section what is said (`script`), what is written on screen
      (`onScreenText`) and what is shown (`visual`).
8. Honour the brain's brand voice, its do/don't rules and its claims limits. Where
   the adaptation has to break one to work, say which and why rather than breaking
   it quietly.
9. EVERY claim in the script must be one this business can stand behind. A number,
   a customer name, a logo or an award the brain does not carry is
   `[NEEDED]` — a gap for the team to fill, never something you supply.
10. Venduo produces nothing. The brief and the script are for the customer's own
   production: Venduo does not write, shoot, generate or upload creative, and
   changes nothing on Meta. Where the answer also recommends a Meta-side change —
   launching what gets made, pausing what it replaces — render the breadcrumb
   block from `venduo://reference/execute-by-reference` and let the user's own
   agent carry it out, after the user confirms.
11. End in a brief and a script for the user's own production, and change nothing: give any Meta-side change as the breadcrumb block from venduo://reference/execute-by-reference, for the user to carry out.

    change:        one line — the entity, and the change, from → to
    entities:      [{ kind: campaign | adset | ad | creative | asset, id }]
    metaMcp:       { tool: <the ads_* tool>, args: { …the ids, PAUSED where settable } }
    preconditions: what must be true first, and the Meta read that checks it
    fallback:      the Ads Manager path, in words
    venduo:        "Venduo does not execute. Confirm with the user before any write."
