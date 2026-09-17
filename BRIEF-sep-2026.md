# Site refresh brief — September 2026

Agreed with Andy on 17-Sep-2026 in the mentor-agent project. Build it here. Content changes go in `projects.json`, design changes in `index.html` (see CLAUDE.md).

**Before touching `index.html`, invoke the `frontend-design` skill.** Use it for a refresh, not a redesign. Keep the existing identity: understated, lower-case, monospace headings, the effort/value/usage meters. Spend the design effort on legibility and contrast, the hierarchy between the At work and At home sections, the card anatomy, and the popup gallery. It should look deliberate, not templated, and should not turn into a glossy SaaS landing page.

**Deadline:** a first pass today (17-Sep), finished Fri 18-Sep. The LinkedIn post that points at the site goes out Mon 21-Sep.

---

## 1. What the site is for

Not "stuff I made". The site is evidence of **an AI-first commercial leader**: someone who saw what today's tools can do for commercial operations and built it, rather than waiting for IT. The work uses AI to improve **quality and commercial outcomes**, not just to polish a proposal in ChatGPT.

**The risk to design against:** looking like a distracted CCO tinkering in his shed. So:

- Work comes first and gets the space. Home builds come second.
- Every work card leads with the **commercial problem and the result**, not the technology.
- The home builds stay, and they're framed as what they are: a family man whose kids have learned that if they can describe it, we can build it.
- "Not a developer" stays. It's the point.
- The site can say it was a quick build. That fits the story. It still has to be engaging, usable and informative.

**Audience:** someone who clicks through from LinkedIn, probably on a phone, giving it 20 seconds. Hiring managers, search partners, founders who might want consultancy.

---

## 2. Andy's feedback (all agreed)

1. **The text is grey and washed out.** It doesn't invite reading or clicking. Body text is Space Grotesk at weight 300 in `--secondary #5a5a5a` / `--muted #999`. Go darker **and** heavier: body at 400, key lines at 500, `--secondary` nearer `#3a3a3a`, and `--muted` only for true metadata. Check dark mode gets the same lift. Keep the monospace heading feel.
2. **The descriptions are too long** (150–520 characters on the card). Cards get a **one-sentence strapline** instead. The detail moves to the popup.
3. **Popup:**
   - **Several images with next/previous** (arrows, dots, keyboard left/right, swipe on mobile). Change the schema from `image` to `images: []`, and still accept the old single `image`.
   - **Bring the description to life:** technology pills, plus a clear status pill (live / daily use / in use at home / shipped / retired).
   - Structure: strapline → what it does (3 short bullets) → the outcome → tech pills → effort/value/usage meters (keep them, the tooltips are where the personality is).

---

## 3. Structure

**Header**
- Title and tagline: keep the lower-case, understated voice, but not "stuff i made". Suggestion: title `things i've built`, tagline `AI in commercial operations, and at home`.
- Role line: `CCO at a travel tech company` goes out of date on 30-Sep. Suggestion: `Andy Keeley · commercial leader · not a developer`. **Andy to confirm.**
- Email and GitHub links visible, not grey.

**Intro: rewrite** (it currently puts the maths game in the first paragraph). Draft:

> I'm a commercial leader, not a developer. In February I started building with Claude Code, on the view that the tools had quietly become good enough for someone who understands the problem to build the fix himself. Seven months on, it's how I prepare for negotiations, answer RFPs, keep the CRM honest and run my week. The hard part was never the code. It was describing the problem properly, arguing with the output until it was right, and then actually using it.
>
> At home, my kids have worked out that if they can describe it, we can build it.

**Section 1: At work** (featured, larger cards, in this order)
**Section 2: At home** (smaller cards or a tighter grid, one line of framing above)

**Remove:** `not-so-fast` (never used) and `ar-collections-copilot` (never got off the ground).

---

## 4. Cards: straplines and popup copy

Straplines are about outcomes, in British English, with no hype. Copy below is a first draft. Check facts against each repo before publishing.

### At work

**mentor-agent** (status: daily use)
Strapline: *A chief of staff with an IQ of 140, sitting on my shoulder.*
What it does:
- Reads my calendar and inbox every morning and tells me what actually matters today, not just what's loudest
- Runs my GTD system and EOS rocks, and holds me to account when something slips
- Co-pilots my inbox: drafts in my voice, and flags what I've promised and not yet done
- Prepares me for every negotiation with a structured six-block deal prep
- Second pair of eyes on contracts and legal letters before they go to the lawyers
- Writes the briefs that get outstanding results out of Claude Design
Outcome: *Nothing gets dropped, and every hard conversation starts prepared.*
Tech: claude code · mcp · gmail · google calendar · python
Visuals (dummy data only): morning brief · GTD "this week" view · a deal prep brief · a Claude Design output made from one of its briefs

