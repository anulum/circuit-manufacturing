<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-MANUFACTURING — repository foundation
-->

# Architecture

## Current executable surface

The checkout contains:
- repository validation tooling;
- dedicated tests;
- workflow definitions;
- native documentation.

No domain component of Circuit Manufacturing is implemented yet. The metadata keeps domain capabilities, claims and qualified record formats empty.

## Intended data flow

1. **Tapeout package, route and recipe release** assemble qualified layouts, firmware, assembly specs and acceptance-verified recipes into person-approved work orders.
2. **Material, moisture and waste tracking** enforce `J-STD-020`/`033` floor-life timers, tamper-evident supplier handoffs, bounded HSM key-provisioning quotas and `GHS` waste segregation.
3. **Wafer sort and serial genealogy** ingest `STDF v4` and `SEMI E183 RITdb` test feeds, gate lots on `Cpk` lower confidence bounds and `AEC-Q001` limits, extract scribe-line `WAT`/`PCM` anchors and bind die `(x, y)` coordinates to unit serial numbers.
4. **Closed-loop `8D` and `RMA` containment** quarantine failed or returned units, place sibling wafer/assembly lots on immediate `HOLD` and trigger regression gates and engineering-change proposals.

## Ownership

**This project owns** the planned Circuit Manufacturing records and boundary rules.

**Owned elsewhere:**

| Responsibility | Owner |
|---|---|
| physical equipment drivers, robotics and safety clamps | Circuit Automation |
| bench failure-analysis capture and calibration | Circuit Lab |
| compact-model corner refitting | Circuit Devices |
| recipe, prototype and tapeout sign-off | Circuit Acceptance |

## Interpretation

- **Normality in `Cpk` bounds.** Parametric `Cpk` lower confidence bounds assume approximate normality (checked alongside non-parametric part-average outlier screening).

Read [the documentation architecture](docs/ARCHITECTURE.md) for the planned records, domain rules and schema identifiers.
