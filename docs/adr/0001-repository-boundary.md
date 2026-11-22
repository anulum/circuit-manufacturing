<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-MANUFACTURING — repository foundation
-->

# Decision: separate manufacturing genealogy, wafer-sort gating, BOM provenance and RMA containment from cell equipment drivers

## Context

Lot genealogy, `STDF` wafer-sort statistics, OSAT key-provisioning security, moisture/waste compliance and `8D`/`RMA` containment span external foundries, OSATs and internal cells, whereas real-time machine protocols (`SECS/GEM`, `OPC UA`, robotics) have distinct safety-interlock boundaries.

## Decision

**What Circuit Manufacturing owns:**
- manufacturing package, process route and recipe release;
- material state, genealogy event, work order and material disposition;
- change proposal and supplier handoff;
- wafer-sort and test-feed record;
- unit serial genealogy and hardware bom provenance;
- corrective action and rma record;

**What it imports:** Circuit Core, Circuit Technology and Circuit Flow.

**Owned elsewhere:**

| Responsibility | Owner |
|---|---|
| physical equipment drivers, robotics and safety clamps | Circuit Automation |
| bench failure-analysis capture and calibration | Circuit Lab |
| compact-model corner refitting | Circuit Devices |
| recipe, prototype and tapeout sign-off | Circuit Acceptance |

## Consequences

**What can be qualified now:** repository governance and validation tooling, before domain code exists.

**What it cannot qualify:** unimplemented schemas, solvers, hardware or sign-off verdicts.

**Architectural consequences:**
- Circuit Manufacturing owns the thirteen manufacturing, provenance, wafer-sort and RMA contracts on the planned manufacturing path;
- real-time equipment protocols, safety interlocks and input-surface clamps live separately in Circuit Automation, avoiding any cyclic dependency.
