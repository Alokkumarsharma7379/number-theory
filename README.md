# Number Theory: Mathematics and Code

Original study notes for university examinations, competitive programming, and careful C++20/Python programming. Mathematical understanding and independently reproducible proofs come first.

## Start here

1. [Source audit](audit/SOURCE_AUDIT.md): what the four supplied PDFs actually contain, with a ledger covering all 80 handwritten PDF pages.
2. [Syllabus map](SYLLABUS_MAP.md): lecture evidence, Burton references, priorities, and dependencies.
3. [Study roadmap](ROADMAP.md): semester-first and CP sequences sharing the same theory.
4. [First-unit plan](plans/01-foundations.md): scope, proof obligations, selected exercises, implementations, and test design.
5. [Corrections and uncertainties](audit/CORRECTIONS.md): issues to resolve before using the scans as exam notes.
6. [Progress](PROGRESS.md) and [references](REFERENCES.md).

## Current state

Phase 1 repository created on 1 November 2026. All handwritten pages have received visual topic-level inspection. This is a source audit, not a certified transcription or a line-by-line validation of every lecture proof. Specific uncertainties remain recorded. Burton's contents, relevant passages, and first-unit exercise lists were inspected; the entire 453-page book has **not** been studied exhaustively.

No teaching unit is marked completed. No number-theory implementations or execution results are claimed. The next unit is **well-ordering, division, GCD, and Bézout's identity**, split into the manageable boundaries described in its plan.

## Scope and navigation

The mapped semester covers divisibility, Diophantine equations, primes, congruences, algebraic structures, arithmetic functions (including Möbius inversion), orders, primitive roots, indices, quadratic residues, reciprocity, and the Jacobi symbol. Algorithmic extensions have separate labels. Quant relevance is principally proof discipline, algorithm analysis, numerical correctness, and experiment design; this repository does not claim that each theorem is a trading tool.

Current directories contain substantive planning and audit documents only. As units are written, use:

```text
number-theory/
  01-divisibility-and-gcd/
    README.md             # scope, prerequisites, navigation, completion checklist
    theory.md             # definitions, motivation, theorem statements, intuition
    proofs.md             # detailed and separate exam-ready proofs
    worked-examples.md    # independently explained source examples
    exercises.md          # selected/deferred register and attempt-first prompts
    solutions.md          # separate solutions, keyed to problem IDs
    exam-notes.md          # compact revision, traps, self-test
    programming.md        # derivation, dry runs, language comparisons, complexity
    cpp/                  # reusable C++20 implementations
    python/               # equivalent Python implementations
    tests/                # reference comparisons, edge cases, execution report
cp-practice/              # guided/independent practice index
revision/                 # shared proof checklist; later theorem/formula indexes
cpp-concepts/             # add only when a completed unit needs a shared explanation
python-concepts/          # likewise; avoid duplicating topic explanations
.github/workflows/        # add real CI when executable tests exist
```

Further concept directories are planned in ROADMAP.md; empty placeholders are deliberately not created. Pitfalls live beside the relevant mathematics and in exam notes rather than being repeated across several files.

## Running code when the first implementation lands

Planned toolchain: GNU C++20 and Python 3.11+. The commands below are conventions, **not commands that currently run against existing files**:

```sh
g++ -std=c++20 -O2 -Wall -Wextra -Wshadow number-theory/01-divisibility-and-gcd/cpp/gcd.cpp -o build/gcd
python number-theory/01-divisibility-and-gcd/python/gcd.py
python -m unittest discover -s number-theory/01-divisibility-and-gcd/tests
```

Create `build/` before compiling. On Windows the executable can be `build/gcd.exe`. A future test driver must compile C++, run both languages on the same cases, and report failures rather than silently skip C++.

For the current documentation, run `python tools/check_repository.py`. This checks local links and page-ledger completeness, not mathematical truth.

## Sources and publication

See REFERENCES.md for source labels and page conventions. Keep textbook PDFs, classroom scans, rendered pages, and extracted text private. `.gitignore` excludes PDFs and `tmp/`. This does not replace checking a future commit's staged files. No remote is configured and nothing has been pushed. See [license guidance](LICENSE_GUIDANCE.md) before publication.
