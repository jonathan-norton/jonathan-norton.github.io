# COPY.md — Portfolio Site Copy

All live words on the site, in page order. Components pull copy from here only (per CLAUDE.md). Square-bracketed items are notes to the builder, not rendered text.

---

## Meta / SEO

- **Title tag:** `Jonathan Norton — CS Senior at Florida State | AI/ML Projects`
- **Meta description:** `Jonathan Norton is a Computer Science senior at Florida State University building AI/ML projects. View projects and resume.`
- **OG title:** `Jonathan Norton — Portfolio`
- **OG description:** `CS senior at Florida State building AI/ML projects, recently on the AI Execution Team at Raymond James.`

[The live site is currently serving an OG description that does not appear in this file, and a meta description that does not match the one above. Both are hardcoded somewhere outside COPY.md. Grep the repo for `og:description` and `currently interning` and fix those occurrences too, or this file will keep drifting from what ships.]

## Nav

- Logo/wordmark text: `Jonathan Norton`
- Links: `Projects` · `About` · `Contact`
- Button (always visible): `Resume`

---

## Section 1 — Hero

**H1:** `Jonathan Norton`

**Subline:** `CS senior at Florida State building AI/ML projects. Recently on the AI Execution Team at Raymond James.`

**Primary button:** `View Resume`
**Secondary button:** `GitHub`

**Inline contact row:** [email icon → mailto:jonathannorton754@gmail.com] · [LinkedIn icon → https://www.linkedin.com/in/jonathanmnorton/]

**Currently strip (label + items):** `CURRENTLY` — `Recruiting for new-grad software engineering and technical PM roles` · `Building a cross-platform networking app for Greek organizations` · `AfroTech-bound this November`
[Update these items as life moves — this strip is the site's freshness signal. Do not publish dates for things that have not happened yet; a passed date is worse than no date. Revisit the AfroTech item after November 2026.]

---

## Section 2 — Projects

**Section heading (H2):** `Projects`
**Section intro line:** `Application, machine learning, and data work, with code you can read on GitHub.`

### Card 1
- **Label:** `APPLICATION DEVELOPMENT`
- **Title (H3):** `Hospital Portal`
- **Body:** `A cross-platform patient and appointment manager built in .NET MAUI, backed by its own REST API and a scheduling service that refuses physician and room double-bookings.`
- **Metric line:** `Full CRUD across patients, physicians, and appointments`
- **Link:** `View on GitHub →` [→ https://github.com/jonathan-norton/hospital-portal]
[Confirm the repo slug before publishing. If the repo is private, make it public or drop the link rather than shipping a 404.]

### Card 2
- **Label:** `DATA ANALYSIS`
- **Title (H3):** `Florida Traffic Incident Analysis`
- **Body:** `A data pipeline analyzing statewide traffic incidents to surface where Florida's roads are most dangerous — and where crashes cluster.`
- **Metric line:** `Key finding: District 5 leads in fatalities and serious injuries; District 4 in crash count`
- **Link:** `View on GitHub →` [→ https://github.com/jonathan-norton/traffic-incident-analysis-pipeline]

### Card 3
- **Label:** `MACHINE LEARNING`
- **Title (H3):** `Handwritten Digit Classifier`
- **Body:** `A convolutional neural network that reads handwritten digits — the classic computer vision problem, built and trained from the ground up.`
- **Metric line:** `99.05% test accuracy`
- **Link:** `View on GitHub →` [→ https://github.com/jonathan-norton/handwritten-digit-classifier]

---

## Section 3 — About

**Section heading (H2):** `About`

**Body copy:**

`I'm a Computer Science senior at Florida State University, on track to graduate in Spring 2027. This past summer I was an IT Project Management Intern on the AI Execution Team at Raymond James in St. Petersburg, where I saw how AI actually ships inside a Fortune 500 firm.`

`Before that: internships at Verizon and Burns & McDonnell, and robotics/ML research at the FAMU-FSU Stride Lab, where I got hands-on with Keras, TensorFlow, and Scikit-Learn. I transferred to FSU after earning my AA at Tallahassee State College.`

`Outside the classroom I serve as Historian of the Theta Eta Chapter of Kappa Alpha Psi and as a Senator for the FAMU-FSU Chapter of the National Society of Black Engineers.`

`I'm Igbo, Nigerian by heritage, raised in Tallahassee. We have a saying: Naija no dey carry last. We don't finish last. That phrase drives me every day to make myself and my family proud.`

`Beyond the code: I'm developing a cooking content page, and you'll otherwise find me on a soccer pitch, in the gym, or a few episodes deep in a Crunchyroll binge.`

**[Portrait slot: use the straight-on suit headshot (IMG_2287), rounded frame per --radius-image. Alt text: "Jonathan Norton". Decision #12 in DESIGN.md.]**
[The live portrait renders with an empty image source. This is an asset or build problem, not a copy problem: confirm the file was committed and that the path in the component matches its location.]

---

## Section 4 — Resume anchor

[Not a full section — the Resume button in nav and hero links to the resume PDF (opens in new tab). No copy needed beyond button labels.]

[Filename mismatch: this file previously said `/resume.pdf`, but the live nav and hero both point to `/JonathanNorton_Resume.pdf`. Pick one and make the repo match. Whichever you pick, re-upload the PDF after the LaTeX header fixes land, since the deployed copy is the old version with the broken link block.]

---

## Section 5 — Contact / Footer CTA

**[Crimson band — the one big crimson moment per DESIGN.md]**

**Closing line (H2, Fraunces, cream):** `Let's talk.`

**Subline:** `Open to junior software engineering, technical PM, and data roles. The fastest way to reach me:`

**Buttons (inverted secondary style):**
- `Email me` [→ mailto:jonathannorton754@gmail.com]
- `LinkedIn` [→ https://www.linkedin.com/in/jonathanmnorton/]
- `GitHub` [→ https://github.com/jonathan-norton]

**Footer small print:** `© 2026 Jonathan Norton · Tallahassee / Tampa, FL · Go Noles`

---

## Copy rules

1. No exclamation points anywhere on the site.
2. Numbers stay numerals (99.05%, not "over 99 percent").
3. Sentence case for headings except card labels (uppercase per DESIGN.md text-label token).
4. Never call the projects "simple," "basic," or "just a…" — they stand on their results.
5. Describe what exists, not what is planned. No published dates for unshipped work.
