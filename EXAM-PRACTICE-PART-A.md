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

### Set 1
1. **Verification** / **Validation**
2. **Waterfall** / **Spiral**
3. **Product backlog** / **Sprint backlog**
4. **type of user** / **reason** (benefit)
5. **«include»** / **«extend»**
6. **Aggregation** / **Composition**
7. **Statement** / **Decision (branch)**
8. **Test-Driven Development (TDD)**
9. **Work-In-Progress (WIP)** / **bottlenecks**
10. **CMMI (Capability Maturity Model Integration)**

### Set 2
1. **Corrective** / **Adaptive**
2. **Process** / **Use case (scenario)**
3. **Product Owner** / **Scrum Master**
4. **Boundary (View)** / **Entity (Model)**
5. **Equivalence partitioning** / **Boundary value analysis**
6. **inspection (review)**
7. **Delivery** / **Deployment**
8. **DevOps**
9. **Delivery** / **Commitment**
10. **Defined (Level 3)** / **Managed (Level 2)**

### Set 3
1. **Prototyping**
2. **comprehensive documentation** / **following a plan**
3. **state (machine)** / **guard condition**
4. **sequence** / **communication**
5. **Velocity**
6. **normal** / **abnormal**
7. **Respect** / **Courage**
8. **Pair programming** / **spike**
9. **Infrastructure as Code (IaC)**
10. **stubs** / **drivers**

---

### Scoring guide
- **9–10 / 10:** Exam-ready on terminology. Shift effort to Part B practice.
- **6–8 / 10:** Solid; re-drill the Key Terms table in `EXAM-STUDY-GUIDE.md` for the ones you missed.
- **≤5 / 10:** Re-read the relevant topic section in the study guide, then redo the set a day later.
