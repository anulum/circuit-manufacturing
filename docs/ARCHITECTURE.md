<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-MANUFACTURING — repository foundation
-->

# Repository architecture

## Current executable tooling

**What it contains:** the repository's metadata, source-provenance, workflow, dependency-alignment, documentation, inventory and preflight controls.

**What each control does:** it inspects its fixed, declared local scope.

**What received metadata cannot do:** select another acceptance policy or grant domain authority.

Foundation qualification is in progress.

## Intended domain boundaries

| Record | Responsibility | Required evidence |
| --- | --- | --- |
| Manufacturing package, process route and recipe release | Tapeout/assembly release archive (with foundry vault merge and PDK-errata checks), ordered station route and acceptance-qualified recipe payload | Tapeout qualification from Circuit Acceptance and person-in-role release sign-off |
| Material state, genealogy event, work order and material disposition | `J-STD-020`/`J-STD-033` moisture-sensitivity floor-life/bake state, lot/wafer/carrier genealogy, work-order dispatch and `GHS` incompatible chemical-waste merge refusal | Automatic hold on expired moisture floor-life or incompatible waste-stream combinations |
| Change proposal and supplier handoff | Engineering/process change control (`PCN`, end-of-life, last-time-buy, second-source qualification) and tamper-evident foundry/OSAT handoff with HSM challenge-response or on-die key-provisioning quotas | Zero plaintext cryptographic key files at OSATs and bounded unit-authorisation counters against overproduction |
| Wafer-sort and test-feed record | Batch `STDF v4` (`Semi-ATE/STDF`, MIT) and finite-chunk-sealed streaming `SEMI E183 RITdb` wafer maps, `IEEE 1687 IJTAG` ring-oscillator/PVT baselines, scribe-line `WAT`/`PCM` distributions, `AEC-Q001` outlier holds and `Cpk` one-sided lower-confidence-bound lot gating | Explicit sample size `n`, confidence level and one-sided lower confidence bound (exact non-central `t` for a one-sided index `Cpl` or `Cpu`, or Bissell's approximation for two-sided `Cpk`, each under a stated normality trust), plus sequence-gap markers on streaming feeds |
| Unit serial genealogy and hardware BOM provenance | Wafer `(x, y)`-to-package-to-board serial lineage, anti-counterfeit `IDEA-STD-1010` / X-ray / decapsulation screening for non-franchised parts and root-of-trust security-version (`SVN`) fuse bindings | End-to-end serial traceability into Deploy Pack, Field Ops Witness, Flight Recorder and Neuro Safety Case |
| Corrective action and RMA record | Field return or test-escape intake, failure-analysis quarantine, automatic sibling-lot `HOLD`, `8D` root-cause/escape-regression link and engineering-change trigger | Closed-loop propagation back to Circuit Digital, Circuit Physical, Circuit Devices, Circuit Technology and Circuit Acceptance |

## Statistical lot gating and licence isolation

- **Lower-confidence-bound `Cpk` gating.** Parametric lot acceptance never relies on a point estimate of `Cpk` alone; every gate states sample size `n`, the sampling unit (accounting for within-wafer and wafer-to-wafer spatial clustering rather than treating spatially correlated dies on one wafer as independent lot draws), confidence level and the one-sided lower confidence bound estimator — exact non-central `t` for a one-sided index (`Cpl` or `Cpu`), or Bissell's approximation for two-sided `Cpk`, each under a stated normality trust — alongside pre-declared `AEC-Q001` part-average outlier limits.
- **Licence isolation.** Permissive `Semi-ATE/STDF` (`MIT`) readers run in-process, while `GPL-2.0` `Semi-ATE` suites and copyleft/proprietary MES adapters execute strictly in separate processes.

## Planned record schemas

- `circuit_manufacturing.manufacturing_package.v1`
- `circuit_manufacturing.process_route.v1`
- `circuit_manufacturing.recipe_release.v1`
- `circuit_manufacturing.material_state.v1`
- `circuit_manufacturing.genealogy_event.v1`
- `circuit_manufacturing.work_order.v1`
- `circuit_manufacturing.material_disposition.v1`
- `circuit_manufacturing.change_proposal.v1`
- `circuit_manufacturing.supplier_handoff.v1`
- `circuit_manufacturing.wafer_sort_and_test_feed_record.v1`
- `circuit_manufacturing.unit_serial_genealogy.v1`
- `circuit_manufacturing.hardware_bom_and_provenance_record.v1`
- `circuit_manufacturing.corrective_action_and_rma_record.v1`

These are planned identifiers. None of them is registered or qualified here.

Read [validation tooling](validation-tooling.md) for the executable repository interfaces.
