# Venduo: the Meta Ads plugin for Claude

Venduo's plugin for Claude reads your Meta Ads account (Facebook and Instagram
ads) from your workspace's own brain and frameworks: how Claude starts a
Venduo session, plus shortcuts for media-buying reviews, creative analysis,
creative pipeline planning and adapting reference ads.

| Shortcut | What it does |
|---|---|
| `/media-buying-review` | Analyse one Meta campaign, ad set or ad, or review the whole account, using this workspace's Venduo brain and media-buying framework. Read-only - it ends in a reading and recommendations, never in a change. |
| `/creative-analysis` | Read the creatives running on this Meta account, or in one ad set or campaign, using this workspace's Venduo brain and creative analysis framework. Read-only - it ends in a reading and recommendations, never in a change. |
| `/pipeline-plan` | Read creative demand against supply for this Meta account, or one slice of it, over a horizon, using this workspace's Venduo brain and creative-pipeline framework. Read-only - it ends in a reading and recommendations, never in a change. |
| `/adapt-reference-ad` | Deconstruct a reference ad in Venduo's creative vocabulary and adapt it for one of this workspace's ICPs, in its brand voice. Read-only - it ends in a brief and a script for the user's own production, and changes nothing on Meta. |

Every shortcut is read-only: it changes nothing in your ad account.

You need a Venduo workspace: <https://venduo.io>.

## Install

**Claude (web, desktop app, Cowork)**

1. Open **Customize → Plugins → Add → Add marketplace** and enter
   `venduo-io/meta-ads-claude-plugin`.
2. Install **Venduo**.
3. Open the plugin's **Connectors** tab and connect Venduo. Installing the
   plugin does not sign you in; the connector is its own step.

**Claude Code**

```
/plugin marketplace add venduo-io/meta-ads-claude-plugin
/plugin install venduo@venduo
```

Then connect the Venduo server under `/mcp`.

If you already use the standalone Venduo skill, remove it when you install the
plugin: the plugin holds the same skill.

## Updates

New versions are published here. To receive them without doing anything, turn
on automatic updates for this marketplace where you added it: in Claude's
plugin settings, or under `/plugin` → Marketplaces in Claude Code.

## About this repository

Every file here is generated from Venduo's own source and published
automatically, so a change made here is overwritten by the next release.
Questions and feedback: <https://venduo.io>.

Venduo is an independent product. It is not affiliated with or endorsed by
Meta or Anthropic.
