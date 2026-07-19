# Setup Guide

There are three ways to use this. Pick the one that matches you. **Most local business
owners should use Option A (Claude Project) — it's the no-code path.**

---

## Option A — Claude Project (easiest, no code)

A Claude Project is a saved workspace with its own instructions and knowledge files. This
lets Claude "remember" your business across chats.

**1. Create the Project.**
In Claude, go to **Projects → New Project**. Name it something like "Service Pages —
[Your Business]."

**2. Add the skill's brain as knowledge.**
Upload (or copy-paste) these three files into the Project's **knowledge** area:
- `SKILL.md`
- `references/service-page-spec.md`
- `references/quality-checklist.md`

(You can add `references/onboarding-interview.md` and `templates/intake.md` too — they
help but aren't strictly required.)

**3. Add the Project instructions.**
Paste this into the Project's **custom instructions** box:

> You are a local service page writer. Follow the process and rules in the knowledge files
> (SKILL.md and the service-page-spec). When I first set up my business, run the short
> onboarding interview and produce a Business Profile for me to save. After that, when I
> ask for a page for one of my services, write the complete page in Markdown, asking only
> for the service-specific facts you still need. Never invent credentials, reviews, prices,
> guarantees, response times, or locations — mark missing facts with [INPUT REQUIRED]
> instead. Don't publish anything or write JSON-LD unless I ask.

**4. Onboard once.**
Start a chat in the Project and say: *"Let's onboard my business."* Answer the questions.
When Claude gives you the **Business Profile**, copy it and add it to the Project knowledge
as a file called `business-profile.md`. Now every future chat knows your business.

**5. Make pages.**
In any Project chat: *"Write my water heater repair page."* That's it. Repeat for each
service.

---

## Option B — Skill (Claude Code or a Claude plan that supports skills)

If your Claude setup supports skills directly, install the whole folder as a skill and it
triggers automatically when you ask for a service page.

- **Claude Code / plugin:** see Option C.
- **Direct skill upload (where supported):** upload the `.skill` package if one is
  provided in the release, or point your skill directory at this folder. Then just ask:
  *"Write a service page for [service]."* The skill's description handles triggering.

---

## Option C — Plugin (Claude Code power users)

This repo includes a plugin manifest so it can be installed through a Claude Code
marketplace.

1. Host this repo (or a marketplace repo that references it) on GitHub.
2. Add it as a marketplace, then install the plugin from that marketplace:
   ```
   /plugin marketplace add TheSearchSherpa/local-service-page-writer
   /plugin install local-service-page-writer@search-sherpa-skills
   ```
3. Ask for a page. The skill loads on demand.

Exact plugin commands can change across Claude Code versions — check the current Claude
Code docs if a command differs.

---

## How the pieces fit

```
Onboard once  ──►  Business Profile  ──►  reused for every page
                                            │
                                            ▼
                        "Write my [service] page"  ──►  complete Markdown page
```

You answer the big questions one time. After that, each new page only needs a few
service-specific details.
