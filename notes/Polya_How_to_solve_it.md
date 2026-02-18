# Pólya — *How to Solve It* (High-level summary)

Note: The PDF in `books/` is scanned; this document is a **paraphrased** high-level summary grounded in OCR of that scan (not a transcription).

## Canonical Problem-Solving Form (Pólya)

1) **Understand the problem**
- Restate it in your own words.
- Identify **unknowns**, **data**, and **constraints**.
- Clarify what “a solution” must look like.

2) **Devise a plan**
- Choose a strategy: analogy, decomposition, transformation, working backward, invariants, etc.

3) **Carry out the plan**
- Execute carefully.
- Track assumptions.
- Validate each step.

4) **Look back**
- Check the result.
- Test edge cases.
- Extract the key idea.
- Generalize and reuse.

**Memory hook:** **U–P–D–R** = **Understand → Plan → Do → Review**

### Pólya’s “main divisions” idea (why the 4 phases matter)

Pólya frames problem solving as repeatedly **shifting your point of view** as your understanding improves. The four phases are a practical way to organize that shifting.

He also warns that skipping phases is a common failure mode:
- Don’t start detailed work before you understand what’s being asked.
- Don’t grind computations before you’ve identified a main connection / rough plan.
- Don’t finish without checking and reflecting; you lose the chance to catch mistakes and extract reusable method.

### Pólya’s “main questions” (paraphrased prompts to drive each phase)

These are the kinds of questions Pólya repeatedly recommends (especially as a teacher’s method: guide by questions until the student can self-question).

**1) Understand the problem**
- What is the **unknown**?
- What are the **data**?
- What is the **condition** (the link between data and unknown)?
- Can you restate the problem clearly?
- Should you draw a figure / introduce notation?
- Is the condition even satisfiable / is the problem well-posed? (Aim for a provisional “yes/no/guess,” not a final proof yet.)

**2) Devise a plan**
- Do you know a related problem? Have you seen something like this before?
- Can you restate the goal in a more usable form (e.g., “look at the unknown” from a different angle)?
- Could working backwards help?
- Would an auxiliary element or auxiliary problem create a bridge?
- Can you separate the condition into parts and recombine?

**3) Carry out the plan**
- Can you justify each step as you go?
- Did you use all the data and the full condition?

**4) Look back**
- Can you check the result?
- Can you derive it differently (a second route)?
- Can you use the result for another problem / generalize it?

### Two common problem types (a useful Pólya lens)

Pólya often distinguishes between:
- **Problems to find** (construct/compute an object/quantity).
- **Problems to prove** (establish a statement’s truth).

High-level implication: for “find” problems, representation + construction + checking feasibility is central; for “prove” problems, choosing the right proof shape (direct/contradiction/induction/etc.) and tracking logical dependencies is central.

### “Questions & suggestions” toolbox (fill-the-gap heuristics)

When you’re stuck in any phase, cycle through a small repertoire of prompts. These are intentionally generic; you adapt them to the domain.

- **Related problem:** Do you know a similar problem? Can you recall its method and map it over?
- **Specialize / simplify:** What happens in a simpler case (smaller numbers, symmetric case, 1D/2D version)?
- **Generalize:** Is there a more general statement that is easier to see (then specialize back)?
- **Introduce notation:** Name the unknown and the key quantities; write down what the condition really says.
- **Draw a figure / make a table:** Externalize relationships.
- **Look at the unknown:** What would it mean to “have” the unknown? What properties must it satisfy?
- **Work backwards:** If the goal were achieved, what would have been true one step earlier?
- **Decompose and recombine:** Split the condition into parts; solve partial constraints; recombine.
- **Auxiliary elements:** Add an extra line/point/variable/function; pose an auxiliary problem that bridges data → unknown.
- **Contradiction / contrapositive:** If the statement were false, what would that force? Where does it break?
- **Induction / iteration:** Does the problem have a natural “next step” structure?
- **Symmetry / normalization:** Can you relabel, center, scale, or pick coordinates to simplify?
- **Check feasibility:** Is it even possible to satisfy the condition (at least plausibly)?

**Mini mnemonic:** **RAGS** = **R**elated problem, **A**uxiliary problem/element, **G**eneralize, **S**pecialize.

### How “bright ideas” happen (practical takeaway)

Pólya’s framing is that the key idea for a plan can appear suddenly, but it is often *prepared* by earlier work: understanding the statement fluently, making connections, and trying small transformations.

---

## Concrete examples (from the book, paraphrased)

