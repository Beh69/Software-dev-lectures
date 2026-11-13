# CSIT314 Software Development Methodologies — Exam Study Guide

**Exam format:** 16 questions, 50 marks total.
- **Part A — 9 fill-in-the-blank questions, 10 blanks, 10 marks.** Each blank = one term or short phrase. (See the "Key Terms" drill list at the end — these are what you memorise.)
- **Part B — 7 questions on a project scenario, 40 marks.** You apply the concepts: write user stories, draw/describe UML, design a testing approach, write test cases, explain practices. Practise *producing* artefacts, not just defining terms.

This guide is built from the lecture slides (Topics 1–12) and labs in this repo. It is organised by the five topic clusters named on your exam sheet.

---

## 1. Software Processes
*(Topic 1 — lifecycle; Topic 2 — process models; Topic 9 — RUP)*

### Software Development Lifecycle (SDLC) activities
Memorise this sequence — it underpins almost everything:

1. **Planning** – business value, feasibility, work plan, staffing, estimation, risk.
2. **Requirements analysis** – *what* services + constraints; stakeholders & expectations; use cases are the major part of a requirements spec.
3. **Design** – *how* to build it: architecture → subsystem → detailed → persistent data → GUI design.
4. **Implementation** – construction (coding) + installation/deployment.
5. **Verification & Validation (V&V)** – conform to spec (right way) + do what user needs. Testing is the main V&V activity.
6. **Maintenance & evolution** – changes are inevitable.

**Three kinds of maintenance** (common fill-in-the-blank):
- **Adaptive** – react to a changed *environment*.
- **Corrective** – fix *errors/bugs*.
- **Perfective** – change *functionality* to meet new needs.

> Key cost idea: the cost of fixing an error rises the later it is found in the lifecycle.

### Process models — when each suits a project

| Model | Core idea | Suits a project when… |
|---|---|---|
| **Waterfall** | Sequential; finish & verify each phase before the next. | Requirements are stable & well understood; short, small, low-uncertainty; mature technology. |
| **Prototyping** | Build a quick throw-away working model, get user feedback, refine, then rebuild properly. | Requirements unclear; UI/HCI-heavy; need early user feedback. |
| **Incremental & Iterative** | Prioritise requirements; deliver in small increments over repeated cycles. | Want early value & feedback, reduced change cost, lower failure risk. |
| **Spiral** | Waterfall + iteration, **risk-driven**; each loop does plan–risk analysis–prototype–evaluate. | Large, complex, high-uncertainty projects (e.g. games, military). |
| **RUP** | Iterative, use-case driven, architecture-centric. | Larger structured projects wanting phase discipline + iteration. |

### Agile (the "why")
1990s frustration with waterfall: big gap between requirements and delivery; requirements changed before the product shipped.
**Agile values (Manifesto):** *Individuals & interactions* over process/tools; *working software* over documentation; *customer collaboration* over contract negotiation; *responding to change* over following a plan.
Key traits: adaptive planning, iterative/incremental, early & continuous delivery, self-organising cross-functional teams, continuous improvement.

### Scrum (know the roles, events, artefacts)
- **Roles:** **Product Owner** (defines/prioritises features, decides release content), **Scrum Master** (enables the team, enacts Scrum), **Team** (self-organising, cross-functional).
- **Events/steps:** Sprint Planning → Daily Scrum (15 min) → Development Work → Sprint Review → Sprint Retrospective.
- **Artefacts/terms:** **Sprint** (one iteration), **Time-box** (fixed sprint length), **Product backlog** (prioritised master list, owned by PO), **Sprint backlog** (items chosen for the sprint + plan), **Burndown chart** (remaining work), **User story**, **Velocity** (work done per iteration).

### Scrum vs Kanban vs XP (quick differences)
- **Scrum:** fixed-length sprints; release at sprint end; roles PO/SM/Team; metric = **velocity**; no changes mid-sprint.
- **Kanban:** continuous flow; continuous delivery; no required roles; metrics = **lead time, cycle time, WIP**; change any time.
- **XP:** short iterations (1–2 weeks), very flexible within iterations, customer prioritises features; engineering-focused (TDD, pair programming).

**RUP essentials:** 6 best practices (develop iteratively, manage requirements, use components, model visually, verify quality, control changes). Phases on the time axis: **Inception → Elaboration → Construction → Transition**. Building blocks: Roles (who), Tasks/Activities (how), Work Products/Artifacts (what), Workflows (when), Disciplines (container).

---

## 2. Requirements & Design
*(Topic 3 — static UML; Topic 4 — dynamic UML, B-C-E; Topic 2 — user stories)*

