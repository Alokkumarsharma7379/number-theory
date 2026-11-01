# First unit: well-ordering, division, GCD, and Bézout

**State:** specified, not yet authored or marked complete. This plan makes the next work concrete without treating a file skeleton as a finished lesson.

## Why start here?

B p. 1 states well-ordering, and B pp. 2–8 repeatedly develop Bézout and its consequences. These arguments are prerequisites for Diophantine equations, inverses, CRT, and much of the later course. Although infinitude of primes appears on B p. 1, its clean proof needs the existence of a prime divisor; it should be revisited in the prime unit rather than interrupt this dependency chain.

**Verified source anchors:** A §1.1 printed p. 1 (well-ordering); §2.2 printed pp. 17–19 (division and examples); §2.3 printed pp. 20–24 (divisibility, GCD, Bézout, coprimality, Euclid lemma); B pp. 1–8 and the divisibility question on p. 12. For later algorithm work, A §2.4 printed pp. 26–32.

## Manageable completion boundaries

### Part A: well-ordering and division

- Explain integer domains, positive/nonnegative sets, divisibility, and integer linear combinations.
- Treat well-ordering as the foundational principle assumed in Burton, not a theorem to “prove” circularly from induction and back again.
- Supply a short induction/strong-induction bridge where needed; retain deeper induction exercises for the prime unit.
- Prove the divisibility properties actually used: transitivity, integer linear combinations, mutual divisibility up to sign, and the nonzero multiple size bound.
- Prove division existence using a least nonnegative remainder and uniqueness using the difference of two remainders.
- Explain negative dividends and, separately, negative divisors.
- End with examples, selected problems, counterexamples, and an exam-ready self-test.

This can be a completed mathematical subsection before any GCD code is added. Pure well-ordering does not need a forced programming snippet. If a quotient/remainder implementation is included, its signed-division semantics and valid input range must be explicit and tested.

### Part B: GCD and Bézout

For each item, include motivation, precise statement, 3–6 sentences of proof intuition, detailed proof, separate **Exam-ready proof**, example, traps, and revision summary.

| Result | Verified reference | Proof obligation |
|---|---|---|
| GCD exists for integers not both zero | A Def. 2.2, p. 21 | Positive common-divisor set nonempty and bounded by a nonzero input |
| GCD equals least positive integer combination | A Thm. 2.3, pp. 21–22; B 3–6 | Nonempty set; remainder argument for both inputs; every common divisor divides minimum |
| All integer combinations are exactly GCD multiples | A corollary, p. 22; B 7 | Both inclusions; coefficients in $\mathbb Z$ |
| Coprime iff integer combination is 1 | A Thm. 2.4, p. 23; B 2–3, 7–8 | Separate forward and reverse directions |
| Dividing inputs by their GCD leaves a coprime pair | A corollary 1, p. 23; B 7 | Quotients are integers; divide a Bézout identity |
| Coprime divisors of c have product dividing c | A corollary 2, p. 23; B 8 | Correct use of coprimality; give counterexample without it |
| Euclid lemma | A Thm. 2.5, p. 24; B 8 | Multiply Bézout by c; every divisibility deduction justified |
| Characterization by common-divisor divisibility | A Thm. 2.6, p. 24 | Avoid assuming this property before it is established |
| GCD scaling | B 8 (positive multiplier) | Prove for positive multiplier; label any extension to negative multiplier with absolute value |

Do not prove Bézout by invoking the full Diophantine solution theorem, which will itself rely on Bézout. Do not describe an arbitrary positive combination as the GCD.

### Part C: Euclidean computation and programming

Prove $\gcd(a,b)=\gcd(b,a-qb)$ by equality of common divisors; explain descending nonnegative remainders and the last nonzero remainder. Derive back-substitution and the extended algorithm from coefficient invariants. Add LCM only with its proof and a range-safe implementation. A §2.4 is the source; these are systematic algorithmic additions rather than an invented claim that the notebook contains complete code.

## Examples to prepare

| Source | Example type | Teaching purpose |
|---|---|---|
| A §2.2, p. 18, unnumbered division examples | Signed divisor/dividend; examples with divisor $-7$ | Mathematical remainder convention versus language remainder |
| A §2.2, pp. 18–19, Example 2.1 | Integrality of $a(a^2+2)/3$ for positive integer a | Exhaustive remainder cases; no need for Fermat |
| A §2.2, p. 18, unnumbered square arguments | Squares modulo 4, odd squares modulo 8 | Recognize finite-case proof technique |
| A §2.3, p. 21, Example 2.2 | $\gcd(-12,30)$ and a linear-combination certificate | Positive GCD with signed inputs |
| A §2.3, p. 22, unnumbered example | Positive combinations of 6 and 15 | Minimum combination versus arbitrary combination |
| A §2.4, pp. 27–28, Example 2.3 | $\gcd(12378,3054)$ and back-substitution | Same problem solved mathematically and algorithmically |