These are **paraphrases** of examples used in the book (OCR’d from the scanned PDF). I’m focusing on what each example is meant to *teach* in terms of questions and heuristics.

### Example A — “Box diagonal” (introducing unknown/data/condition)

**Problem (paraphrased):** Given the length, width, and height of a rectangular box (rectangular parallelepiped), find its space diagonal.

**How it illustrates Pólya:**
- **Understand:** explicitly name the unknown (diagonal length), the data (three edges), and the condition (diagonal determined by those dimensions).
- **Plan:** connect to a known related problem (Pythagoras). Reduce the 3D question to 2D right triangles.
- **Do:** apply Pythagoras twice (first on the base rectangle diagonal, then with height).
- **Look back:** check plausibility (dimension/scale; if height goes to 0, reduces to rectangle diagonal).

### Example B — Construction: “Inscribe a square in a triangle” (drop conditions, then recover)

**Problem (paraphrased):** Inscribe a square in a given triangle so that two vertices lie on the base, and the other two lie on the other sides (one on each side).

**How it illustrates Pólya:**
- **Understand:** keep returning to “unknown/data/condition,” and force a clear drawing.
- **Heuristic move:** if stuck, **keep only part of the condition** (e.g., place a square with two vertices on the base) and explore what remains free.
- **Plan idea:** vary the “partial” square and observe how the remaining vertex moves; this suggests a locus/constraint that can be used to satisfy the full condition.

### Example C — Proof: “Angles in different planes” (use a related theorem + auxiliary element)

**Problem (paraphrased):** Two angles lie in different planes. Each side of one angle is parallel to the corresponding side of the other, and the corresponding sides have equal length. Prove the two angles are equal.

**How it illustrates Pólya:**
- **Understand:** restate the hypothesis in your own notation and draw a careful figure.
- **Plan:** recall a **related theorem**: corresponding angles in congruent triangles are equal.
- **Auxiliary element:** add segments to complete triangles (connect the endpoints) so the “related theorem” becomes applicable.
- **Do:** prove triangles are congruent (via side equalities and parallelism setup), then conclude the angle equality.

### Example D — Rate problem: “Water into a cone” (express, then differentiate)

**Problem (paraphrased):** Water flows into a right circular cone (vertex down). Given base radius $a$, height $b$, inflow rate $r$, and current water depth $y$, find the rate of change $dy/dt$ at that moment (with a later numerical substitution).

**How it illustrates Pólya:**
- **Understand:** identify what changes (the depth $y$ as a function of time).
- **Plan:** express the desired rate using a definition: $dy/dt$.
- **Key connection:** relate inflow to volume: $dV/dt = r$, and connect $V$ to $y$ using similar triangles (radius at depth $y$ is proportional to $y$).
- **Do:** compute $V(y)$, differentiate, and solve
	$$\frac{dy}{dt} = \frac{dV/dt}{dV/dy} = \frac{r}{dV/dy}.$$
- **Look back:** only after the symbolic expression is correct, substitute numbers.

### Example E — “Related problem” as a plan-generator (box diagonal, the teacher’s prompts)

**Problem context (paraphrased):** Same “box diagonal” setting as Example A, but the emphasis is on *getting* the plan.

**What it teaches:**
- Ask: “Do you know a related problem with a similar unknown?” (length of a segment).
- Pull in a known solved template (right-triangle side length).
- Create the related structure you need: introduce a right triangle where the unknown diagonal is the hypotenuse.

### Example F — Carrying out: introduce an auxiliary unknown and eliminate it (box diagonal)

**Problem context (paraphrased):** Continue the box-diagonal solution.

**What it teaches:**
- Introduce an auxiliary unknown (e.g., face diagonal) so the plan becomes concrete.
- Compute step-by-step (Pythagoras on the base face, then again in a perpendicular face).
- Distinguish “seeing” a step vs being able to justify it (especially when solid-geometry facts are new).

### Example G — Looking back: test your formula by symmetry, limits, scaling, and units

**Problem context (paraphrased):** After obtaining $x = \sqrt{a^2+b^2+c^2}$ for the box diagonal.

**What it teaches:**
- **Symmetry:** swapping $a,b,c$ shouldn’t change the result.
- **Limiting case:** if one dimension goes to $0$, the formula should reduce to the rectangle diagonal.
- **Monotonicity:** increasing any dimension should increase $x$.
- **Scaling / dimension check:** scaling all lengths by $k$ scales $x$ by $k$; units must be consistent.

### Example H — Auxiliary problem by substitution (quartic → quadratic)