**RFP builder** (new card; status: in use)
Strapline: *A first-draft RFP response in under two hours instead of a week, so the week goes on the win strategy.*
What it does:
- Builds a searchable corpus from every past bid, product document and security answer
- Drafts each answer from what we've actually said and delivered before, with the source cited
- Flags the questions it can't answer confidently, so a human writes those properly
Outcome: *Faster, and more consistent. The time goes into the answers that win the bid, not retyping the ones we've written twenty times.*
⚠️ Framing: speed must never read as corner-cutting. Lead with consistency and where the time goes.
Tech: claude · python · document corpus

**Deal prep** (new card; status: in use)
Strapline: *Six questions answered before every negotiation, every time.*
What it does: a questioning agent that works through context, positioning, deal dynamics, gaps and strategy, then produces a one-page brief. Three levels of rigour, depending on what's at stake.
Outcome: *No negotiation starts on instinct alone.*
Tech: claude code skill · yaml

**Deal sprint board** (new card; status: shipped)
Strapline: *Every open deal, its stage and whether we're genuinely ready to close, on one screen.*
What it does: the sprint board across all live deals. Each card shows five gates plus a readiness "spine" drawn from the deal prep, and readiness is calculated, never hand-set, so it can't go stale.
Tech: python · fastapi · yaml

**HubSpot integration** (new card; status: retired)
Strapline: *The CRM kept in line with the real pipeline, without the Friday-afternoon admin.*
What it does: pulled, reconciled and pushed deal changes between the working pipeline and HubSpot, with a dry run and a verification pass.
Honest status line: retired when the book got small enough to manage directly.
Tech: node.js · hubspot api

**customer-health-dashboard** (existing; shorten)
Strapline: *Every customer's health on one page, straight into the board pack.*

**hotel booking engine** (existing `hotel-booking-app`; keep)
Strapline: *A working booking journey on our own hotel API, built to show engineering what was possible.*

### At home

Framing line above the section: *Mostly built because someone at home asked for it.*

Keep as they are, but each needs a strapline: sorry-quick-q · investment-agent · zenbox · fitness-mentor · health-tracker · maths-challenge · anki-srs · sonic-fighters · realm-raiders · beyblade-clash · wordle-solver · fitness-tracker.

---

## 5. Screenshots: Andy's job

Two or three per featured work card. **Dummy or blurred data only: no customer names, values or contacts.** 16:10, 1600×1000.

| Card | Shots |
|---|---|
| mentor-agent | morning brief · GTD this-week view · deal prep brief · a Claude Design output |
| RFP builder | a drafted answer with its source cited |
| Deal prep | a one-page brief (dummy deal) |
| Deal sprint board | the board with dummy deals |
| customer-health-dashboard | the dashboard with dummy accounts |
| hotel booking engine | search results · booking journey |

Build the gallery so cards work with zero, one or many images.

---

## 6. Must work

- On a phone first: cards stack, the popup works full-screen, the gallery swipes
- Light and dark mode both readable
- No build step (unchanged)
- Update `site.updated`

## 7. Open for Andy

- Title, tagline and role line wording
- Is Magpie (the AI product priced and sold to customers) a card? It's the strongest commercial story, but it's intuitive's product, so it would need careful wording.

---

## 8. Round 2: review of the live site (17-Sep, afternoon)

The first pass is a big step forward: legible text, straplines working, work before home, mentor-agent leading. These fixes are in priority order. Keep using `frontend-design` for 1 and 4.

**Before Monday's post**

1. **Work cards look unfinished.** Every work card has a large grey image area holding only an emoji, while the home cards (no image area) look tidier. **When a card has no images, collapse or hide the image area.** Keep the emoji small next to the name, as the home cards do. When screenshots are added later, the image area comes back automatically. This applies to the featured mentor-agent card too.
2. **The "notes" section repeats the intro** ("not a developer", "the hard part was never the code"). Remove the first three notes. Keep only the last one ("If you've got a problem that feels like it should be software but you don't have developers to build it — get in touch. I might be able to help.") and make it the closing line of the page, visible but not shouty.
3. **Remove the backlog section.** The items have no `name` (so the headings render blank) and they don't help the site's argument. Delete the `backlog` array, or stop rendering it.
4. **Mobile check.** A 390px-wide render showed text and cards cut off on the right (header role line, intro, cards). It may be a headless-browser artefact, but verify at 360–390px: no horizontal scroll, the header line wraps, cards fit the width, and the popup and gallery work full-screen.

**Worth doing**

5. **Reorder the work section:** mentor-agent · rfp builder · deal prep · customer-health-dashboard · deal sprint board · hotel booking engine · hubspot integration (retired goes last).
6. **Meter key.** "Effort" at 5/5 in red can read as "hard work" or "expensive" to a commercial reader, and the tooltips don't work on touch. Add a one-line key near the first section, e.g. `effort = how long it took to build · value = what it's worth to me · usage = how often it's used`, or make the tooltips tappable.

**Tidy (no visible change)**

7. Remove the legacy `description` fields from work cards that now have `bullets` (mentor-agent, customer-health-dashboard, hotel booking engine). They aren't rendered, and the mentor-agent one carries old copy.