### User stories
Template: **"As a `<type of user>`, I want `<goal>` so that `<reason>`."**
Short, informal, user-perspective. Contrast with **use cases** (more detailed, structured, standard format, broader scope).
> *Part B tip:* given a scenario (e.g. the insurance claims system in Lab 1), be ready to write several well-formed user stories.

### UML use case diagrams
- **Actor** = a user or external system. **Use case** = a typical interaction between actor and system; captures functional *and* non-functional requirements from the user's point of view.
- **Boundary box** = scope of the system. Actor↔use case can be 1:1, 1:m, m:m.
- **Relationships:**
  - **«include»** – *compulsory* reused sub-behaviour.
  - **«extend»** – *optional* / conditional behaviour (alternative course under certain conditions).

### The "4+1" View Model (very likely a fill-in-the-blank)
Architecture described through 4 views + 1:
- **Logical view** – functionality to end-users (class, object, package, state, composite structure diagrams). *Conceptual.*
- **Process view** – runtime behaviour, concurrency, communication (sequence, communication, activity diagrams). *Conceptual.*
- **Development view** – code organisation (component diagram). *Physical.*
- **Physical view** – deployment onto hardware (deployment diagram). *Physical.*
- **+1 = Use case view (scenarios)** – ties the other four together; the user requirements.

### UML class diagrams
Class box: **name / attributes / methods**. Visibility prefixes:
- `+` public, `-` private, `#` protected, `{read only}` constant, underline = static.
- Attribute: `name: Type`; Method: `name(): ReturnType`.

**Class relationships (memorise the four + their meaning):**
- **Aggregation** – "is-a-part-of"; parts *can* exist independently (department is part of university).
- **Composition** – "is composed of"; parts *cannot* exist independently (destroy house → destroy its walls).
- **Inheritance / Generalization** – "is-a"; subclass specialises superclass, inherits its properties.
- **Association** – generic "has-a / uses / communicates with" (the default/everything-else).

### State (machine) diagrams
Show the states one object passes through over its life in response to **events (triggers)**.
Transition parts: **source state → [guard condition] event / action → target state.** Guard and action are optional.
> *Part B tip:* Lab 3 practised these for a watch and a landline phone — be able to draw states + transitions for a described device.

### Sequence & communication diagrams (Process view)
- **Sequence diagram:** objects along X-axis, time down Y-axis; models messages for *one* use case. Elements: object/lifeline (`name:Class`), the **X** marks object deletion, **focus of control** (activation bar), **messages** (solid filled arrow = call; dashed open arrow = return). The initiating object sits on the left.
- **Communication diagram:** same information, different style — emphasises *links/relationships* between objects rather than time order.

### B-C-E design (a.k.a. MVC)
- **Boundary (View)** – UI; the only classes actors interact with (screens, menus, dialogs).
- **Control** – one controller per use case; coordinates messaging, holds application/business rules ("the glue"), implements the sequence diagram.
- **Entity (Model)** – business-domain data; maps to DB tables; responsible for persistence.

> *Part B modelling flow:* Use case (what) → class diagram (structure) → sequence diagram (behaviour of one use case) → B-C-E/MVC design → code. State diagrams add per-object dynamics.

---

## 3. Quality & Testing
*(Topic 5 — V&V, static/dynamic, TDD)*

### Verification vs Validation (classic fill-in-the-blank)
- **Verification:** "Are we building the product **right**?" → conforms to specification.
- **Validation:** "Are we building the **right** product?" → does what the user really needs.
- V&V is a whole-lifecycle process. Two objectives: find/fix defects; assess operational usability.

### Static vs Dynamic techniques
- **Static verification = software inspections/reviews.** No execution; can be done *before* implementation and on any artefact (requirements, design, config, test data). Catches defects *early* (cheaper), can assess standards/portability/maintainability, and finds things hard to test (security, exception handling).
- **Dynamic verification = testing.** Execute the system with test data and observe behaviour. (Inspections and testing are **complementary**, not competing.)

### Test case design — standard matrix (useful for Part B "write test cases")
Columns: **Case ID, Scenario, Steps, Prerequisites, Test Data, Expected Results, Actual Results, Status (Pass/Fail).**
Each test case: uniquely identified, states its purpose, lists expected results.

### Levels & who tests
- **Unit testing** – individual functions/methods/classes in isolation; should be **automated** (JUnit, cppUnit, PyUnit…). Two case types: normal operation, and abnormal inputs (must not crash).
- **Integration testing** – test interactions between integrated components; focus on **interfaces**, not internals. Strategies: **top-down** (needs stubs), **bottom-up** (needs test drivers), **sandwich**.
- **System testing** – whole system + environment: **function** testing (functional reqs), **performance** testing (non-functional: reliability, availability), **acceptance** testing (validation before handover — client satisfaction).
- Performed by: the developer, an independent test group, and the customer.

