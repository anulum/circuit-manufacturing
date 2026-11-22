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

Circuit Manufacturing is being built on the planned manufacturing path to govern foundry and assembly tapeout packages, process routes, qualified recipe releases, moisture-sensitive material states, hazardous-waste compatibility, wafer-sort `STDF v4` / `SEMI E183 RITdb` ingestion with `Cpk` lower-confidence-bound lot gating, per-unit serial genealogy, hardware bill-of-materials anti-counterfeit and cryptographic-provisioning provenance, and closed-loop `8D` corrective-action and `RMA` sibling-lot containment — completely deterministically without requiring AI. Its current executable surface is repository validation tooling. It has no installed manufacturing-execution package, wafer-sort analyser, genealogy tracker, RMA engine or qualified record schema.

Read [Architecture](ARCHITECTURE.md), [validation tooling](validation-tooling.md), [data boundaries](THREAT_MODEL.md) and the [repository boundary decision](adr/0001-repository-boundary.md).