**Waiting on Andy (don't change yet)**

- `health-tracker`: keep, soften or drop. Leave it as it is until he decides.
- Screenshots for the work cards (see section 5).

---

## 10. Round 3: one collection, ordered by strength (17-Sep, afternoon)

**Andy's call, and it replaces the at work / at home split in section 3.** The best things he's built, apart from mentor-agent, are personal. They're also the most visual and the ones he uses daily. Leading with commercial tools that "look like anyone will have done similar" undersells the skill. The site becomes one collection that says **this guy gets AI and builds real things he actually uses**. The commercial argument goes in the LinkedIn post, not in the page structure.

**The tinkering risk is handled by the ordering:** strongest and most used first, whatever the category. A small `work` or `home` tag on each card keeps the context.

### Done already in this project (by the mentor-agent session)
- mentor-agent `strapline` updated (below) and `images` set to: system diagram → today page → GTD terminal
- New images in `images/`: `mentor-agent-0-system.png`, `outreach-board-1.png` (all dummy data)

### Structure changes
1. **Remove the two sections** (`sections.work` / `sections.home` and their framing lines). One grid.
2. **Add a `tag` field** per project: `work` or `home`. Render it as a small quiet pill next to the status pill. Keep the meter key once, above the grid.
3. **mentor-agent stays featured** at the top (full-width card).
4. **Order** (use the `projects` array order):
   1. mentor-agent (featured)
   2. sorry-quick-q
   3. investment-agent
   4. fitness-mentor
   5. anki-srs
   6. health-tracker (see the note under "Waiting on Andy")
   7. outreach board (new)
   8. commercial toolkit (new, merged)
   9. zenbox
   10. hotel booking engine
   11. maths-challenge
   12. sonic-fighters
   13. realm-raiders
   14. beyblade-clash
   15. wordle-solver
   16. fitness-tracker
5. **Intro:** trim the commercial-first framing. Suggested:
   > I'm a commercial leader, not a developer. In February I started building with Claude Code, on the view that the tools had quietly become good enough for someone who understands the problem to build the fix themselves. Seven months on, some of it runs my working week and some of it runs the house. Most of it I use every day. The hard part was never the code. It was describing the problem properly, arguing with the output until it was right, and then actually using it.
6. **Tagline:** `AI in commercial operations, and at home` → `built with Claude Code, and used every day`.

### mentor-agent: new strapline (already in projects.json)
*Not a chatbot. A system: my inbox, calendar, pipeline and customer files, organised so AI can actually run my week with me.*
Update its bullets to match the diagram: connected to Gmail, Calendar and the EOS rocks store · structured memory (state handover, a lessons file of its own mistakes, GTD, pipeline, account files, knowledge base, daily journal) · one-letter commands and skills · morning and Friday rituals · outputs: today's plan, deal prep briefs, drafts, boards, design briefs.

### New card: commercial toolkit (tag `work`)
**Replaces five cards:** rfp builder, deal prep, deal sprint board, hubspot integration, customer-health-dashboard. Delete those five objects.
- name: `commercial toolkit` · status: live · statusLabel: `in use`
- strapline: *The commercial jobs I used to do by hand: RFPs, negotiation prep, the deal board, CRM hygiene and customer health.*
- bullets:
  - RFP builder: first-pass answers drafted from everything we've written before, with sources, and gaps left blank for a human
  - Deal prep: a questioning agent that won't produce a brief until the value case, leverage, objections and ask are credible
  - Deal sprint board: five gates per deal, with readiness calculated from the prep, never hand-set
  - Customer health: one score per account, straight into the board pack
  - HubSpot sync: CRM kept in line with the working pipeline (retired when the book got small)
- outcome: *Each one took a recurring commercial job and made it faster and more consistent.*
- tags: claude api · python · fastapi · node.js · hubspot api
- effort/value/usage: take the highest of the five for effort, 4 value, 4 usage (Andy to adjust tooltips)
- images, in order:
  `images/rfp-builder-1-review.png`, `images/deal-prep-1-brief.png`, `images/deal-sprint-board-1.png`, `images/deal-sprint-board-2-prep.png`, `images/customer-health-1-summary.png`, `images/customer-health-2-priority.png`, `images/hubspot-integration-1-dry-run.png`, `images/rfp-builder-2-run.png`

### New card: outreach board (tag `work`)
- name: `outreach board` · status: live · statusLabel: `daily use`
- strapline: *A job search run like a sales pipeline: every contact scored, staged, and with a clear view of whose move it is.*
- bullets:
  - Every person and role scored on desire × winnability, so the list doesn't quietly reorder itself around whatever's available
  - Stages with a definition, not a feeling: "warm" means they advocate for you without being asked
  - Whose move it is flips automatically when a chase date passes
  - A weekly scorecard where the only leading indicator is conversations opened
- outcome: *No warm lead goes cold because nobody noticed it was my move.*
- tags: python · fastapi · yaml · claude code
- images: `images/outreach-board-1.png`

### Waiting on Andy
- **health-tracker and investment-agent screenshots:** real personal data or dummy? Don't add new images for these until he says.
- Hotel booking engine screenshots.
