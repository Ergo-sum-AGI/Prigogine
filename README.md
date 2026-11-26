# Prigogine

Friedrichs Model, Liouville Spectral Organization, and the Search for a Common
Framework of Dynamical Complexity and Irreversibility.

This repository is a research diary, not a publication archive. Files are kept
in the state in which they were last worked on. Several contain known open
problems or internal corrections that have not yet been propagated into the
files they bear on. The notes below are intended to let a returning reader
(or an auditor) see at a glance what each file is, what state it is in, and
what would need to happen next if the line of work were resumed.

## Stage 1 — Single-particle foundation

| Artifact | State | Note |
|---|---|---|
| `friedrichs_stage1_single_particle_foundation.md` | Current (revision 2) | Core Stage 1 reference. Continuum functionals corrected; contour-jump factorization recorded with a block-by-block check. Open obligations are tabulated in §14 of the file. |
| `friedrichs_biorthogonal_completeness_note3.md` | Foundational source | Earlier derivation of biorthogonal completeness. Should be read as background to the Stage 1 file rather than as a corrected statement. |
| `friedrichs_liouville_resonance_eigenoperator.md` | Supporting note | Single-sector eigenoperator derivation. Useful as a worked example; not independently audited. |
| `To establish the continuum resolvent jump.txt` | Working derivation | Block-by-block proof of the continuum resolvent jump factorization (eq. 7.3 in Stage 1). Formal kernel algebra; test-space justification still owed. |

## Stage 2 — Liouville spectral organization

| Artifact | State | Note |
|---|---|---|
| `Stage 2 Liouville Spectral Organization of Friderichs.md` | Superseded draft | Original Stage 2 write-up. Kept for provenance; superseded by the corrected version. |
| `Stage 2-Liouville Spectral Organization of the Friedrichs Model (corrected).md` | Current (pending audit) | Three major corrections incorporated. Still the working Stage 2 reference. Audit against the Stage 1 revision 2 obligations has not been done. |

## Stage 3 — Spectral-coordinate and metric construction

| Artifact | State | Note |
|---|---|---|
| `Stage 3-Spectral-Coordinate and Metric ConstructionI.md` | Provisional | Preliminary Stage 3 work. An internal inconsistency is known and has not been resolved. |
| `friedrichs_lambda_M_derivation_summary.md` | Provisional | Preliminary derivation of the Λ/M construction. Inherits the open issue in the Stage 3 file above. |

## Transfer-operator and zeta-function notes

| Artifact | State | Note |
|---|---|---|
| `friedrichs_transfer_operator_note1.tex` | Working note (Research Note I) | Transfer-operator investigation of the Friedrichs model. Contains the contractive-semigroup claim that the corrigendum withdraws; see `corrigendum_friedrichs_zeta.md` §8. Not yet revised. |
| `friedrichs_zeta_note2.tex` | Working note (Research Note II) | Spectral-determinant and Selberg–Riemann connection. The half-scaled zero correspondence is argued via the functional equation in this draft; the corrigendum records why that argument is insufficient and supplies an independent route. Not yet revised. |
| `corrigendum_friedrichs_zeta.md` | Corrective note | Records the withdrawn and retained claims across both Research Notes. Self-correcting: §2 withdraws the functional-equation argument, §5 reinstates the conclusion via the Selberg zero-divisor theorem. |
| `Correction to Corrigendum.md` | Corrigendum to the corrigendum | Confirms the §5 reinstatement and adds the residue statement for the logarithmic derivative. Should be read together with `corrigendum_friedrichs_zeta.md`. |

## Historical and reference material

| Artifact | State | Note |
|---|---|---|
| `microscopic_theory_of_irreversible_processes_equations.md` | Reference | Equation register for Prigogine–Mayné–George–De Haan (1977). |
| `microscopic_theory_of_irreversible_processes_full_transcription.md` | Reference | Full transcription of the 1977 PNAS paper. |
| `research_legacy_note_friedrichs_liouville.md` | Hand-over note (legacy) | Legacy note. Useful for orientation; not maintained. |
| `tough-millennium-problem-solved.md` | Programme statement / origin | Poses the research question the repository addresses: whether there exists a common spectral formulation of dynamical complexity and thermodynamic irreversibility, with the Ruelle transfer operator and Prigogine's non-unitary transformation as complementary aspects. Names the Friedrichs model as the first controlled test case (implemented as Research Note I) and the Riemann zeta function as the longer-range target. Written as a research-diary entry, not a publication. |

## Reading order

A reader coming to this repository fresh should read, in order:

1. `tough-millennium-problem-solved.md` — the research question.
2. `friedrichs_stage1_single_particle_foundation.md` — the one-particle foundation for the controlled experiment.
3. `Stage 2-Liouville Spectral Organization of the Friedrichs Model (corrected).md` — the Liouville lift.
4. `friedrichs_transfer_operator_note1.tex` and `friedrichs_zeta_note2.tex` — the transfer-operator side of the controlled experiment (this is the "next step" the origin file names)
5. `corrigendum_friedrichs_zeta.md` and `Correction to Corrigendum.md`, since the corrigenda qualify claims in both notes.
6. `Stage 3-Spectral-Coordinate and Metric ConstructionI.md` — the current frontier, with its known open issue.

## Status conventions

- **Current** — the file is the working reference for its stage; further work would build on it, not replace it.
- **Current (pending audit)** — as above, but no audit has been done against the upstream obligations.
- **Provisional** — the file contains a known open issue or an incompletely propagated correction. Treat conclusions as conditional.
- **Superseded** — kept for provenance only.
- **Working derivation / Working note / Foundational source / Supporting note** — the file is a piece of the derivation chain rather than a stage-level reference; read it in context.
- **Corrective note / Corrigendum** — the file exists to record a correction to another file. Read it alongside its target.
- **Reference / Hand-over / Programme statement / origin** — not part of the live derivation chain yet instrumental or foundational.
