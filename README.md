# employmentArc

A working analysis of **Matthew Don** ([matthewdon.is-a.dev](https://matthewdon.is-a.dev)) and the
employed future that the evidence on that site actually supports.

**Goal:** define the roles worth targeting, prove the fit from the real
experience/projects/skills on the site, name the companies and teams that
value this profile, and list the gaps to close to become a stronger candidate.

> Compiled 2026-10-05. Sources are listed at the bottom. Everything here is
> derived from the public site, public repos and public role research — treat
> the role definitions as durable, and the specific openings as a starting
> point to re-check.

---

## 1. The profile in one page

**What the site says, distilled.**

| Dimension | Evidence |
| --- | --- |
| Self-positioning | "Go-to-market engineer" |
| Domain | B2B outbound, cold calling, SMS, CRM, funnels, backlinks/SEO, social listening, sourcing |
| Core stack | TypeScript, React, Python, Convex, Hono, Vite, XState, Telnyx, Docker, Vercel, Cloudflare R2, MCP, Firecrawl, OpenAI, AMD ROCm |
| Shipped products (2025–2026) | **Log** (social listening, Convex hackathon, 17★, 40.9K views on X), **Rank** (backlink-prospect ranking, Nebius hackathon, 68+ commits), **Blaster** (CRM-driven SMS pipeline, CLI + MCP + HTTP API), **Dialer** (browser cold-calling on Twenty CRM, 127 commits), **Offer** (offer-funnel builder, 56 commits in 17 days) |
| OSS components | `@listeningkit/treg` (3,000+ APIs through one Convex interface, spend limits), `@listeningkit/telnyx` (SMS + delivery events) — both published on npm |
| Earlier ventures | inferencesaver.com (AI gateway; sold 17K ChatGPT accounts in China), pivora.co (outbound platform), Diala (voice-clone cold-calling on AMD MI300X/ROCm), genericalternatives.co.uk (China sourcing), arbeidslink.no (recruitment CRM for Norwegian oil & gas), Evvi.ai (auction auto-bid intelligence) |
| Content / audience | X posts with 13K–40.9K views; hackathon demo videos; background as video editor / social media manager / content strategist for creators with 300K–10M followers |
| Education | Scholarship to University of Salford (digital video production), dropped out |
| Base | Irish, mobile (travelled extensively), China + Europe operating history |

**The through-line:** a commercially-literate builder who ships working software
fast, in public, against real revenue problems — and then promotes it. That is
not a generic software engineer, and it is not a generic salesperson. It is a
specific and *currently in-demand* shape (§3).

---

## 2. How to read "fit"

For each archetype below: **Fit** (strong / moderate / stretch), **why the
evidence supports it**, **who hires it**, and **what's missing**. Gaps are
consolidated into an action list in §5.

The honest summary up front:

- **Strongest fits:** GTM Engineer, Founding/Product Engineer at AI-native
  startups, Forward-Deployed / Applied AI Engineer, Developer Relations.
- **Moderate:** Solutions/Sales Engineer, Technical Founder (or GTM OSS as a
  company).
- **Weak / off-target:** traditional backend SWE at large non-AI companies,
  pure sales, pure marketing, data science.

---

## 3. Target roles (ranked)

### 3.1 GTM Engineer / Founding GTM Engineer — **Strong fit (best lane)**

**Why this is the single best match:** the title on the site is literal, and
the portfolio is the job description. GTM engineering is defined as *building
the systems that generate pipeline* — enrichment, targeting, sending
infrastructure, reply routing, and the integrations between them. He has
shipped: a CRM-driven SMS pipeline (Blaster), a browser cold-calling dialer
(Dialer), an offer-funnel builder (Offer), a backlink-prospect ranker (Rank),
and a social-listening buying-intent tool (Log). That is end-to-end outbound
infrastructure, and he built the interfaces too (CLI + MCP + HTTP API on
Blaster).

He also has the *commercial* half that pure builders lack: he ran a sourcing
company in China, an outbound platform (pivora.co), and a recruitment CRM —
he understands pipeline, CAC, ICP and the difference between a list and a
system. GTM engineering explicitly rewards "commercial thinker + builder."

**Evidence mapped to the role:**

| GTM-eng responsibility | Evidence |
| --- | --- |
| Enrichment / data pipeline | Treg component (3,000+ APIs, spend limits, call log), Blaster prospect discovery with per-call cost ceilings |
| Buying signals / intent | Log scores Reddit/X/Facebook posts 0–100 for buying intent; Rank judges domains act/review/drop |
| Sending infrastructure | Blaster jurisdiction-aware SMS (US 10DLC vs IE/UK alphanumeric), number pools, suppression lists |
| Reply routing / lifecycle | Blaster enrollment lifecycle; Dialer records + transcribes calls via webhooks |
| CRM architecture | Built custom objects in Twenty CRM (Dialer, Offer) |
| AI/LLM in the stack | Firecrawl brand profiling, AI intent scoring, MCP servers, OpenAI endpoints |
| Attribution / analytics | Offer forwards visitor id, UTMs, `fbclid`, `gclid` into each lead |
| LLM/MCP-native outreach | Native `POST /mcp` endpoints on multiple products |

**Who hires it:** Clay, 6sense, HubSpot, Verkada, OpenAI, Notion, Intercom,
Ramp, Klaviyo, Read AI, Langdock (Berlin), Trigger.dev (UK), and the long tail
of Series A/B startups hiring their *first* GTM engineer. Roughly 30% of
postings are "Founding GTM Engineer" — often at companies that look exactly
like his portfolio. Median pay ~$127.5K; senior/staff $180K–$250K+; AI-native
principal $250K–$350K+. Coding (Python/SQL) commands the premium.

**Gap:** the market keyword-matches on **Clay, n8n/Make, HubSpot/Salesforce,
SQL/Python**. He built bespoke equivalents instead of using the standard
tools — a strength in an interview, a liability in an ATS. See §5.

---

### 3.2 Forward-Deployed Engineer (FDE) / Forward-Deployed AI Engineer — **Strong fit**

**Why:** FDE hiring at Palantir/OpenAI/Anthropic explicitly favors four
backgrounds, and he hits three: a full-stack/backend engineer who held the
customer relationship directly (his agency work for arbeidslink.no and his own
sourcing/outbound businesses); an applied-AI engineer who took models to
production against real customer data (Log, Diala voice cloning); and the
**founder-shaped generalist who shipped a product from scratch under real
external user constraints** (all six products, many alone or with one
collaborator).

The FDE job is described as "70% glue code inside the customer's broken
environment" — integration, auth, audit hooks, legacy systems, then shipping
production code. His Blaster/Dialer/Offer work is exactly this shape: SIP/WebRTC
integration, AES-256-GCM credential sealing, signed webhooks, scoped API keys,
deployment on Docker/Hostinger/Vercel.

**Evidence:**

- Native MCP servers as production artifacts (Anthropic FDE listings name MCP
  servers, sub-agents and skills as deliverables).
- Credential security: AES-256-GCM sealing of session credentials; scoped API
  keys; signed webhooks.
- Multi-surface product delivery (CLI + MCP + REST) = the "one capability, many
  entry points" pattern FDEs ship.
- Ran deployments end-to-end, including a self-hosted softphone inside a
  customer context.

**Who hires it:** Palantir (origin of the title), OpenAI, Anthropic,
Databricks, Scale AI, Google Cloud, AWS, Vercel, Glean, Harvey, Cognition,
Baseten, Cresta, Ramp. OpenAI publishes FDE base bands around
$162K–$325K; frontier-lab FDE TC stabilizes at $350K–$550K mid-to-senior.

**Gap:** enterprise hygiene — IAM, VPC/PrivateLink, KMS, audit chains,
eval harnesses in CI, runbooks, rollback plans. His repos have the product
instinct but not the regulated-enterprise paper trail. Also: frontier labs
are overwhelmingly **in-person SF**; his mobility is the advantage (he already
travels) but visa/logistics must be handled.

---

### 3.3 Founding Engineer / Product Engineer (AI-native startups) — **Strong fit**

**Why:** the clearest signal on the site is *shipping speed against real
constraints*: Log in 13 days with one collaborator, Offer in 17 days (56
commits), Blaster and Dialer with 60–127 commits. Founding-engineer hiring
values exactly this "startup CTO" shape — end-to-end ownership, comfort with
ambiguity, no need for a spec. He also picks up unfamiliar domains fast (oil &
gas recruitment CRM, Norway; car-auction auto-bid, Northern Ireland; plastic
cups, China).

**Evidence:** six products shipped in ~2 years across CRM, telephony, SMS,
funnels, social listening, backlinks, WebGL/three.js landers; MIT-licensed
output; 9 architecture diagrams on Log; tests via mock providers.

**Who hires it:** seed–Series A AI-native startups, especially in the Convex /
agent-infra / vertical-AI ecosystem. Convex itself runs a **GTM Engineer** and
**Head of Developer Experience** role and hires people who build on the
platform — a warm, on-thesis target. Trigger.dev (open-source AI agent infra,
$16M Series A) hired a Marketing Lead; adjacent roles exist.

**Gap:** proof of *durability*, not just shipping. Most products have modest
external adoption (1–17★, low npm downloads). Founding roles get flooded by
"built a chatbot" candidates; his differentiator is revenue-domain products,
so he must lead with pipeline/revenue outcomes, not feature lists.

---

### 3.4 Developer Relations / DevRel Engineer — **Strong fit**

**Why:** this is the role that combines his two rare halves: genuine shipping
credibility **and** a content/audience engine. The site itself is a
demonstration — technical deep-dives (proxy rotation, anti-detect browsers on
Camoufox, WebGL dithered landers), X posts with 13K–40.9K views, hackathon
demos, and a video-production background (video editor / content strategist
for 300K–10M-follower creators). Supabase's DevRel bar — "you're equally
comfortable writing a video script and TypeScript" — is almost written for him.

**Evidence:**

- Publishes technical *walkthroughs* (proxy rotation method; why "solved
  browser use" claims are false).
- OSS components with docs and integration guides (`@listeningkit/treg`,
  `@listeningkit/telnyx`).
- MCP-native products → strong talking points for the 2026 DevRel shift toward
  agent experiences.
- Audience on X + video skills = the "growing audience on YouTube/Twitch/X"
  bonus that DevRel postings explicitly list.

**Who hires it:** Supabase, Convex (Head of Developer Experience), Trigger.dev,
Vercel, Clerk, Resend, Neon, Liveblocks, and open-source infra companies. Pay:
global median ~$208K; Google-level DevRel $376K+ TC.

**Gap:** his content is currently **promotional/agency-flavored**, not
maintainer-flavored. DevRel employers want sustained OSS engagement —
maintaining a repo, triaging issues, conference talks, docs contributions —
not just launch threads. Needs a "public maintainer" identity, not just a
"growth" one, plus measurable community metrics.

---

### 3.5 Solutions Engineer / Sales Engineer (pre-sales) — **Moderate fit**

**Why:** he has the technical range and the ability to demo (he already does
product walkthroughs and hackathon demos), and he has sold/run outbound. Many
of his products *are* the tooling an SE would demo. Databricks and Vercel pay
SE/Solutions Architect roles on OTE, and AI-native SE roles are growing.

**Watch-outs:** SE is deal-centric and metrics are win rate/deal velocity —
the OTE component and explicit quota culture may not suit a builder. The role
also tends to want enterprise polish (exec decks, security questionnaires)
that he has not demonstrated. Treat as a **fallback / on-ramp**, not the
primary target. Cresta's $185K–$235K+ for 3+ years is the most accessible
high-paying version.

---

### 3.6 Technical founder / GTM OSS as a company — **Moderate, and arguably the real thesis**

**Why:** the site's own narrative — "we're going to make GTM OSS one
integration at a time," the Treg/Telnyx components, the OSS agency model
(discuss tools → build → content → sponsorship) — is a founder thesis, not a
job application. The founder path is where his messy, multi-domain,
commercially-fluent profile is an *asset* rather than a placement problem.

**What's already in place:** two npm packages, MIT-licensed products, an
audience, a repeatable hackathon cadence, and a monetization model (sponsorship
+ services) described in public.

**Gap:** distribution and monetization to date are thin (npm downloads in the
single digits, stars in the single/double digits). The open question is whether
to raise/join a team or keep bootstrapping.

---

## 4. Companies & teams that would value this

Grouped by why they'd care. Re-check openings; these are patterns, not live
guarantees.

**A. GTM-tooling and AI-GTM companies (best keyword overlap + a portfolio they recognize)**
Clay, 6sense, HubSpot, Verkada, Klaviyo, Read AI, Langdock (Berlin),
Trigger.dev (UK), Apollo-adjacent startups, and the ~30% of postings labeled
"Founding GTM Engineer" at Series A/B.

**B. Frontier-AI deployment teams (FDE / Applied AI)**
Palantir, OpenAI, Anthropic, Scale AI, Databricks, Google Cloud,
AWS Professional Services, Vercel, Glean, Harvey, Cognition, Baseten, Cresta,
Ramp. Note the location reality: mostly SF/NYC in-person.

**C. Open-source / developer-platform companies (DevRel + product eng)**
Convex, Supabase, Vercel, Clerk, Resend, Neon, Liveblocks, PlanetScale,
Trigger.dev. Convex is doubly relevant: he already builds on it, published a
component for it, and Convex is actively hiring GTM + DevEx.

**D. Vertical / agent startups needing a founder-shaped first engineer**
Seed–Series A companies in sales tech, recruitment tech, logistics/sourcing,
and vertical AI — domains he has directly built in.

**E. The ecosystem around his own products (warm intros)**
Twenty CRM (he builds custom objects on it and contributes), Telnyx (he ships
their SMS/SIP surface), Firecrawl, XState, Cloudflare R2 — vendors whose
developer-relations/product teams benefit from a power user with an audience.

---

## 5. Gaps to close (the actual work)

Ranked by leverage. Each has a concrete, shippable fix.

### G1 — Translate bespoke work into JD keywords (highest leverage, lowest effort)
The market screens for **Clay, n8n/Make/Zapier, HubSpot/Salesforce, SQL,
Python**. He has built equivalents from scratch, which is more impressive but
invisible to ATS and recruiters.
**Fix:** publish one page per product written in JD language ("built a
waterfall enrichment pipeline equivalent to Clay's, with per-provider cost
ceilings; wired to a 33-tool MCP server"), and get hands-on with Clay + one
CRM (Salesforce or HubSpot) so the keyword is true.

### G2 — Add revenue/impact numbers to every project
The site describes architecture well but rarely quantifies business outcome
(pipeline generated, meetings booked, CAC changed, hours saved).
**Fix:** attach one defensible number to each of Log, Blaster, Dialer, Offer,
Rank — even a pilot number from his own agency use. GTM/FDE hiring explicitly
screens on "can they frame work in pipeline terms."

### G3 — Prove production AI, not demos
Rank is explicitly tested against mocks with live model calls "not switched
on." Frontier FDE/Applied-AI roles want production LLM systems with evals.
**Fix:** ship one end-to-end production AI deployment with (a) an eval harness
running in CI, (b) auth wired to a real IdP, (c) audit logging, (d) cost
telemetry, and (e) a **postmortem-style write-up** (what broke, trade-offs,
what he'd do differently). Hiring managers read postmortems, not tutorials.

### G4 — Build the enterprise/regulated paper trail
No evidence yet of IAM/least-privilege, VPC/PrivateLink, KMS/envelope
encryption, audit/compliance, runbooks, rollback plans.
**Fix:** take one existing product (Blaster is closest — it already has SMS
compliance and scoped keys) and add a written architecture doc showing the IAM
model, data-residency story, threat model, and day-two operations. This is the
FDE differentiator.

### G5 — Build a public maintainer identity (for DevRel / OSS credibility)
Current public output is launch/growth content, not sustained maintenance.
**Fix:** pick one repo (Treg is the strongest candidate — pipeline infra,
cost ceilings, MCP-relevant), commit to it publicly for a quarter: issue
triage, docs, changelog, a real README quickstart, adoption metrics. Speak at a
meetup/hackathon and publish the recording. Track community numbers.

### G6 — Turn the audience into measurable distribution
"40.9K views on X" is good; hiring managers want *conversion* and repeatability.
**Fix:** publish a one-page case study of the 13K-view ICP-targeted campaign
with CTR/signup numbers, and a content cadence (weekly technical post) with
followers/subscribers tracked over time.

### G7 — Decide the location/visa posture
Frontier labs are in-person SF/NYC; the highest-fit remote roles are Europe
(Berlin, London, Amsterdam) and US-remote. His mobility is an asset but visas
are a gate.
**Fix:** pick a primary market (EU-remote vs SF-relocation), state willingness
to travel 25–50%, and confirm work-authorization path (Irish/EU passport is a
strong base for the European market).

### G8 — Formalize the "why hire me" narrative
Right now the site reads as a founder's brag reel. For employment, recruiters
need a role-shaped story.
**Fix:** one paragraph that maps the portfolio onto one target archetype
(suggested: *"GTM/FDE engineer who ships revenue infrastructure end-to-end and
has already built the outbound stack — CRM, SMS, dialing, funnels, intent —
in public"*), with three proof links and one impact metric each.

---

## 6. Positioning: the one-line pitch

> **Go-to-market engineer who ships the whole outbound stack in public.**
> Shipped six revenue-infrastructure products in two years — a CRM-driven SMS
> pipeline, a browser dialer on Twenty CRM, a social-listening buying-intent
> engine, a backlink-prospect ranker, and an offer-funnel builder — published
> the underlying Convex components on npm, and built them as CLI + MCP + HTTP
> so agents can drive them. Commercially fluent: ran sourcing/outbound
> businesses across Europe and China. Speaks the language of pipeline, not
> just pull requests.

Best used for **GTM Engineer, Forward-Deployed/AI Engineer, Founding Product
Engineer, and DevRel** applications. Tune the third clause per role (revenue
systems for GTM, integration/enterprise for FDE, OSS/community for DevRel).

---

## 7. 30 / 60 / 90 action plan

**Days 1–30 — Package the evidence**
- [ ] Add impact metrics to the five flagship projects (G2).
- [ ] Rewrite each project into JD-keyword language (G1).
- [ ] One-page narrative + role-shaped resume variants (GTM / FDE / Founding / DevRel) (G8).
- [ ] Stand up a clean portfolio `README` versioned in this repo.

**Days 31–60 — Close the visible gaps**
- [ ] Ship Treg as a published, documented, maintained component (G5).
- [ ] Add enterprise architecture doc + evals/CI to one product (G3, G4).
- [ ] Get hands-on with Clay + one CRM and document a real workflow (G1).
- [ ] Publish the content-campaign case study with numbers (G6).

**Days 61–90 — Go to market (the meta-move)**
- [ ] Apply to / get intros at Group A–C companies (§4), led by Convex, Clay, Trigger.dev, Supabase.
- [ ] Two conference/meetup talks or a recorded deep-dive.
- [ ] Run an open-source contribution sprint at a target vendor (Twenty, Telnyx, Convex) to create warm ties.
- [ ] Decide founder vs employed track and commit; the same artifacts serve both.

---

## 8. Interview / take-home notes by archetype

- **GTM Engineer:** expect a take-home building an enrichment/outbound workflow.
  Prepare a 5-minute walkthrough of Blaster's jurisdiction-aware sending and
  Treg's per-call cost ceilings. Know Clay/n8n mapping.
- **FDE / Applied AI:** expect an open-ended case ("customer wants an AI system
  they can't specify"). Lead with scope + eval design + what you'd *not*
  promise. Bring the enterprise architecture doc (G4).
- **Founding/Product Engineer:** expect "ship this in a week" energy. Lead with
  Log-in-13-days / Offer-in-17-days and the architecture diagrams. Discuss
  failure modes.
- **DevRel:** expect a content/talk sample. Lead with the proxy-rotation and
  anti-detect walkthroughs plus the audience data. Show maintainer cadence.

---

## 9. Sources

- Primary: [matthewdon.is-a.dev](https://matthewdon.is-a.dev) (fetched 2026-10-05).
- Repos referenced on the site: `matthewdonsemail-lab/{log,rank,blaster,dialer,offer}`, npm `@listeningkit/{treg,telnyx}`.
- **GTM Engineer role:** fullcast.com GTM engineer job description; revenueflow.com "What Is a GTM Engineer"; pipeline.zoominfo.com "What Is GTM Engineering"; cremanski.com "we read 100 job ads"; gtmonly.com; Norwest "What is a GTM Engineer"; omnesgroup.com.
- **Forward-Deployed Engineer:** fdejobslist.com "How to hire a Forward Deployed Engineer"; oflight.co.jp FDE 2026 guide; provn.co FDE role/skills/salary; recruitslab.com; arc-codex.com; creativeminds.dev FDE career/portfolio.
- **DevRel:** Supabase Developer Relations Engineer postings (Coatue/DevRelJobs/LinkedIn); resumegeni.com developer-advocate guide.
- **Companies/hiring signals:** gtmjobs.substack.com; refery.substack.com; gtmail.nl Benelux GTM-engineering state; svgtm.com; convex.dev/jobs; techinterview.org and stillhiring.fyi (Convex).

---

*This is a living document. Update metrics, role definitions and target lists
as the market moves; the durable parts are the archetypes, the evidence map and
the gap list.*
