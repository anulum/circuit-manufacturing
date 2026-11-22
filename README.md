<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-MANUFACTURING — repository foundation
-->

# Circuit Manufacturing

Circuit Manufacturing is being built on the planned manufacturing path to govern foundry and assembly tapeout packages, process routes, qualified recipe releases, moisture-sensitive material states, hazardous-waste compatibility, wafer-sort `STDF v4` / `SEMI E183 RITdb` ingestion with `Cpk` lower-confidence-bound lot gating, per-unit serial genealogy, hardware bill-of-materials anti-counterfeit and cryptographic-provisioning provenance, and closed-loop `8D` corrective-action and `RMA` sibling-lot containment — completely deterministically without requiring AI. This checkout contains repository validation tooling and documentation only. Full foundation qualification is in progress. There is no installed manufacturing-execution package, wafer-sort analyser, genealogy tracker, RMA engine or qualified record schema.

**What does not exist yet:**
- a manufacturing-execution, `STDF` wafer-sort, genealogy or `8D`/`RMA` engine;
- a registered runtime record schema;
- an active foundry tapeout, OSAT line or factory integration.

## Boundary

**What this project owns:**

| Record | Scope |
|---|---|
| Manufacturing package, process route and recipe release | Tapeout/assembly release archive (with foundry vault merge and PDK-errata checks), ordered station route and acceptance-qualified recipe payload |
| Material state, genealogy event, work order and material disposition | `J-STD-020`/`J-STD-033` moisture-sensitivity floor-life/bake state, lot/wafer/carrier genealogy, work-order dispatch and `GHS` incompatible chemical-waste merge refusal |
| Change proposal and supplier handoff | Engineering/process change control (`PCN`, end-of-life, last-time-buy, second-source qualification) and tamper-evident foundry/OSAT handoff with HSM challenge-response or on-die key-provisioning quotas |
| Wafer-sort and test-feed record | Batch `STDF v4` (`Semi-ATE/STDF`, MIT) and finite-chunk-sealed streaming `SEMI E183 RITdb` wafer maps, `IEEE 1687 IJTAG` ring-oscillator/PVT baselines, scribe-line `WAT`/`PCM` distributions, `AEC-Q001` outlier holds and `Cpk` one-sided lower-confidence-bound lot gating |
| Unit serial genealogy and hardware BOM provenance | Wafer `(x, y)`-to-package-to-board serial lineage, anti-counterfeit `IDEA-STD-1010` / X-ray / decapsulation screening for non-franchised parts and root-of-trust security-version (`SVN`) fuse bindings |
| Corrective action and RMA record | Field return or test-escape intake, failure-analysis quarantine, automatic sibling-lot `HOLD`, `8D` root-cause/escape-regression link and engineering-change trigger |

**Static imports:** Circuit Core, Circuit Technology and Circuit Flow.

**Records read without importing domain code:**

| Source | Records consumed |
|---|---|
| Circuit Core, Circuit Technology and Circuit Flow | entity references, data-handling profiles, operation profiles, person approvals, facility readiness, technology profiles, run plans and learning records |
| Circuit Physical, Circuit Assembly and Circuit Digital | post-fill layouts, shuttle specs, assembly packages, chiplet stacks, DFT manifests and signed firmware bindings |
| Circuit Automation, Circuit Lab, Circuit Devices and Circuit Acceptance | cell/state/reconciliation/clamp/recovery/reservation records, calibrated captures, compact models, qualifications and acceptance reports |
| Evidence Manifest Toolkit | shared evidence manifest envelopes |

**Capability registration and handoffs:** Registers the manufacturing-execution manifest with Circuit Core and exports provenance, genealogy and RMA records to Deploy Pack, Field Ops Witness, Flight Recorder, Neuro Safety Case, Evidence Manifest Toolkit and Experiment Ledger.

**Explicit non-claims and operating boundaries:**
- It belongs to the planned manufacturing path: no factory, foundry run or assembly line is claimed to exist today.
- Every manufacturing route, lot gate, genealogy trace and corrective-action check works deterministically without machine learning.
- Point-estimate `Cpk` alone never clears parametric wafer-sort acceptance: lot gating requires a one-sided lower confidence bound naming sample size `n`, confidence level and estimator.
- Adaptive test ordering never skips safety-critical or customer-contracted test bins without an enrolled person-in-role approval, and wafer-sort maps are never used as reinforcement-learning rewards.

## Current tooling

Repository controls inspect:
- metadata and source attribution;
- workflows and dependency alignment;
- native documentation and repository inventory;
- preflight orchestration.

Metadata declares architecture-only maturity with empty implemented domain capability and claim inventories.

- Use the exact environment in [Contributing](CONTRIBUTING.md).
- Full CI and preflight belong in CI or in an explicitly admitted pre-push environment.
- See [Validation](VALIDATION.md) for the maintained validation scope.

## Intended evidence

Every future domain artefact will carry the platform's common provenance envelope, its source and environment digests, its confidentiality compartment and its explicit verification boundary. None of the planned record schemas is registered or qualified by this foundation.

## Documentation and support

Read [Architecture](ARCHITECTURE.md), [support](SUPPORT.md), [security reporting](SECURITY.md) and [citation metadata](CITATION.cff).

**Not claimed:**
- a hosted service, released package or DOI;
- a public CI status;
- a performed simulation, hardware measurement or sign-off verdict.

## Licence

Source is licensed under [AGPL-3.0-or-later](LICENSE). A commercial licence is available through the contact in [NOTICE](NOTICE.md).

![ANULUM](docs/assets/anulum_logo_company.jpg)

![Fortis Studio](docs/assets/fortis_studio_logo.jpg)

## Text and data mining reservation
The rightsholder, Miroslav Šotek (ANULUM), expressly reserves the use of the
works in this repository for text and data mining, including the collection of
this content for, and its use in, training, fine-tuning or evaluating machine
learning and artificial intelligence models, in accordance with Article 4(3) of
Directive (EU) 2019/790 and the national provisions transposing it.

No permission for such use has been granted beyond what the licence in
`LICENSE` grants. This reservation does not change that licence: uses the
licence permits remain permitted on its terms, including its attribution and
share-alike conditions.

Reservation made on 2026-11-22. Requests for permission: contact the
rightsholder through the contact listed in this repository.
