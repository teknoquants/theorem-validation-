# PTA — p-adic Teichmüller Automata: white paper and verification scripts

## Contents
- PTA_whitepaper.docx — full white paper (Theorems 1–14, corrected and verified).
- verify_scripts/verify_thmN.py — one verification script per theorem.
- run_all.sh — runs all fourteen scripts in order.
- EXPECTED_OUTPUT.txt — reference transcript; your run should match it.

## Provenance
Theorems 1–14: author-corrected statements (Roger, XISOSIS). Every verification
script is the author's revised version, checked to run. This completes the original
fourteen-theorem PTA programme: each draft theorem's headline was found to have no
true form or to overstate what holds, and each was replaced by a proved, verified,
honestly-scoped statement.

## What the scripts check (and deliberately do NOT)
Each script tests only the falsifiable content of its theorem in exact arithmetic
(Fractions, Gaussian integers Z[i], Q(i) for phases; finite fields from computed irreducible
polynomials in Theorem 8; modular integers in Theorem 12; symbolic streams in Theorem 13),
with finite eigenspectra numerical where noted (Theorem 14). Many tests are *negative* —
confirming a false statement is false: Thm 3 (parallel-edge swap is only a graph symmetry),
Thm 5 (unnormalised product diverges), Thm 6 (a core–hair coherence survives), Thm 7
(populations cycle, no pointwise convergence), Thm 8 (only Aff(F_p) commutes with Frobenius),
Thm 9 (constant q needs no traversal), Thm 10 (F_P=(-)⊕P is NOT exact), Thm 11 (x1²+…+x5² is
isotropic over Q_p), Thm 12 (a p^{n-1} perturbation changes a mod-p^n invariant), Thm 13 (the
geometric bound is not a factorial prohibition; output need not stabilize), Thm 14 (the
spectral gap decreases across the tested range and a constant q needs no traversal, so
"computational supremacy" is unsupported). Hypotheses that are not finite-sample facts
(block-encoding existence, QSVT polynomials, amplitude estimation, hardware, IUTT/Diophantine
identifications, asymptotic spectral behavior) are printed as NOT-TESTED / SCOPE manifests.

## Running
python3 with numpy for scripts 1,2,4,6,7,8,14; scripts 3,5,9,10,11,12,13 use only the
standard library. From this folder:  ./run_all.sh   or e.g.  python3 verify_scripts/verify_thm14.py

## Standard applied
Every claim is tested by an independent computation, able to fail — not asserted by
definition. This standard, and the negative-testing discipline, caught real errors during
development (non-monoidal representation, Thm 1; exponential cost mislabelled polynomial,
Thm 3; QSVT parity error, Thm 4; divergent product, Thm 5; over-strong direct-sum, Thm 6;
false pointwise convergence, Thm 7; over-broad commutation, Thm 8; two false complexity lower
bounds, Thm 9; a fixed-object functor wrongly called exact, Thm 10; an overstated Solèr
nonexistence claim, Thm 11; index/size confusion, Thm 12; an overstated factorial/stabilization
claim, Thm 13; an overstated asymptotic-gap claim, Thm 14), each corrected before inclusion.

