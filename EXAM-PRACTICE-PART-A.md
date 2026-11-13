# CSIT314 — Part A Practice: Fill-in-the-Blank

**Format reminder:** Part A = 9 questions, 10 blanks, 10 marks. Each blank is one term or short phrase.
Below are **three full practice sets (30 blanks total)** mirroring the real style, followed by a complete **answer key**. Cover the answer key and attempt each set under ~10 minutes.

---

## Practice Set 1

**Q1.** The two halves of V&V are ______ ("are we building the product right?") and ______ ("are we building the right product?").

**Q2.** A ______ model is sequential — each phase must be complete and correct before the next begins — whereas a ______ model is risk-driven and iterative, suited to large, complex projects.

**Q3.** In Scrum, the prioritised master list of everything that might be needed is the ______, while the subset chosen for the current iteration is the ______.

**Q4.** A user story follows the template: "As a ______, I want a goal so that a ______."

**Q5.** In a UML use case diagram, a ______ relationship models compulsory reused behaviour, and an ______ relationship models optional/conditional behaviour.

**Q6.** The two UML class relationships that both mean "part-of" are ______ (parts can exist independently) and ______ (parts are destroyed with the whole).

**Q7.** The white-box coverage criterion where every statement runs at least once is ______ coverage; the stronger one requiring every branch outcome is ______ coverage.

**Q8.** Writing an automated test before the code it verifies is the practice called ______.

**Q9.** In Kanban, the maximum number of cards allowed in a column is the ______ limit, and it is mainly used to reveal ______.

**Q10.** The process-maturity framework with five levels developed by the SEI is ______.

---

## Practice Set 2

**Q1.** Maintenance that fixes bugs is ______ maintenance; maintenance that adapts software to a changed environment is ______ maintenance.

**Q2.** In the 4+1 View Model, the view describing runtime behaviour and concurrency is the ______ view, and the "+1" view that ties the others together is the ______ view.

**Q3.** The three Scrum roles are the ______, the ______, and the Team.

**Q4.** In B-C-E design, the layer the actor interacts with is the ______ layer, and the layer that maps directly to database tables is the ______ layer.

**Q5.** A black-box technique that divides inputs into classes and tests one value per class is ______; the complementary technique that tests values at the edges of ranges is ______.

**Q6.** Static verification performed by people reviewing artefacts without executing them is called a software ______.

**Q7.** The CI pipeline step where every change is automatically built and tested in a production-like staging environment (but deployed to production manually) is Continuous ______; automatically deploying to production on passing tests is Continuous ______.

**Q8.** The practice of unifying development and IT operations teams, summarised as "operate what you build," is ______.

**Q9.** In Kanban, lead time equals the ______ point minus the ______ point.

**Q10.** CMMI maturity level where processes are standardised and deployed organisation-wide is the ______ level; the level where they are merely managed at project level is the ______ level.

---

## Practice Set 3

**Q1.** The software process model best suited to a project with unclear requirements and a UI focus, where a quick working model is built and then discarded, is ______.

**Q2.** The Agile Manifesto values working software over ______, and responding to change over ______.

**Q3.** A UML ______ diagram shows the states one object passes through in response to events; an optional ______ on a transition decides whether it fires.

**Q4.** A UML ______ diagram shows object messages ordered by time for a single use case, while a ______ diagram shows the same information but emphasises links between objects.

**Q5.** The Scrum metric for how much work is completed per iteration is ______.

**Q6.** The two kinds of unit test case are tests of ______ operation and tests using ______ inputs that must not crash the component.

**Q7.** Three XP values are Communication, Simplicity, and Feedback; the remaining two are ______ and ______.

**Q8.** The XP practice where two programmers work jointly at one keyboard is ______, and the throw-away program written to explore a risky problem is a ______.

**Q9.** Treating the whole IT infrastructure as scripted, version-controlled code — a prerequisite for CI/CD — is ______.

**Q10.** In integration testing, a top-down approach requires writing ______ for lower layers, whereas a bottom-up approach requires writing test ______.

---

## Answer Key
*(Each answer cites the source slide so you can revise the concept. "T5 p.3" = UOW 2016 Topic 5.pdf, page 3.)*

### Set 1
1. **Verification** / **Validation** — *T5 p.3; T1 p.28*
2. **Waterfall** / **Spiral** — *T2 pp.4–6; pp.34–35*
3. **Product backlog** / **Sprint backlog** — *T2 pp.14,16,22*
4. **type of user** / **reason** (benefit) — *T2 p.15*
5. **«include»** / **«extend»** — *T3 pp.13–14*
6. **Aggregation** / **Composition** — *T3 pp.19–21*
7. **Statement** / **Decision (branch)** — *T5 pp.21–24*
8. **Test-Driven Development (TDD)** — *T5 pp.30–32*
9. **Work-In-Progress (WIP)** / **bottlenecks** — *T8 pp.8–9*
10. **CMMI (Capability Maturity Model Integration)** — *T10 p.7*

### Set 2
1. **Corrective** / **Adaptive** — *T1 p.31*
2. **Process** / **Use case (scenario)** — *T3 pp.6–11; T4*
3. **Product Owner** / **Scrum Master** — *T2 pp.16–17,20*
4. **Boundary (View)** / **Entity (Model)** — *T4 pp.14–21*
5. **Equivalence partitioning** / **Boundary value analysis** — *T5 pp.25–27*
6. **inspection (review)** — *T5 pp.5–8*
7. **Delivery** / **Deployment** — *T6 pp.32–35*
8. **DevOps** — *T7 p.10*
9. **Delivery** / **Commitment** — *T8 pp.8–9*
10. **Defined (Level 3)** / **Managed (Level 2)** — *T10 pp.9–12*

### Set 3
1. **Prototyping** — *T2 pp.29–33*
2. **comprehensive documentation** / **following a plan** — *T8 (Agile vs Waterfall table); T2 pp.6–10*
3. **state (machine)** / **guard condition** — *T3 pp.28–30*
4. **sequence** / **communication** — *T4 pp.4–11, 24, 27*
5. **Velocity** — *T2 p.22; T8 (Kanban vs Scrum) p.13*
6. **normal** / **abnormal** — *T5 pp.16–19*
7. **Respect** / **Courage** — *T8 pp.16–21*
8. **Pair programming** / **spike** — *T8 pp.22–27, 29*
9. **Infrastructure as Code (IaC)** — *T6 pp.26–27*
10. **stubs** / **drivers** — *T5 p.28; T6 (integration) pp.4–6*

> **Legend:** T1–T12 = "UOW 2016 Topic 1–12.pdf". Full file↔page lookup is in `EXAM-STUDY-GUIDE.md` → *Sources & Citations*.

---

### Scoring guide
- **9–10 / 10:** Exam-ready on terminology. Shift effort to Part B practice.
- **6–8 / 10:** Solid; re-drill the Key Terms table in `EXAM-STUDY-GUIDE.md` for the ones you missed.
- **≤5 / 10:** Re-read the relevant topic section in the study guide, then redo the set a day later.
