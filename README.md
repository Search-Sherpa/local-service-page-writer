# Local Service Page Writer

A free, portable Claude **skill** that writes complete, honest, conversion-focused website
service pages for local service-area businesses — plumbers, roofers, HVAC, electricians,
landscapers, cleaners, contractors, med spas, auto shops, and the like.

It works on **any website or CMS** because it outputs plain Markdown. It has **no
dependencies** — no Python, no accounts, no special filesystem. And it **never makes things
up**: if a fact is missing, it tells you instead of inventing a fake license, review, or
location.

---

## What you get

- **Guided onboarding.** A short interview captures your business once (name, service area,
  real proof, voice, services). It produces a reusable **Business Profile**.
- **One page at a time.** Ask for "my water heater repair page" and it writes the whole
  thing — intro, what's covered, signs you need it, process, prep, FAQ, and a call to
  action — plus title/meta/slug suggestions.
- **Honesty by default.** No invented credentials, awards, ratings, review counts, years in
  business, guarantees, prices, response times, or physical locations. Missing facts show
  up as `[INPUT REQUIRED: …]` so you know exactly what to confirm before publishing.
- **Local, not spammy.** It localizes to the areas you *genuinely serve* and refuses to
  spin up dozens of near-duplicate "service + city" doorway pages.

## What it will NOT do

Blog posts · Google Business Profile posts · product/pricing pages · homepage or about
copy · mass "service + city" landing pages · schema-only (JSON-LD) requests · publishing to
your live site. It writes the page copy; you publish it.

---

## Quick start

**Download the current release:**
[local-service-page-writer.zip](https://github.com/Search-Sherpa/local-service-page-writer/releases/latest/download/local-service-page-writer.zip)

**No-code (recommended for business owners): use a Claude Project.**
See [`project-setup/SETUP-GUIDE.md`](project-setup/SETUP-GUIDE.md) — it walks you through
creating a Project, adding these files as knowledge, onboarding once, and then generating a
page with a single sentence.

**Power users: install as a plugin in Claude Code.**
```
/plugin marketplace add Search-Sherpa/local-service-page-writer
/plugin install local-service-page-writer@search-sherpa-skills
```
Then just ask for a service page. (See the setup guide for details; commands vary by Claude
Code version.)

**Try it fast, anywhere:** paste the contents of `SKILL.md` and
`references/service-page-spec.md` into a Claude chat and say *"Let's onboard my business,
then write my [service] page."*

---

## How it works

```
Onboard once  ──►  Business Profile  ──►  reused for every page
                                            │
                                            ▼
                        "Write my [service] page"  ──►  complete Markdown page
```

Under the hood it runs a five-step loop: **Classify** (is this really a service page?) →
**Collect** (use what you gave, ask only for gaps) → **Validate** (separate real facts from
hype) → **Write** (full page in Markdown) → **QA** (a checklist pass, with missing facts
flagged, not faked).

---

## Repository layout

```
local-service-page-writer/
├── SKILL.md                      # The skill: modes, workflow, guardrails
├── README.md                     # You are here
├── LICENSE                       # MIT
├── CONTRIBUTING.md               # How to request or propose changes
├── CHANGELOG.md                  # Release history
├── references/
│   ├── service-page-spec.md      # The full page specification (the "brain")
│   ├── onboarding-interview.md   # The guided interview + Business Profile format
│   └── quality-checklist.md      # The QA pass
├── templates/
│   ├── intake.md                 # Optional fill-in intake + Business Profile format
│   └── service-intake.md         # The small per-service question set
├── examples/
│   ├── sample-business-profile.md
│   ├── sample-service-intake.md
│   └── sample-service-page.md    # A fully worked (fictional) example
├── evals/                        # Test scenarios (also document intended behavior)
│   ├── evals.json
│   ├── complete-intake.md
│   ├── missing-proof.md
│   └── location-claim-risk.md
├── project-setup/
│   └── SETUP-GUIDE.md            # No-code Claude Project instructions
└── .claude-plugin/
    ├── plugin.json               # Claude Code plugin manifest
    └── marketplace.json          # Claude Code marketplace catalog
```

Curious what "good" looks like? Open
[`examples/sample-service-page.md`](examples/sample-service-page.md). Note how it leaves two
`[INPUT REQUIRED]` markers instead of inventing a warranty and a serviced fuel type — that's
the skill working correctly.

---

## Why the honesty rules matter

A service page is a commercial, sometimes regulated document. A fabricated license or a
fake "24/7 guarantee" isn't a style slip — it can mislead a customer and expose the
business to real liability. This skill treats that boundary as non-negotiable: it omits
what it can't verify and flags what you still need to supply. That's also better SEO —
search systems and customers both reward pages that are useful and true over pages that are
loud.

---

## Customizing it

Everything is Markdown, so edit freely:
- Change the default **tone or reading level** in `references/service-page-spec.md`.
- Add or reorder **body sections** in the section menu of the spec.
- Adjust the **interview questions** in `references/onboarding-interview.md`.
- Tighten or loosen the **QA checklist** in `references/quality-checklist.md`.

The one thing worth keeping intact is the honesty block — it's what makes the output safe to
publish and safe to give away.

---

## Author

Built by **Jeremy Bengtson** — SEO strategist and founder of **The Search Sherpa**.

- Website: https://jeremybengtson.com/
- The Search Sherpa: https://thesearchsherpa.com/
- GitHub: https://github.com/TheSearchSherpa

If this saved you time, a link back or a mention is always appreciated.

## More Claude skill resources

- [Learn Claude Skills](https://learnclaudeskills.com/)
- [Claude Skills Guide](https://claudeskillsguide.com/)

## License

MIT — see [`LICENSE`](LICENSE). Free to use, modify, and redistribute. Attribution
appreciated but not required.

## Contributing

Issues and pull requests are welcome, but only the maintainer can approve changes to this
repository. Read [`CONTRIBUTING.md`](CONTRIBUTING.md), then use the repository's
[issues](https://github.com/Search-Sherpa/local-service-page-writer/issues) or submit a
pull request from a fork.

## Important review notice

This tool produces an AI-assisted draft, not a publication guarantee. The business owner
is responsible for verifying every fact, offer, credential, location, and legal or
industry-specific requirement before publishing. Medical, legal, financial, and other
regulated or safety-critical pages should be reviewed by an appropriately qualified
professional. Nothing in this repository guarantees rankings, leads, or search features.