Use concise problem descriptions and independently written reasoning. Label new pedagogical examples as original, not as textbook exercises.

## Lecture-question inclusion register

| Source | In-scope obligation | Treatment |
|---|---|---|
| B 2–6 | Coprime and general Bézout statements | Consolidate repeated presentations into one checked proof plus special-case consequence |
| B 7 | All combinations are GCD multiples; normalized pair coprime; converse from combination 1 | Include all distinct results |
| B 8 | Coprime product divisibility; Euclid lemma; scaling | Include all three |
| B 12 | $6\mid n(n+1)(n+2)$ | Include as a worked proof exercise; elementary parity plus modulo 3, then coprime divisors combine |
| B 1, 13–19, 37–41 | Infinitude/factorization and prime bounds | Deferred to primes and modular applications, not omitted |
| B 9–11 | Diophantine theorem and fruit problem | Deferred to next unit; unclear fruit assumptions remain flagged |
| B 11–12 | Residue group questions | Deferred to algebra bridge after congruences |

## Burton exercise selection

The lists in A §2.2 (p. 19) and §2.3 (pp. 24–26) were inspected. Numbers below are verified. This is the selection plan, not a claim of solved exercises. Difficulty is an editorial learning estimate.

| Problem ID | Printed page | Faithful short description | Difficulty | Reason for selection |
|---|---:|---|---|---|
| A §2.2 #1 | 19 | Division with remainder in $[2b,3b)$ | Medium | Existence and uniqueness under a shifted interval |
| A §2.2 #2 | 19 | Compare forms $6k+5$ and $3j+2$; reject converse | Easy | Necessary versus sufficient conditions |
| A §2.2 #3(a–c) | 19 | Possible square/cube/fourth-power remainder forms | Medium | Exhaustive cases with different moduli |
| A §2.2 #4 | 19 | $3a^2-1$ cannot be a square | Medium | Impossibility by residue obstruction |
| A §2.2 #7 | 19 | Unique balanced remainder in $(-|b|/2,|b|/2]$ | Hard | Endpoint choice, negative divisor, uniqueness |
| A §2.3 #1 and #2(a–d) | 24 | Signed divisibility and basic product/cancellation facts | Easy | Formal manipulation from definition |
| A §2.3 #3 | 24 | Does divisibility of a sum imply divisibility of a summand? | Easy | Construct a counterexample |
| A §2.3 #10–12 | 25 | Zero/equal/unit arguments, sign invariance, consecutive-input GCD | Easy–Medium | Edge cases and common-divisor reasoning |
| A §2.3 #13(a–b) | 25 | Representability by integer combination; coprimality of Bézout coefficients | Medium | Both directions and a less obvious consequence |
| A §2.3 #14(a) | 25 | Coprimality of $2a+1$ and $9a+4$ | Medium | Find a short certificate by eliminating a |
| A §2.3 #15 | 25 | GCD of two combinations divides b; numerical-form consequence | Medium | Reverse linear combinations, include zero-input exclusion |
| A §2.3 #18, three-consecutive-integers part | 25 | Product of three consecutive integers divisible by 6 | Easy–Medium | Exact overlap in technique with B 12; cross-reference one solution |
| A §2.3 #20(a,c,e,f) | 25 | Coprimality under products; GCD of scaled input; common-divisor consequences; squares | Medium–Hard | Distinct Bézout and coprimality techniques |
| A §2.3 #23 | 26 | From $a\mid bc$, show $a\mid\gcd(a,b)\gcd(a,c)$ | Hard | Non-obvious synthesis; prove using normalization and Euclid lemma |

**Deferred explicitly:** §2.2 #5–6 and #8–11 (additional remainder/integrality practice); §2.3 #4–9, #14(b–c), #16–17, the four/five-consecutive parts of #18, #19, #20(b,d), #21–22. These remain available for mixed revision or later induction/factorization units. Their deferral is a scope choice, not a statement that they are unimportant. Review §2.4 examples and its entire exercise list before finalizing Part C's separate selection; do not invent that list now.

