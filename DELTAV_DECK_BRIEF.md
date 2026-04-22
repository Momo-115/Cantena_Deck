# Delta V Pitch Deck — Full Brief for Claude

## WHAT THIS FILE IS
This is the complete brief for Cantena's Delta V accelerator pitch deck. It contains deck structure, per-slide content and current visual state, speaker script, backup slides, competitive analysis, PMR data, and visual direction. The main deck is implemented in `CantenaDeck_DeltaV.html`; this brief reflects its current state after the Paul-Cheek-style review and founder revisions (April 2026).

## CURRENT STATE
- **Main deck (Slides 0–7):** implemented in `CantenaDeck_DeltaV.html`. Content locked and HTML updated (2026-04-22). Completed changes:
  1. ✅ Slide 3 — X-axis label updated to "CERTAINTY ON READINESS"
  2. ✅ Slide 4 — LCD replaced with "NOT READY" in amber (#F59E0B) Inter-bold text; removed 7-segment `FAIL` rects
  3. ✅ Slide 5 — Mohamed's school line updated to "CGO · UMass Bio & Chem '27" (Boston dropped for line-length parity)
  4. ✅ Slide 6 — Validation column rebuilt in new order (Harris first, then LOIs, then pilots); all three now have sub-lines; TAM placeholder was never present in HTML
  5. ✅ Slide 7 — three breathing takeaway anchors added below the hero via new `.ask-takeaways-min` CSS class
  - Image `src` attributes (title-logo, ask-logo, three headshots) were NOT missing — all images are embedded as base64 data URIs in the HTML. The initial read-through missed this because those lines exceed 500 chars.
- **Appendix (B1–B8):** not yet built. To be implemented next.

## FORMAT
- HTML pitch deck (16:9, native 1920x1080 per slide, responsively scaled for display). Inter font. Scroll-based with slide separators.
- Per-slide PNG export via html2canvas (no PDF bundler in this deck). Exports are native 1920x1080 at scale=3 (5760x3240 fidelity) for PowerPoint conversion.
- 1 title slide + 7 main slides + 8 appendix slides = 16 slides total
- Appendix slides should be visually separated with a clear "APPENDIX" divider
- 30pt minimum font size on all main slides (backup slides can be slightly smaller for detail)
- Dark title/CTA slides (`--ink` near-black), warm off-white (`--bone` #F5F3EE) content slides

## CONTEXT

### The Company
**Cantena** — non-destructive concrete moisture testing using microwave reflectometry and Bayesian inversion.

### The Event
**Delta V** — MIT's flagship summer accelerator. Competitive interview round.
- **Format**: 2-minute pitch (strict cutoff at 2:00) followed by 10 minutes of Q&A
- **Slides due**: Thursday April 23, 2026 at 12:00 noon, emailed as PowerPoint (16:9) to deltavstaff@mit.edu
- **Important**: Cantena applied to Delta V with a PREVIOUS idea (quantity takeoff automation). The pivot to moisture testing must be framed as a strength — evidence of disciplined entrepreneurship.

### The Panel
- Ana Bakshi — Martin Trust Center for MIT Entrepreneurship
- Andrew Bialecki — Klaviyo (CEO)
- Steve Fredette — Toast (co-founder)
- Ed Hallen — Klaviyo (co-founder)
- Brian Halligan — HubSpot founder; Propeller Ventures; MIT Lecturer
- Ellen Roche — MIT Professor, Mechanical Engineering

### The Ask
Acceptance into Delta V. That's the only ask. Don't ask for money, intros, or anything else.

### The Founders
- **David Santana — CTO** (the user): MIT CS '27, on leave. Graduate coursework in ML, statistics, probability.
- **Estiven Lezama — CEO**: Harvard Physics '27, on leave. BREAD apparatus experimental RF research experience.
- **Mohamed Mohamed — CGO**: UMass Boston Biology & Chemistry '27, on leave. Wet lab experience for sensor calibration. (On-deck caption shortens to "UMass Bio & Chem '27" — Boston dropped for line-length parity with the other cofounders.)
- All three have been best friends for 7 years (since high school), grew up together in Boston.
- A 4th cofounder (BU CS '26) departed end of March for IBM return offer — do NOT mention in the deck.
- **Presentation format:** all three pitch together. Every slide except the team slide is first-person single-voice (speaker TBD per slide). The team slide is three voices — each cofounder delivers their own self-introduction as their headshot is focused on, then a [speaker TBD] delivers the pivot closer.

### The Technology
Non-destructive moisture testing for concrete slabs:
- **Physics forward model**: Models reflection coefficients based on RH at different layers in the concrete using a layered dielectric model + Fresnel equations across a broadband frequency sweep (1-10 GHz)
- **Bayesian inversion**: MCMC with carefully selected priors to recover RH profile from measured reflection coefficients
- **Hardware**: Vivaldi antenna + nanoVNA, tethered to a laptop (current prototype stage)
- **Key physics**: Water dielectric constant ~80, dry concrete ~4-8. That 10-20x contrast means the RF reflection spectrum is highly sensitive to moisture content and distribution.
- Forward model and Bayesian inversion are nearly complete.

### Previous Idea (for pivot context)
Automating quantity takeoffs (QTO) in preconstruction for commercial GCs, starting with division 9. Abandoned because:
- Startup graveyard (many have tried and failed)
- Pilots losing interest (only 3 LOIs, none committed to real project use)
- Tech was near-impossible (heavy CV/ML on data they didn't have)
- Investors at Suffolk BOOST confirmed it was a dead end

The pivot happened through disciplined PMR: 40+ conversations with GCs, estimators, flooring subs, and professors over 6 weeks. The same industry relationships that informed the QTO decision led directly to discovering the moisture problem.

---

## STORY ARC: FALL-RISE ("Man in a Hole")

The emotional arc starts neutral, drops into the pain (YMCA story, $2.9M), then climbs out with the solution, team, traction, and ask. Ends on a high note.

```
Emotion
  ^
  |                    6  7
  |                   /
  |   1             5
  |    \           /
  |     2        4
  |      \      /
  |       3----
  |
  +-------------------------> Time
```

| # | Slide | Emotion |
|---|-------|---------|
| 1 | Problem — $2.9M | Neutral → falling (tension) |
| 2 | YMCA story — why tools fail | Falling → bottom (frustration) |
| 3 | Competitive position chart | Bottom → rising (clarity) |
| 4 | Solution | Rising (relief, intrigue) |
| 5 | Why us | Rising (respect, conviction) |
| 6 | Traction | High (momentum) |
| 7 | Ask | High (confidence) |

---

## MAIN DECK — 1 TITLE + 7 CONTENT SLIDES

### SLIDE 0: Title (dark)
**Time: not part of the 2:00 budget — on screen while presenter is being introduced**

**On screen (current):**
- Dark background (`--ink` #0A0D12), centered layout.
- Ambient cues: faint radial brightening toward center (`--signal` blue at ~6% opacity) and a single barely-visible broadband frequency sweep line across the lower third (~14% opacity). Evokes RF/physics without shouting.
- White Cantena wordmark logo (520px wide, centered). Embedded as base64 `data:image/png;base64,…` URI in the HTML (same source file — `assets/images/cantena_logo_v1_white_transparent.png` — remains in the repo for reference).
- Thin signal-blue divider rule (72×1px, 60% opacity).
- Tagline (22px, uppercase, letter-spaced 0.28em, 72% white): **"SEE INSIDE CONCRETE"**
- Top-left marker: `CANTENA` (14px, uppercase, tracked, 38% white).
- Bottom-right marker: `DELTA V · APRIL 2026`.

**Script:** none on this slide — held while the presenter is introduced or greets the panel.

---

### SLIDE 1: Problem — The Cost of Getting It Wrong
**Time: 18 seconds**

**On screen (current):**
- Hero number (huge, 288px, near-black): **"$2.9 million."**
- Hero caption (42px) directly below: *"What **one** flooring company spent on moisture failures. / In a single year."* (italicized "one" carries the emphasis; line break preserved)
- Thin divider rule
- Two-stat row (88px numbers, 26px captions):
  - **"$250–500K"** — *"Single incident. Student housing."*
  - **"> $2 / sqft"** — *"RFI cost when moisture is too high."*
- Background: warm off-white (`--bone` #F5F3EE). No photo — clean typographic slide.

**Visual direction:**
- Aesthetic is typographic restraint. The $2.9M hero does the emotional work; the stat row provides credibility without competing for attention.
- No illustrations or photography — per founder's design call, clean beats busy.

**Script:**
"I'm [NAME], cofounder of Cantena. Every commercial building sits on a concrete slab, and before flooring goes down, that concrete has to be dry. When it's not, the costs are catastrophic. A flooring director we interviewed, ten years in the industry, told us his company spent two point nine million dollars on moisture mitigation in a single year. A single incident on a student housing project cost a GC a quarter to half a million dollars."

---

### SLIDE 2: The YMCA Story — Why Current Testing Fails
**Time: 22 seconds**

**On screen (current):**
- Top-view slab schematic (1280×620 SVG). Warm off-white slab fill, thin near-black border, faint interior grid.
- Small grey header label above: `CONCRETE SLAB · TOP VIEW · 10,000 SQFT`
- Below header, sub-label: *"Pass threshold: **≤ 75% RH**"*
- **Four probe markers** placed in the four corners of the slab (not a perfect grid — one in each quadrant):
  - Green filled circles with white checkmark, labeled underneath with RH% and "PASS"
  - Readings: **68%**, **72%**, **73%**, **74%** (all below 75% pass threshold)
  - Each probe has a dashed green coverage ring (~190px radius) to convey "area of confidence"
- **One red failure marker** in the center gap between all four probe coverage rings:
  - Larger red filled circle with white "X"
  - Label: **"98%"** in dark red, bold, with "FAIL" underneath
- Caption below slab (54px): *"YMCA renovation. 4 probes. All passed. **Flooring failed.**"*
- Footnote (22px muted): *"ASTM F2170: drill, wait 24–72 hrs per probe. 4 probes on 10,000 sqft."*

**Visual direction:**
- Slab schematic reads as a construction-drawing top view — thin strokes, neutral fills, architectural feel.
- Coverage rings are the key visual grammar: they make the uncovered center gap obvious, so the red dot's position in that gap tells the story by itself.
- Emotional low point of the deck — visually restrained but the red-in-the-gap composition feels like a failure report.

**Note on numbers:** brief's original 81–89% probe values were replaced with 68–74% to keep the story internally consistent with a ≤75% pass threshold (81–89 would fail under that threshold). Script was updated to drop specific probe numbers ("*All four passed*") so spoken and visual match.

**Script:**
"That same flooring director told us about a YMCA renovation. They drilled four holes, placed four humidity probes, the industry gold standard. All four passed. They installed the flooring. Weeks later, glue was seeping through the seams. They tore it up, tested between the probes: 98 percent. Four points on ten thousand square feet. The test passed. The floor failed."

---

### SLIDE 3: Competitive Position (Mohamed to verify)
**Time: 12 seconds**

**On screen (current):**
- Single-quadrant chart (Aulet/Disciplined Entrepreneurship style — NOT a 2x2 feature matrix). 1360×680 SVG.
- Axes with arrowheads, near-black strokes:
  - X-axis: **"CERTAINTY ON READINESS"** — Low (left) to High (right)
  - Y-axis: **"SPEED TO ANSWER"** — Slow (bottom) to Fast (top)
- Competitors plotted organically as small dark grey dots with 19px text labels:
  - **Top-left cluster** (fast, low certainty): Tramex CMEX5, Wagner C555, DeFelsko
  - **Bottom-right cluster** (slow, high certainty — drill + wait methods): Wagner Rapid RH L6, Vaisala Jade, Tramex Hygro-i
- **Cantena plotted alone in top-right**, larger dot (15px radius) in brand blue (`--moisture` #2B6CB0), 34px bold label. Whitespace around it is the point — no other labels in that quadrant.
- Tagline below chart (44px): *"The industry gives you one or the other. **We give you both.**"* (bold portion in brand blue)

**Visual direction:**
- No status-quo dot, no logos — text labels only, for readability at 1920×1080.
- Whitespace discipline: the empty top-right quadrant IS the message. Do not fill it.

**Script:**
"Here is the competitive landscape through the lens of what our customers care about most: certainty on readiness and speed to answer. The industry gives you one or the other. Fast surface meters can't tell you if a slab is ready. The gold standard takes days and still misses moisture between probes. We are the only solution that gives you both."

---

### SLIDE 4: Our Solution
**Time: 22 seconds**

**On screen (current):**

Single 1460×540 SVG composite, two panes side-by-side:

**Left pane — cross-section (labeled `ANTENNA OVER SLAB`):**
- Stylized handheld device (not a literal Vivaldi photo): dark grey rectangular housing with a small LCD screen on top face and a tapered antenna slot at the bottom.
- **LCD screen displays "NOT READY" in amber (#F59E0B) bold Inter text, letter-spacing 1.5.** (Replaced the original red 7-seg `FAIL` rects — 7-seg couldn't render "NOT READY," and the new flat text is more modern and less alarming.)
- RF wave arcs emanating downward from the antenna slot (three arcs with increasing opacity — 0.35 → 0.5 → 0.65 — to suggest penetration).
- Concrete slab below (770×260), filled with a vertical moisture gradient: dry/light at top (0"), transitioning through blue-grey to saturated darker blue mid-slab (~4–5"), lifting slightly at the bottom.
- Depth tick labels on the left edge of the slab: 0", 2", 4", 6".

**Right pane — product screen (framed chart panel):**
- White chart panel with thin black border, rounded corners.
- Header: **"MOISTURE PROFILE"** (17px bold, tracked). Subhead: *"Recovered RH by depth."*
- Y-axis: depth 0"–6" (top-down). X-axis: RH 0–100%. Labels: "DEPTH" and "RH %".
- Dashed red vertical line at 75% labeled **"≤ 75% PASS"** (matches Slide 2's threshold).
- Recovered moisture curve (3.5px stroke, brand blue) sweeping from ~30% at 0" depth through 78% at 3" to 88% at 5", visually crossing the 75% threshold around 2.5–3" depth. Makes the slab's "not ready" verdict visible.

**Bottom strip — three pillars** with icons, labels, sub-labels:
- Drill icon with red cross: **"No drilling."** — *"Non-destructive."*
- Clock icon: **"Seconds, not days."** — *"Instant readings."*
- Stacked-layers icon: **"Full depth profile."** — *"Every layer measured."*

**Visual direction:**
- Device is intentionally stylized, not a photo of the actual Vivaldi + nanoVNA rig. Aesthetic choice for deck coherence.
- The 75% threshold line is the connective tissue between Slide 2 and Slide 4 — same number, same meaning.
- When swapping LCD text to "NOT READY" in amber, keep 7-segment aesthetic for visual punch.

**Script:**
"We are building a device that gives you the full moisture profile through a concrete slab, instantly, without touching it. We send a broadband RF signal into the concrete. Water has a dielectric constant of 80. Dry concrete is 4 to 8. That massive contrast means the reflection spectrum encodes exactly where the moisture is. We use a physics-based forward model and Bayesian inversion to recover the relative humidity at every depth, in seconds. No drilling. No blind spots."

---

### SLIDE 5: Why Us
**Time: 18 seconds**

**On screen (current):**
- Three headshots in a row (240×240, circular, white 4px border, soft drop shadow).
  - Images are embedded as base64 `data:image/jpeg;base64,…` URIs directly in the HTML (not referenced from `assets/images/`). Source files remain in the repo for reference: `assets/images/david linkedin.jpeg`, `assets/images/estiven linkedin.jpeg`, `assets/images/mohamed linkedin.jpeg`.
- Per-member caption stack (center-aligned, 340px column):
  - Name (32px bold): **David Santana** / **Estiven Lezama** / **Mohamed Mohamed**
  - Role & school (19px, middle-dot separator):
    - `CTO · MIT CS '27`
    - `CEO · Harvard Physics '27`
    - `CGO · UMass Bio & Chem '27` (Boston dropped for line-length parity)
  - Specialty (16px muted):
    - "Machine learning & statistics"
    - "Radiofrequency research"
    - "Wet lab sensor calibration — biology & chemistry"
- Below headshots, a two-line tagline stack:
  - Tagline-primary (26px, muted): *"Friends for 7 years."*
  - Tagline-hero (42px, bold, near-black): **"40+ industry conversations.** / **Killed our first idea. Found this one."**

**Visual direction:**
- Headshots are approachable (not corporate portraits).
- "Friends for 7 years" is a quiet cofounder-trust de-risk signal — important for this panel.
- The pivot mention is a single punchy two-line statement, not a timeline.

**Script (three voices — each cofounder delivers their own line as their headshot is focused on):**

- **David:** "I'm David, CTO. MIT CS with graduate coursework in machine learning and statistics."
- **Estiven:** "I'm Estiven, CEO. Harvard physics, with experimental RF research experience."
- **Mohamed:** "I'm Mohamed, CGO. UMass bio and chem, leading our wet-lab sensor calibration."
- **[speaker TBD]:** "We've been friends for seven years. Six weeks, forty-plus industry conversations. We started with a different idea, our research showed it was a dead end, and we followed the problem here."

---

### SLIDE 6: Traction
**Time: 18 seconds**

**On screen (current):**

Two-column grid: **Validation** (left) and **Product** (right). Each column heading is small, uppercase, tracked, with a thin underline. Items are 36px main lines with 24px muted sub-lines.

**Validation** (ordered by power, most-powerful-first):
- **Harris Flooring: 5 projects, sharing data** / *Same director who quoted the $2.9M figure.* (bullet marker)
- **3 signed LOIs, carried through our pivot** / *Same teams. New idea.* (bullet marker)
- **2 pilots lined up** / *Found us at the Harvard proptech symposium.* (bullet marker)

**Product** (progress-tracking):
- **Physics forward model** — green checkmark marker (done)
- **Bayesian inversion** — green checkmark marker (done)
- **Next: tethered prototype on a real site** — open-circle marker (in progress)

**No TAM figure on this slide.** Market sizing lives in appendix B3 (per founder decision — one number deserves its own slide, not a footnote).

**Visual direction:**
- Harris Flooring bullet first so the panel reads the $2.9M callback before anything else — closes the narrative loop from Slide 1.
- Sub-lines preempt the obvious Q&A probes ("which teams?", "what pivot?", "are those real pilots?") without lengthening the main text.
- Green check vs. open circle in the Product column is the visual grammar for done vs. in-flight — mirrors product-roadmap conventions the panel will instantly parse.

**Script:**
"The flooring director I quoted, who spent $2.9 million on mitigation, has five projects starting and wants to share data with us. Three other companies signed letters of intent that carried through our pivot. Two have committed to pilot once our prototype is ready. Our forward model and Bayesian inversion are nearly complete. This summer, our tethered prototype goes onto a real construction site."

---

### SLIDE 7: Ask (dark slide, matching title slide style)
**Time: 10 seconds**

**On screen:**
- Hero line: **"We want to build this at Delta V."**
- Below, three breathing takeaway anchors (no numbers, no bullets, smaller font, center-aligned):
  - Moisture is a billion-dollar blind spot.
  - We have the physics, the team, the relationships.
  - Coming up: prototype on a real site.
- Cantena logo + contact info at bottom

**Script:**
"We want to build this at Delta V. Three things to remember. Moisture is a billion-dollar blind spot. We have the physics, the team, and the relationships. Coming up: prototype on a real site."

---

## APPENDIX / BACKUP SLIDES (for Q&A)

These should be after a clear "APPENDIX" divider. They won't be presented but the team can pull them up during Q&A.

### B1: Physics Forward Model
- Diagram of layered dielectric model: concrete slab divided into N layers, each with an RH-dependent dielectric constant
- Show how RH maps to dielectric constant via a mixing model
- Show how the layer stack produces reflection coefficients via Fresnel equations across broadband frequency sweep
- Purpose: for Ellen Roche and technical follow-up questions

### B2: Bayesian Inversion
- Measured reflection spectrum as input
- Prior distributions on RH per layer
- MCMC sampling
- Posterior RH profile with uncertainty bands
- Show simulated example: recovered profile vs. true profile with credible intervals
- Purpose: proves the inversion works and quantifies uncertainty

### B3: Market Sizing (Mohamed)
- Beachhead TAM: medium-sized GCs near Boston
- Broader addressable market
- Simple visual: beachhead circle inside larger market circle with dollar figures
- No spreadsheets — just a graph (per Cheek's guidance)
- PLACEHOLDER: cofounder is calculating these numbers

### B4: Business Model (Mohamed)
- How Cantena makes money
- Options being explored: hardware sale, per-test pricing, hardware + subscription
- PLACEHOLDER: cofounder is working on this

### B5: Competitive Landscape Detail (Mohamed)
Full competitor breakdown for deep Q&A:

**Wagner Rapid RH L6** (dominant US player):
- Single-use F2170 sensors, drill 3/4" hole at 40% slab depth, 24hr equilibration
- Point measurements only: 3 sensors per first 1,000 sqft + 1 per additional 1,000 sqft
- ~$8-12 per single-use sensor
- Cantena advantage: non-destructive, instant, full depth profile, no consumables

**Vaisala SHM40 / Jade Smart Cloud** (Finnish, $500M+ revenue company):
- Same borehole method, reusable HUMICAP probes, cloud monitoring option
- Requires network infrastructure for Jade system
- More enterprise-oriented
- Cantena advantage: no drilling, no infrastructure, no cloud subscription, accessible to small subs

**Tramex CMEX5** (Irish, invented first non-destructive meter):
- Impedance-based, ~20mm (3/4") sensing depth
- Qualitative/comparative only — can't answer "is this slab ready?"
- Affected by surface conditions, mix design, rebar proximity
- Cantena advantage: 4x deeper penetration, quantitative depth profile, broadband RF vs single-frequency

**Wagner C555**:
- EMF-based surface meter, 1/2" depth only
- Explicitly marketed as screening tool to sell Rapid RH probes
- Cantena advantage: standalone value, reads 3-4x deeper, quantitative

**GPR (GSSI, Proceq)**:
- $15-50K equipment, qualitative moisture detection, requires expert interpretation
- Fails on wet/fresh concrete
- Cantena advantage: orders of magnitude cheaper, quantitative, works on wet concrete, handheld

### B6: Pivot Timeline
Visual timeline:
- Oct 2025: Team formed, started first idea
- Nov 2025 - Feb 2026: Built QTO product, did PMR, discovered it was a dead end
- Feb 2026: Killed QTO idea based on evidence
- Mar 2026: 40+ PMR conversations, followed the problem to moisture testing
- Apr 2026: Forward model working, pilot sign-ups, Delta V interview
- Emphasize: disciplined entrepreneurship process, not random pivoting

### B7: Product Roadmap
- NOW: Tethered prototype (Vivaldi antenna + nanoVNA + laptop)
- SUMMER 2026: Validate on real construction sites via pilots
- NEXT: Standalone handheld device
- FUTURE: Potential SaaS data layer for historical data and predictive analytics

### B8: Traction Detail
Full traction breakdown for Q&A:
- **Pilots from Harvard symposium**: Jay Willow (Adila Construction), Manish Shah (Two Kings Company)
- **Drew at Harris Flooring**: 10 years in industry, $2.9M/yr in mitigation, 5 upcoming projects with PMs, wants to work with us and share data
- **8 companies from professor's industry board**: Carroll Daniel, Choate, Haskell, Messer, Hood, Evans, Juneau, Harper
- **Pending re-engagement**: Wehr Construction, Slape Construction
- **Tocci Construction**: willing to have team come in person
- **Walsh Brothers**: willing to have team observe takeoff in person
- **Whiting Turner**: high-up contact interested, waiting for product
- **Events**: BU construction conference (10-min slot, only startup), Harvard proptech symposium (4 startups, VCs attending)
- **Warm intros available**: TNT accelerator CEO → McKinsey partner; mentor with construction industry contacts

---

## Q&A PREPARATION

Likely questions and suggested answers:

**"Why did you pivot?"**
"We practiced disciplined entrepreneurship. We talked to 40+ people, discovered QTO was a startup graveyard with no path to defensible technology, and we killed it. Through those same industry relationships, we kept hearing about moisture — and when we looked at the competitive landscape, we found a genuine gap that matched our technical skills perfectly."

**"How do you know this is a real problem?"**
"A flooring director at Harris told us his company spent $2.9 million on moisture mitigation last year. An estimator at Carroll Daniel said every project he's been on has had moisture issues. A superintendent at Juneau described a $250-500K single incident. This isn't hypothetical."

**"Does the physics actually work?"**
"The physics is well-established — water has a dielectric constant of 80 versus 4-8 for dry concrete. That 10-20x contrast means the RF reflection spectrum is highly sensitive to moisture. What's novel is our inversion approach: a physics-based forward model of layered dielectric media combined with Bayesian inference to recover the moisture profile. The forward model and inversion are nearly complete and producing physically reasonable results in simulation."

**"What about Wagner / Tramex / existing tools?"**
"The market splits into two camps that each fail differently. The gold standard — Wagner Rapid RH, F2170 — requires drilling, waiting 24-72 hours, and gives you point measurements that can miss moisture between probes, as the YMCA story shows. Surface meters are instant but only read 3/4 inch deep and are qualitative. Nobody gives you a non-destructive, quantitative, depth-resolved moisture profile."

**"You applied with a different idea. How do we know you won't pivot again?"**
"Our first pivot happened because we hadn't done enough customer discovery before building. This time we did 40+ conversations first. Every call confirms the problem. The competitive landscape has a genuine gap. The physics is working. We're converging, not searching."

**"What's your IP strategy?"**
"The combination of broadband RF reflectometry with physics-constrained Bayesian inversion for concrete moisture profiling is novel. We plan to file a provisional patent. The calibration data we collect from real concrete across different mix designs becomes a compounding data moat."

**"How do you handle rebar?"**
"Rebar is conductive and creates reflections. Our forward model can incorporate known rebar depth and spacing as fixed parameters — GCs know slab thickness and rebar placement from design documents. In practice, we measure between rebar lines. Validating this on real slabs is a key summer milestone."

**"What's your business model?"**
"We're exploring hardware sale and hardware-plus-subscription models based on our PMR. The immediate path is getting the tethered prototype onto a real site — the business model crystallizes once we have validation data." (Update this once cofounder finalizes business model work.)

---

## FULL CONTINUOUS SCRIPT (for practice, ~450 words, ~1:52 at natural pace)

Speaker assignments per slide are TBD except the team slide (three voices, one per cofounder, then one closing line). Use first person throughout; placeholder `[NAME]` in the Slide 1 opener will be filled once opener is assigned.

**[Slide 1 — Problem]**
"I'm [NAME], cofounder of Cantena. Every commercial building sits on a concrete slab, and before flooring goes down, that concrete has to be dry. When it's not, the costs are catastrophic. A flooring director we interviewed, ten years in the industry, told us his company spent two point nine million dollars on moisture mitigation in a single year. A single incident on a student housing project cost a GC a quarter to half a million dollars.

**[Slide 2 — YMCA]**
That same flooring director told us about a YMCA renovation. They drilled four holes, placed four humidity probes, the industry gold standard. All four passed. They installed the flooring. Weeks later, glue was seeping through the seams. They tore it up, tested between the probes: 98 percent. Four points on ten thousand square feet. The test passed. The floor failed.

**[Slide 3 — Competitive Position]**
Here is the competitive landscape through the lens of what our customers care about most: certainty on readiness and speed to answer. The industry gives you one or the other. Fast surface meters can't tell you if a slab is ready. The gold standard takes days and still misses moisture between probes. We are the only solution that gives you both.

**[Slide 4 — Solution]**
We are building a device that gives you the full moisture profile through a concrete slab, instantly, without touching it. We send a broadband RF signal into the concrete. Water has a dielectric constant of 80. Dry concrete is 4 to 8. That massive contrast means the reflection spectrum encodes exactly where the moisture is. We use a physics-based forward model and Bayesian inversion to recover the relative humidity at every depth, in seconds. No drilling. No blind spots.

**[Slide 5 — Team — THREE VOICES]**
*David:* "I'm David, CTO. MIT CS with graduate coursework in machine learning and statistics."
*Estiven:* "I'm Estiven, CEO. Harvard physics, with experimental RF research experience."
*Mohamed:* "I'm Mohamed, CGO. UMass bio and chem, leading our wet-lab sensor calibration."
*[speaker TBD]:* "We've been friends for seven years. Six weeks, forty-plus industry conversations. We started with a different idea, our research showed it was a dead end, and we followed the problem here."

**[Slide 6 — Traction]**
The flooring director I quoted, who spent $2.9 million on mitigation, has five projects starting and wants to share data with us. Three other companies signed letters of intent that carried through our pivot. Two have committed to pilot once our prototype is ready. Our forward model and Bayesian inversion are nearly complete. This summer, our tethered prototype goes onto a real construction site.

**[Slide 7 — Ask]**
We want to build this at Delta V. Three things to remember. Moisture is a billion-dollar blind spot. We have the physics, the team, and the relationships. Coming up: prototype on a real site."

---

## IF SCRIPT RUNS LONG, CUT IN THIS ORDER:
1. Slide 1: drop "A single incident on a student housing project cost a GC a quarter to half a million dollars." (saves ~5 sec)
2. Slide 5 closer: drop "We've been friends for seven years." (saves ~2 sec)
3. Slide 4: replace "Water has a dielectric constant of 80. Dry concrete is 4 to 8. That massive contrast means the reflection spectrum encodes exactly where the moisture is." with "The massive dielectric contrast between water and dry concrete means the reflection spectrum encodes where the moisture is." (saves ~3 sec)

---

## EXISTING ASSETS IN THIS REPO
- `assets/images/david linkedin.jpeg` — David's headshot (Slide 5)
- `assets/images/estiven linkedin.jpeg` — Estiven's headshot (Slide 5)
- `assets/images/mohamed linkedin.jpeg` — Mohamed's headshot (Slide 5)
- `assets/images/ernesto linkedin.jpeg` — departed cofounder, not used in this deck
- `assets/images/cantena_logo_v1_white_transparent.png` — white Cantena logo (title + ask slides)
- `assets/images/White Cantena logo (NB).png` — white logo variant
- Various GC logos in assets/images/ (Carroll Daniel, Choate, Haskell, Messer, Hood, Evans, Juneau, Harper, Skanska, Pulte, Timberlab — legacy from QTO pitch, most unused in DeltaV deck)
- `CantenaDeck_Moisture.html` — previous version of a moisture-focused deck, use as HTML/CSS framework reference
- `assets/js/html2canvas.min.js` — per-slide PNG export library (used in current deck)
- `assets/js/jspdf.umd.min.js` — present in repo but NOT loaded in DeltaV deck (PNG per-slide export only; PDF assembly would be done downstream if needed)
- `assets/css/` — font CSS files

## DESIGN NOTES
- Style tokens defined in `:root` of DeltaV deck CSS:
  - `--ink` #0A0D12 (near-black), `--ink-soft` #111722
  - `--bone` #F5F3EE (warm off-white content background)
  - `--signal` #7FB3FF (cool blue for RF/signal cues)
  - `--moisture` #2B6CB0 (deeper blue for water/moisture/brand)
  - `--warn` #E85D4E (warm red for failure states)
  - `--text` #0F1419, `--text-mute` #5A6472
- Inter font family, loaded from Google Fonts (weights 200–900)
- 16:9 ratio, **native 1920×1080 per slide** (previous decks used 1060×596 — this one is 4K-ready). Slides scale responsively in the browser via CSS transforms; export is always at native 1920×1080.
- PNG per-slide export via the top-right control bar (`html2canvas` at scale=3). For Delta V PPT submission, exports are dropped into PowerPoint slides.
- Dark slides: title (`--ink`) and ask (`--ink`). Content slides: `--bone`. No mixing.