**Problem (paraphrased):** Solve an equation like $x^4 - 13x^2 + 36 = 0$.

**What it teaches:**
- Introduce an auxiliary unknown $y=x^2$ to get a simpler related problem (a quadratic in $y$).
- Use the auxiliary result, then map back to the original unknown.
- More generally: look for “convertible reductions” (equivalent rewrites) that make the next step obvious.

### Example I — Look-back reinterpretation: frustum lateral area as “perimeter × slant height”

**Problem (paraphrased):** Find the lateral surface area of a right circular conical frustum given lower radius $R$, upper radius $r$, and altitude $h$.

**What it teaches:**
- After a long derivation, look for a *meaningful factorization*.
- Recognize the slant height $\sqrt{(R-r)^2+h^2}$ and the “mid-perimeter” $\pi(R+r)$.
- Read the result as: **Area = (perimeter of mid-section) × (slant height)**.
- Use analogy: it mirrors the trapezoid rule **Area = (middle line) × (altitude)**, suggesting a shorter proof.

### Example J — Construction via loci intersection (given side, altitude, opposite angle)

**Problem (paraphrased):** Construct a triangle given one side, the altitude to that side, and the opposite angle.

**What it teaches:**
- Reduce the construction to locating the unknown vertex $A$.
- Split the condition into parts and describe each part’s **locus**:
	- points at fixed distance from the base line (a parallel line),
	- points from which the base subtends a given angle (an arc).
- The solution is the **intersection of loci**.

### Example K — Decompose an ambiguous condition (crossword pun/anagram clue)

**Problem (paraphrased):** A crossword clue like “Forward and backward part of a machine (5 letters).”

**What it teaches:**
- Treat the clue as a condition with parts (meaning + wordplay constraint).
- If too many candidates satisfy meaning, focus on the wordplay (“forward and backward” suggests the word reads the same both ways).
- Use “drop part of the condition” as a search tactic, then recombine.

### Example L — Go back to definitions (line–parabola intersection)

**Problem (paraphrased):** Construct the intersection points of a given line with a parabola specified by focus and directrix.

**What it teaches:**
- If you don’t have advanced theorems available, “go back to the definition.”
- A parabola is a locus defined by equal distance to focus and directrix.
- Combine “definition as locus” with “intersection of loci” to turn an abstract curve into constructive constraints.

### Example M — Guess → reformulate → prove a simpler sub-claim (max-area quadrilateral)

**Problem (paraphrased):** Among all quadrilaterals with a fixed perimeter, which has maximal area?

**What it teaches:**
- Make the simplest symmetric guess (square) and state it clearly.
- If the full claim is hard, solve a part first: among rectangles with fixed perimeter, show the square maximizes area.
- Translate into algebra and reduce to a basic inequality like $(a-b)^2\ge 0$.

### Example N — Use crossings + structural constraints (crossword “back and forth”)

**Problem (paraphrased):** A crossword clue like “Do the walls again, back and forth” for a 7-letter word.

**What it teaches:**
- Start with a plausible prefix guess (“re-”), but treat it as provisional.
- Check against other entries (crossing letters) to confirm/refute.
- Re-examine the clue: “back and forth” may impose a forward/backward structure that narrows the search.

### Example O — Extreme case + invariance idea (two ships, closest approach)

**Problem (paraphrased):** Two ships move in straight lines at constant velocities; find their minimum separation.

**What it teaches:**
- First, specialize to an extreme case (one ship at rest) to get immediate traction.
- Then add a key remark: motion is relative. Subtract one ship’s velocity from both so one becomes “at rest” without changing relative distances.
- Pattern: solve a less ambitious auxiliary problem + add one insightful invariance to lift it back.

### Example P — Check by varying data to extremes (frustum volume of a pyramid)

**Problem (paraphrased):** Find the volume of a pyramid frustum with square bases (side lengths $a$ and $b$) and height $h$.

**What it teaches:**
- Before you have the full formula, predict constraints it must satisfy:
	- if $b=a$, you get a prism ($V=a^2h$),
	- if $b=0$, you get a pyramid ($V=a^2h/3$).
- These serve as built-in checks once you derive a candidate formula.

### Example Q — Vary the problem after a failed attempt (trapezoid from four sides)

**Problem (paraphrased):** Construct a trapezoid given its four side lengths.

**What it teaches:**
- If a direct attempt fails, don’t discard it—modify it.
- Vary a datum to reach simpler limiting shapes (triangle, parallelogram), study those, and then return.
- The final approach often comes via a more accessible auxiliary construction discovered by variation.