Each completed solution must have: source ID/page, short problem, difficulty, key idea, complete independent solution, why it works, useful alternative if any, meaningful programming connection if any, and a specific common mistake. Put independent-attempt prompts before a link to the separate solutions file.

## Code design and explanations

**Mathematical problem:** given signed integers a,b, compute a nonnegative GCD; for nonzero pairs also produce integer coefficients x,y with $ax+by=g$. Teach a divisor-enumeration reference before Euclid. The reference is for small tests, not an optimized solver.

**Initial supported C++ range:** use a clearly stated conservative range such as $|a|,|b|\le10^9$ for the learning implementation, with widened intermediate calculations where proved necessary. Do not silently accept all `long long` inputs. In particular, negating `LLONG_MIN`, `abs(LLONG_MIN)`, and overflowing LCM products require deliberate handling. `__int128` is a GNU extension, not portable ISO C++20; label its use if chosen. Decide the exact contract before writing tests.

**Python:** arbitrary-precision integers avoid fixed-width overflow, but operations on growing integers are not constant-time. Compare the manual implementation with `math.gcd`; explain tuple assignment and quotient/remainder semantics. Built-in comparisons do not replace a proof.

**Shared API policy:** document `gcd(0,0)=0` as a programming convention. For extended GCD either define and explain a consistent zero-pair result or reject that case. Invalid text/input handling belongs to a small CLI wrapper, not mixed into the mathematical invariant.

**Dry run:** use A Example 2.3 for the remainder table and one small signed example for sign normalization. Show coefficient columns for extended Euclid. Link to one implementation wherever Bézout is reused.

**Complexity:** prove logarithmic remainder-step count (e.g. every two steps reduce the current scale by at least half); distinguish arithmetic-step complexity from bit complexity. Iterative GCD has constant auxiliary word storage under fixed-width arithmetic. Extended Euclid stores a fixed number of coefficients, whose sizes still matter. No invented runtime comparisons.

**Language concepts introduced naturally:** `long long`, range limits, `%` signs, local variables, loops, functions, return values, `std::gcd`, small structs/pairs for certificates; Python `int`, `//`, `%`, tuples and `math.gcd`. Vectors enter with array GCD and prefix/suffix practice, not before needed.

## Actual verification plan

| Check | Cases / independent oracle | What it detects |
|---|---|---|
| Small exhaustive GCD | All pairs in $[-50,50]^2$ against positive-divisor enumeration (zero-pair convention separate) | Sign, zero, divisibility errors |
| Certificate invariant | For every valid extended result, verify $ax+by=g$ using Python exact integers | Coefficient-update and sign bugs |
| Boundary fixtures | $(0,0),(0,7),(-7,0),(1,-1)$, equal numbers, coprime pairs, large common factors, supported range endpoints | Input-contract and arithmetic mistakes |
| Slowest-shape inputs | Consecutive Fibonacci values within supported range | Termination, loop/count assumptions |
| Reproducible random checks | Fixed seed, record case count and bounds; compare with `math.gcd` | Wider regression coverage |
| Metamorphic checks | Swap inputs, change signs, replace a by $a+kb$ within supported range | Broken GCD invariants |
| LCM if included | Small brute-force multiples plus exact identity $g\ell=|ab|$ for nonzero inputs; zero separately | Overflow/order-of-operations errors |
| Cross-language execution | One shared fixture stream through compiled C++ and Python; compare parsed outputs | Implementation divergence |
| Compiler diagnostics | C++20 with `-Wall -Wextra -Wshadow`; sanitizers if supported | Undefined behavior and warnings |

Compile and execute before recording results. The report must name compiler/Python versions, commands, seed/case count, actual pass/fail results, and anything not executed. Failure to find a compiler is an explicit execution limitation, never a passing result. Keep oracle code simple and independent of the optimized recurrence.

## Revision and completion

The unit's revision file must give definitions, full theorem hypotheses, key proof constructions, typical questions, formulas, counterexamples, and closed-book self-tests. A useful diagnostic is: “If $d=ax+by>0$, what additional fact makes d the GCD?” Another is: “Why does the remainder argument fail if the minimum is taken over all integer combinations?”

Finish with an original mixed set covering a signed calculation, an existence/uniqueness proof, a false converse, a Bézout certificate, and a non-obvious divisibility argument. Use [proof-checklist.md](../revision/proof-checklist.md). Mark the subsection complete only when its own mathematical deliverables are checked; record code execution and student mastery separately.
