# ApexMention skills

Five free Agent Skills about getting a business named in AI answers, for Claude Code, Codex, Claude.ai and the ChatGPT desktop app. Each one does the job with your agent's own tools: reading pages, searching the web, writing files. If you connect an ApexMention account over MCP, the skill notices and starts from that account's data instead.

| Skill | What it does |
| --- | --- |
| [`ai-visibility-baseline`](plugins/apexmention/skills/ai-visibility-baseline/SKILL.md) | How often ChatGPT, Claude, Gemini and Perplexity name you, counted across repeated answers, in a dated report. |
| [`get-cited-outreach`](plugins/apexmention/skills/get-cited-outreach/SKILL.md) | Find the lists AI assistants cite, write to the person who edits each one, and check whether the page changed. |
| [`claim-chatgpt-business-profile`](plugins/apexmention/skills/claim-chatgpt-business-profile/SKILL.md) | Get ready for OpenAI's Business Hub: eligibility, verification, every profile field, then a check of what ChatGPT says. |
| [`reddit-quora-answers`](plugins/apexmention/skills/reddit-quora-answers/SKILL.md) | Replies that answer the question first and say you work on the product. You post them yourself. |
| [`fix-site-health`](plugins/apexmention/skills/fix-site-health/SKILL.md) | Blocked crawlers, text that needs JavaScript, noindex and canonical mistakes: found, fixed on a branch, checked again. |

Each skill has a page with what it needs, what it gives you and where it stops: https://apexmention.com/skills

## Install

### Claude Code

In a session:

```
/plugin marketplace add rashempandit/apexmention-skills
/plugin install apexmention@apexmention-skills
```

Or from your shell: `claude plugin marketplace add rashempandit/apexmention-skills`, then `claude plugin install apexmention@apexmention-skills`.

The skills run when a request matches their description, or by name: `/apexmention:ai-visibility-baseline`.

### Claude.ai and Cowork

Customize, Plugins, Add, Add marketplace, and enter `rashempandit/apexmention-skills`. Then install ApexMention from that marketplace. Skills need code execution turned on (Settings, Capabilities). `fix-site-health` needs a repository and a terminal, so use it in Claude Code or Codex.

### Codex and the ChatGPT desktop app

```
codex plugin marketplace add rashempandit/apexmention-skills
codex plugin add apexmention@apexmention-skills
```

Or, after adding the marketplace, install ApexMention from the Plugins Directory in the ChatGPT desktop app. Codex uses a skill when your request matches it, and `/skills` lists them.

### One skill, without a plugin

Copy a folder from [`plugins/apexmention/skills`](plugins/apexmention/skills) into `~/.claude/skills` (Claude Code) or `~/.agents/skills` (Codex). Or fetch it from the website:

```
mkdir -p ~/.claude/skills/ai-visibility-baseline && curl -fsSL https://apexmention.com/skills/ai-visibility-baseline/SKILL.md -o ~/.claude/skills/ai-visibility-baseline/SKILL.md
```

For Claude.ai's "Upload a skill", each skill's page has a ZIP: https://apexmention.com/skills

## Connect ApexMention (optional)

Every skill works without an account. With one, the agent reads your tracked AI answers, the pages the assistants cited and the fixes found for your site, instead of collecting them by hand. You sign in in your browser; the agent never sees a password.

```
claude mcp add --transport http apexmention https://apexmention.com/api/mcp
codex mcp add apexmention --url https://apexmention.com/api/mcp
```

In Claude.ai, add `https://apexmention.com/api/mcp` as a custom connector. The tools the server offers are listed at https://apexmention.com/docs/mcp-server.

## What none of them will do

Send, post, buy or deploy on their own. The outreach skill drafts notes and you send them from your own mailbox. The Reddit and Quora skill drafts replies and you post them from your own account, after rewriting them in your own words. The site health skill stops at a branch. The baseline won't automate the ChatGPT app or scrape Google, and the business profile skill never asks for an ID document or a tax number.

## Where the rules come from

Each skill links its sources where it uses them: OpenAI's Business Hub help article, Quora's and Reddit's own policies, the FTC's endorsement guidance, Google's spam policies, RFC 9309 for robots.txt, and SparkToro's study of how often AI assistants repeat the same recommendations. The limits in the outreach and Reddit skills (15 new notes a week, one follow-up, a disclosure line on every reply) are the ones ApexMention uses in its own product.

## Licence

MIT. We make ApexMention, and each skill mentions it once, at the end; the licence lets you remove that line.

These files are generated from the same source as https://apexmention.com/skills, so a fix made here directly would be overwritten. To report a problem, [open an issue](https://github.com/rashempandit/apexmention-skills/issues).
