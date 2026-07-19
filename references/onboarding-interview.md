# Onboarding Interview

Use this in **onboard mode** to capture reusable, business-level facts once, so every
future service page is fast. The output is a **Business Profile** the user saves and
reuses.

The interview should feel like a friendly consultation, not a form. Follow these rules:

- **Chunk the questions.** Ask in small themed groups, **no more than 3 questions per
  turn**, with a one-line intro to each group ("First, the basics…"). Never dump the whole
  list at once — that's the fastest way to lose a busy owner.
- **Infer before you ask.** If the user already said "we're a family HVAC company that's
  served Boise for 15 years," you've captured business name context, service area, and
  years in business. Don't re-ask. Confirm what you inferred instead.
- **Frame proof as honest discovery.** People are used to AI inventing credentials. Set the
  expectation early: "If you have licenses, certifications, or a real review count we can
  mention, great — if not, we simply leave proof out. I never make it up." This teaches the
  guardrail while gathering facts.
- **Every optional item accepts "skip"** → omit it, don't back-fill.
- **End with a summary and a confirmation** before writing the profile — the user's one
  edit checkpoint.

## Question flow

### Group 1 — The basics
1. What's the exact business name, as it should appear on the site?
2. What kind of business is it? (e.g., plumbing, roofing, HVAC, cleaning, landscaping,
   med spa)
3. Do you work from a physical location customers visit, travel to customers, or both?

### Group 2 — Where you work
4. What city or area is the business based in or centered on?
5. Which cities, towns, or areas do you genuinely serve? (We'll say "serves," not imply an
   office in each one.)
6. Anything that affects *where* or *when* you can work — travel limits, seasons, service
   radius?

### Group 3 — Proof and trust (honest only)
7. Any licenses, certifications, or insurance you can name?
8. Any real, verifiable numbers — years in business, review count/rating, jobs completed?
9. Any warranties or guarantees you actually offer, in your own words?

(If the answer to any of these is "no" or "skip," that's completely fine — the pages will
simply stand on clarity instead.)

### Group 4 — Voice and audience
10. Who's your ideal customer for most jobs?
11. What tone fits your brand — friendly and plain, professional and precise, warm,
    no-nonsense?
12. Any words, claims, or competitors you want the pages to avoid?

### Group 5 — The service list and the ask
13. List the services you'd want pages for (we'll build them one at a time).
14. What's the main action you want visitors to take — call, book online, request a quote?
15. Where does that action go — a phone number, a booking link, a form? (Give the exact
    detail if you have it.)

## Writing the Business Profile

Once confirmed, produce the profile using the format in
`templates/intake.md`'s "Business Profile" structure. Fill only what the user gave you;
mark anything they explicitly want but haven't provided as `[INPUT REQUIRED: …]`; simply
omit anything they skipped.

Then close the loop: show the list of services they named and ask which page to build
first. That hands them an immediate next action and a queue.

Example close:

> Here's your Business Profile — save this text somewhere reusable (a note, a doc, or your
> Claude Project knowledge) and paste it back whenever you want a new page. You listed
> these services: **water heater repair, drain cleaning, sump pump installation, emergency
> plumbing**. Which one should we build first?