### Example R — Working backwards (measuring 6 quarts with 9- and 4-quart containers)

**Problem (paraphrased):** You have two containers of capacities 9 and 4; obtain exactly 6 units of water.

**What it teaches:**
- Forward trial-and-error can work, but is slow and accidental.
- Working backwards: visualize the desired final state and ask what state could precede it.
- “Antecedent of the antecedent” thinking turns a random search into a directed chain.

### Example S — Add an auxiliary line to make a theorem obvious (sum of triangle angles)

**Problem (paraphrased):** Prove the sum of angles in a triangle equals a straight angle.

**What it teaches:**
- Introduce a helpful auxiliary element (draw a line through a vertex parallel to the opposite side).
- Use a known related fact (alternate interior angles) to translate the claim into something immediate.

---

## Canonical Technique Families (the “forms” most tactics take)

### 1) Representation changes (make it visible)
- Draw a diagram; make a table.
- Introduce coordinates; rename variables; rewrite conditions.
- Re-encode the problem (algebra ↔ geometry ↔ graph ↔ counting).

**Heuristic:** “If I can’t *see* it, I can’t solve it.”

### 2) Decomposition & recomposition
- Split into cases.
- Prove a lemma.
- Solve a simpler subproblem and build back up.

**Heuristic:** “Solve a smaller twin.”

### 3) Analogy & reuse
- Find a similar solved problem.
- Map the structure and adapt the method.

**Heuristic:** “What does this *remind* me of?”

### 4) Working backward / reverse engineering
- Start from the goal.
- Ask what must be true immediately before the goal.
- Invert operations when possible.

**Heuristic:** “If it were already solved, what had to happen?”

### 5) Auxiliary elements
- Add a helpful construction (extra line/point), or define an auxiliary variable/function.
- Create a bridge between given information and the goal.

**Heuristic:** “Add the missing piece.”

### 6) Constraints and extremes
- Check boundary cases.
- Use contradiction.
- Use extremal elements (largest/smallest/first/last) to force structure.

**Heuristic:** “Push it to the edge.”

### 7) Invariants, monotonicity, and conservation
- Identify what stays constant.
- Identify what only increases/decreases.
- Track conserved quantities across steps/moves.

**Heuristic:** “What can’t change?”

### 8) Symmetry and normalization
- Exploit symmetry; relabel objects.
- Normalize (translate/scale/center) to reduce degrees of freedom.

**Heuristic:** “Make the situation fair.”

### 9) Guess–verify–refine
- Experiment with small cases.
- Make a plausible conjecture.
- Then prove it cleanly.

**Heuristic:** “Experiment, then justify.”

### 10) Proof-shape choices
- Choose the proof pattern that matches the structure: direct, contradiction, contrapositive, induction, pigeonhole, counting, etc.

**Heuristic:** “Match the proof to the problem’s bones.”

---

## Mental Models (what you’re training)

- **State-space navigation:** treat each transformation as a move that reduces uncertainty.
- **Structure-first thinking:** identify the problem *type* (existence, construction, optimization, equivalence, counting, process) before grinding.
- **Constraint satisfaction:** each constraint either eliminates cases, suggests an invariant, or hints at a representation.
- **Local-to-global:** small examples discover patterns; proofs certify them.
- **Meta-cognition loop:** when stuck, change (a) representation, (b) direction (forward/backward), or (c) granularity (subproblem/lemma).

---

## Compact checklist (memorize)

### SIGHT–PATH–CHECK

**SIGHT (Understand / Represent)**
- **S**tate it in your own words
- **I**dentify unknowns, data, constraints
- **G**ive names/variables; define terms
- **H**ighlight what must be proved/constructed
- **T**ry a diagram/table/special cases

**PATH (Devise a plan)**
- **P**attern match (similar problems?)
- **A**uxiliary addition (new variable/line/lemma?)
- **T**ransform (rewrite, substitute, change viewpoint)
- **H**ead backward (work from goal)

**CHECK (Do / Review)**
- Verify steps; test edges; ask “why must this be true?”
- Extract the key idea; write the one-sentence method; generalize.

---

## “If stuck, do this” triggers

- Stuck understanding → **rephrase + example + diagram**
- Stuck planning → ask: **“What’s the simplest related problem?”**
- Stuck executing → **work backward one step** or **split into cases**
- Stuck proving → try **contradiction/contrapositive** or hunt an **invariant**
- Solution found → **look back**: shorten, generalize, or find a cleaner representation
