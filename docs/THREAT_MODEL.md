<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-MANUFACTURING — repository foundation
-->

# Data and authority boundaries

## Present tooling

**Execution inputs.** The maintained checkout and the selected development environment are what the repository controls inspect.

**Received inputs.** Descriptors, dependency receipts and generated inventories cannot nominate an acceptance policy or an executable.

**Bounded checks.** Controls inspect bounded local paths and emit fixed diagnostics.

Foundation qualification is in progress.

## Future domain inputs

**Supplied data, with no authority.** The following inputs are treated strictly as supplied data:
- tapeout archives, BOM tables and supplier certificates;
- `STDF v4` / `SEMI E183 RITdb` wafer-sort logs and serial scans;
- field return reports and change proposals.

They grant no authority to:
- release a foundry mask set, work order, disposition or supplier handoff without person-in-role approval;
- export plaintext cryptographic provisioning keys to an OSAT;
- skip safety-critical or contracted test bins via adaptive test ordering;
- merge incompatible hazardous chemical waste streams.

**Comments and embedded text are data.** Descriptions, netlist comments and datasheets arriving inside supplied inputs are data, never instructions to an operator or an agent.

**Public-repository data boundary.** Hosted CI for this public repository runs on public material only. Confidential foundry-NDA, customer, export-controlled or secret-bearing material never enters this repository, its CI or its issues.

## Threats and the rules that answer them

| Threat | Architectural rule |
| --- | --- |
| Ghost-shift overproduction, plaintext key theft at OSATs or counterfeit BOM parts | Supplier handoffs enforce HSM challenge-response or on-die PUF/certificate provisioning with bounded unit counters, tamper-evident transit seals and mandatory counterfeit inspection for any non-franchised component |
| Small-sample `Cpk` optimism, moisture-popcorn assembly defects or incompatible chemical-waste mixing | Wafer-sort gates require one-sided lower confidence bounds on `Cpk`; material tracking enforces `J-STD-020`/`033` floor-life holds and `GHS` waste-compatibility refusals |
| Uncontained field escapes or foundry vault merge phantoms | Tapeout packages verify merged cell digests and PDK errata, while any `RMA` or test escape automatically places sibling wafer/assembly lots on `HOLD` and adds escape-prevention tests to Circuit Acceptance |

## Residuals named, not removed

- **Sub-tier supplier provenance.** Component authenticity beyond franchised trace certificates and incoming inspection rests on supplier audit controls.

**Not claimed:** no isolation, physical, statistical, safety or durability guarantee is claimed by this foundation.