### White-box vs Black-box
- **White-box** – examines internal code/control structure. Coverage levels (increasing strength): **statement → decision/branch → condition → path**.
- **Black-box** – no knowledge of internals; derive tests from inputs.
  - **Random/uniform** – treat all inputs as equal; avoids bias but can't test everything.
  - **Systematic/non-uniform** – **Equivalence Partitioning** (split inputs into classes, test one value per class) + **Boundary Value Analysis** (test values at the edges/range limits).

### Test-Driven Development (TDD)
Write the test **before** the code; passing the test drives development. Steps:
1. Identify a small new piece of functionality.
2. Write an automated test for it.
3. Run all tests — the new one **fails** (nothing implemented yet).
4. Implement the functionality; re-run tests.
5. When all pass, move to the next chunk.

**Benefits:** code coverage (every segment has a test), regression testing (changes don't break old code), simplified debugging (failure localised to the new code). *(Lab 5 did this with a JUnit Calculator — adding `multiply` test-first.)*

---

## 4. Development Practices
*(Topic 8 — XP, Kanban; Topic 6 — CI/CD; Topic 7 — DevOps)*

### Extreme Programming (XP)
**5 values:** **Communication, Simplicity, Feedback, Respect, Courage.**
**12 practices** (grouped):
- *Feedback:* Test-Driven Development, The Planning Game, On-site Customer, Pair Programming.
- *Continuous process:* Continuous Integration, Refactoring, Small Releases.
- *Shared understanding:* Simple Design, Collective Code Ownership, System Metaphor, Coding Standards.
- *Programmer welfare:* 40-Hour Week (sustainable pace).
Participants: Customer, Developers, Tracker, Coach. A **spike** = a simple throw-away program to explore/reduce risk. Acceptance tests come from user stories and are black-box system tests.

### Kanban
Japanese for "signboard"; from Toyota manufacturing, adapted to software (2010). Real-time communication, full transparency, visual progress.
**5 board components:** **Visual signals (cards), Columns (workflow stages), Work-In-Progress (WIP) limits, Commitment point, Delivery point.**
- **WIP limit** – max cards per column; exposes **bottlenecks**.
- **Lead time = Delivery point − Commitment point.**

### Builds (CI foundation)
- **Private build** – developer's local machine, manual, fast, checks it compiles before commit.
- **Integration build** – on a dedicated build server, triggered by changes / nightly, from the trunk.
- **Release build** – by the release manager, to production, full test suite, slow.

### Continuous Integration (CI)
Developers integrate work **frequently** (several times/day); each integration is verified by an **automated build** (compile + run automated tests).
**9 practices (Fowler):** single source repository; automate the build; make the build self-testing; everyone commits to mainline every day; every commit builds mainline on an integration server; keep the build fast; test in a clone of production; make it easy to get the latest executable; everyone can see what's happening.
**Benefits:** productivity (short feedback), quality (frequent testing finds bugs), reduced risk. **Infrastructure as Code (IaC)** = treat infrastructure like software (scripted setup) — a prerequisite for CI/CD.

### CI → CD → Continuous Deployment (know the escalation)
- **Continuous Delivery** – every change is automatically built & tested in a **staging** environment (production-like); deployment to production is still **manual**.
- **Continuous Deployment** – one step further: if tests pass, the change is deployed to production **automatically**, often several times a day.

### DevOps
Unifies **Dev**elopment and IT **Op**erations — removes the "wall of confusion" (different objectives, perspectives, environments, requirements). Teams merge; "**operate what you build**" (Netflix case study). Lifecycle: plan/code/build → test → integrate/release → deploy/operate → monitor.
**DevOps vs Agile:** DevOps spans Dev + Ops (Agile = Dev only); DevOps weights timeliness **and** quality equally; feedback comes from monitoring tools (Agile: from customers).
**Tool categories:** source repo (Git), build server (Jenkins), configuration management (Puppet/Chef), virtual infrastructure (AWS/Azure), test automation (Selenium).

---

## 5. Process Improvement — CMMI
*(Topic 10)*

**CMMI = Capability Maturity Model Integration** (SEI / Carnegie Mellon, US DoD). A framework of best practices to improve product quality and development efficiency; aligns process improvement with business objectives.

**5 Maturity Levels (the most likely fill-in-the-blank set):**
1. **Initial/Performed** – unpredictable, poorly controlled, reactive, ad hoc. (XP cited as an example of ad hoc.)
2. **Managed** – project level; processes planned, documented, monitored, controlled; skilled people & resources.
3. **Defined** – organisation level; standard processes deployed org-wide, tailored per guidelines.
4. **Quantitatively Managed** – processes measured and controlled using quantitative/statistical data.
5. **Optimizing** – focus on continuous process improvement.

**Process-area groups:** Project Management, Process Management, Engineering, Support.
Progressing one level up typically takes ~2–3 years; better suited to large organisations.

*(Bonus — Topic 11, Data-driven development, if examined: lifecycle = model requirements → data collection → cleaning → labelling → feature engineering → model training → evaluation → deployment → monitoring. Evaluation metrics: precision, recall, F-measure. Lab 7 used Weka + the diabetes dataset with J48 decision tree.)*

---

## Part A — Key Terms Drill (cover the right column, recall from the left)

| Clue | Term |
|---|---|
| "Are we building the product right?" | **Verification** |
| "Are we building the right product?" | **Validation** |
| Static V&V with no execution | **Software inspection / review** |
| Fix bugs in existing software | **Corrective maintenance** |
| Adapt to a changed environment | **Adaptive maintenance** |
| Change functionality for new needs | **Perfective maintenance** |
| Risk-driven iterative process model | **Spiral model** |
| Sequential "finish-a-phase-first" model | **Waterfall model** |
| Throw-away quick working model for feedback | **Prototyping** |
| Prioritised master list of everything needed | **Product backlog** |
| Fixed length of one Scrum iteration | **Time-box** / **Sprint** |
| Chart of remaining work in a sprint | **Burndown chart** |
| Amount of work done per iteration | **Velocity** |
| "As a <user>, I want <goal> so that <reason>" | **User story** |
| Compulsory reused use-case behaviour | **«include»** |
| Optional/conditional use-case behaviour | **«extend»** |
| "is-a-part-of", parts can exist alone | **Aggregation** |
| "is composed of", parts die with the whole | **Composition** |
| "is-a" specialisation | **Inheritance / Generalization** |
| Default "uses / has-a" relationship | **Association** |
| UML diagram of object messages over time | **Sequence diagram** |
| B-C-E layer = UI the actor touches | **Boundary (View)** |
| B-C-E layer holding business rules per use case | **Control** |
| B-C-E layer mapping to DB tables | **Entity (Model)** |
| 4+1 view for runtime behaviour/concurrency | **Process view** |
| The "+1" view in the 4+1 model | **Use case / scenario view** |
| Testing without knowing internals | **Black-box testing** |
| Testing the internal code structure | **White-box testing** |
| Split inputs into classes, test one each | **Equivalence partitioning** |
| Test at the edges of input ranges | **Boundary value analysis** |
| Write tests before code | **Test-Driven Development (TDD)** |
| Max cards allowed in a Kanban column | **WIP limit** |
| Delivery point − commitment point | **Lead time** |
| XP practice: two developers, one keyboard | **Pair programming** |
| Integrate frequently + automated build | **Continuous Integration** |
| Auto-build/test to staging, deploy manually | **Continuous Delivery** |
| Auto-deploy to production on passing tests | **Continuous Deployment** |
| Unify Dev + Ops, "operate what you build" | **DevOps** |
| Infrastructure managed as scripted code | **Infrastructure as Code** |
| 5-level process maturity framework | **CMMI** |
| CMMI level: org-wide standard processes | **Defined (Level 3)** |
| CMMI level: project-level controlled processes | **Managed (Level 2)** |

---

## Part B — How to answer scenario questions
Part B gives a project scenario (like the **Sure Thing Insurance** online-claims system in Lab 1). Expect to:
1. **Write user stories** — use the "As a… I want… so that…" template; cover different actors (policyholder, assessor, investigator).
2. **Draw/describe a use case diagram** — actors + use cases + «include»/«extend».
3. **Produce a class diagram** — classes, attributes, methods, and the right relationship (aggregation/composition/inheritance/association).
4. **Draw a sequence (or state) diagram** — one use case's message flow, or an object's state transitions.
5. **Recommend a process/practice** — e.g. "which model suits this project and why" (link to requirements stability, size, risk); or how CI/CD/DevOps/XP would support the team.
6. **Design a testing approach** — pick levels (unit→integration→system→acceptance), white/black-box, and justify.
7. **Write concrete test cases** — use the 8-column matrix with real test data and expected results.

**Exam strategy:** Part A rewards precise vocabulary (memorise the drill table). Part B rewards *applying* a concept correctly to the given scenario and *justifying* choices — always tie your answer back to the scenario's facts.
