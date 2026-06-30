# BESS Industry Glossary — Acronyms & Core Concepts

A working reference for the acronyms and concepts that come up constantly in BESS (Battery Energy Storage System) engineering, commercial, and procurement conversations. Organized by category rather than alphabetically, since grouping related terms together makes them easier to actually retain — and most real conversations mix terms from several categories in a single sentence anyway.

Maintained by [Sam](#) as a companion to the *Industrial Ledger* LinkedIn series on BESS engineering and commercial fundamentals. Corrections and additions welcome — see [CONTRIBUTING.md](CONTRIBUTING.md).

---

## 1. Grid Operators (ISOs/RTOs)

These organizations run wholesale electricity markets and manage grid reliability across a region. Every BESS project lives inside one of these markets, and which one matters a lot — rules, revenue streams, and capacity-accreditation methods differ significantly between them.

| Term | Meaning |
|---|---|
| **ISO** | Independent System Operator — a nonprofit entity that operates the grid and runs wholesale power markets for a region, independent of the utilities that own the generation/transmission assets. |
| **RTO** | Regional Transmission Organization — functionally similar to an ISO but typically covers a larger, multi-state footprint. The terms are often used interchangeably in practice. |
| **PJM** | The largest RTO in the US, covering all or part of 13 Mid-Atlantic/Midwest states plus DC (PA, NJ, MD, OH, VA, etc.). Runs the capacity-market structure (BRA) referenced constantly in BESS commercial discussions. |
| **CAISO** | California ISO — manages most of California's grid. Known for extreme solar duck-curve dynamics, which is why CAISO has driven much of the US 4-hour storage buildout (arbitrage around the solar ramp). |
| **ERCOT** | Electric Reliability Council of Texas — manages ~90% of Texas's grid, operating largely independent of the rest of the US grid. Energy-only market (no mandatory capacity market), which changes how BESS revenue stacks are built there. |
| **MISO** | Midcontinent ISO — covers a large swath of the Midwest and parts of the South (from Minnesota down to Louisiana). |
| **NYISO** | New York ISO. |
| **ISO-NE** | ISO New England. |
| **SPP** | Southwest Power Pool — covers much of the central US (Kansas, Oklahoma, Nebraska, etc.). |

---

## 2. Capacity Market & Reliability Accreditation

The vocabulary around how storage gets paid for simply being available and reliable, separate from any energy it actually sells.

| Term | Meaning |
|---|---|
| **ELCC** | Effective Load Carrying Capability — the methodology used to calculate how much "capacity credit" a resource earns, based on how reliably it can deliver power during the grid's highest-risk hours. A battery's ELCC depends heavily on duration: a 4-hour system generally earns a lower ELCC % than an 8-hour or 10-hour system, because it can't cover as long a stretch of risk hours. ELCC also has a **marginal** dynamic — as more of a given resource type gets built, each new increment's ELCC tends to decline (a saturation effect, separate from any duration comparison). |
| **ICAP** | Installed Capacity — a resource's maximum/nameplate output rating (in PJM, specifically its summer rating), before any accreditation adjustment. |
| **UCAP** | Unforced Capacity — a resource's *accredited* capacity value after adjusting for outage risk and reliability performance (via ELCC or similar methodology). This is the actual product transacted in the capacity market — what gets paid for. |
| **Capacity Accreditation** | The general process of converting a resource's nameplate (ICAP) capacity into the (usually smaller) accredited value (UCAP) the grid operator will actually count toward reliability and compensate. |
| **BRA** | Base Residual Auction — PJM's primary capacity-market auction, held roughly 3 years ahead of the delivery year, where generation and storage resources bid to provide capacity. |
| **CONE** | Cost of New Entry — the estimated cost to build a new generation resource in a given region; used as a reference price/cap in capacity auctions. |
| **LOLE** | Loss of Load Expectation — a reliability metric estimating the expected number of days/hours per year the grid might not be able to meet demand. A core input to ELCC and resource-adequacy modeling (PJM's standard is roughly "1 day in 10 years"). |
| **LOLH** | Loss of Load Hours — a related reliability metric expressed in expected hours of shortfall rather than days/events. |
| **EUE** | Expected Unserved Energy — the expected amount of energy (MWh) that won't be served during shortfall events; another resource-adequacy risk metric. |
| **Resource Adequacy (RA)** | The general practice/requirement of ensuring there's enough generation, storage, and demand response capacity to reliably meet peak demand with an adequate reserve margin. |

---

## 3. Battery & System Technical Terms

| Term | Meaning |
|---|---|
| **BESS** | Battery Energy Storage System — the umbrella term for the whole system (cells + BMS + PCS + EMS + thermal/fire systems), not just the battery cells. |
| **BMS** | Battery Management System — the hardware/firmware that monitors and protects individual cells/modules: voltage, temperature, balancing, fault detection. |
| **EMS** | Energy Management System — the higher-level control software that decides *how* the BESS is dispatched (when to charge/discharge, which revenue stream to chase). Often the system referenced in cybersecurity/remote-access discussions, since it's typically the layer with external/vendor connectivity. |
| **PCS** | Power Conversion System (sometimes "Power Conditioning System") — the inverter stack that converts DC battery power to AC grid power (and back during charging). The PCS rating is what sets a system's **MW** number; the battery cells set the **MWh** number. |
| **SoC** | State of Charge — how full the battery is right now, as a % of its capacity. |
| **SoH** | State of Health — how degraded the battery is relative to new, as a % of original capacity/performance. |
| **RTE** | Round-Trip Efficiency — the % of energy returned from the battery relative to what was put in, accounting for conversion and resistive losses. A frequently-ambiguous spec in practice: does it include auxiliary load? At what duration/C-rate was it measured? Where are losses allocated (PCS vs. transformer vs. collection system)? |
| **C-rate** | A unitless measure of how fast a battery is charged/discharged relative to its capacity. 1C means full charge/discharge in 1 hour; 0.25C means 4 hours. C-rate = Power (MW) ÷ Energy (MWh). |
| **DoD** | Depth of Discharge — how much of the battery's capacity is used in a given cycle, expressed as a %. |
| **Augmentation** | Adding additional battery capacity partway through a project's life (a mid-life "top-up") to compensate for degradation and keep meeting a contracted capacity guarantee. |
| **LFP** | Lithium Iron Phosphate — the dominant chemistry in grid-scale BESS today, valued for cycle life, thermal stability, and lower cost (no cobalt/nickel). |
| **NMC** | Nickel Manganese Cobalt — a lithium-ion chemistry with higher energy density than LFP, more common in EVs than in grid storage. |
| **NCA** | Nickel Cobalt Aluminum — another high-energy-density chemistry, notably used in some EV and early stationary-storage applications. |
| **DC-coupled / AC-coupled** | Describes how a battery is connected relative to a paired generation source (e.g., solar). DC-coupled shares a single inverter/DC bus with the generation source; AC-coupled uses a separate inverter for the battery, connecting only at the AC side. Affects augmentation flexibility and conversion efficiency. |

---

## 4. Safety & Standards

| Term | Meaning |
|---|---|
| **UL 9540** | The overarching UL safety listing/standard for energy storage systems and equipment — certifies the equipment itself. |
| **UL 9540A** | A standardized fire **test method** (not a code) used to evaluate a battery system's thermal-runaway fire-propagation behavior — initiates thermal runaway in one cell and measures whether/how it propagates to neighboring cells, modules, or units. Results are used by Authorities Having Jurisdiction (AHJs) to determine required fire-protection measures. |
| **NFPA 855** | The National Fire Protection Association's standard for the *installation* of stationary energy storage systems — covers spacing/separation, suppression, and ventilation requirements. Generally requires equipment to be UL 9540-listed and, above certain thresholds, UL 9540A-tested. |
| **AHJ** | Authority Having Jurisdiction — the local fire marshal or regulatory body responsible for approving a BESS installation against applicable codes. |
| **IEEE** | Institute of Electrical and Electronics Engineers — publishes various interconnection and grid-code standards (e.g., IEEE 1547 for distributed energy resource interconnection). |
| **Thermal Runaway** | The self-sustaining, escalating heat-generating chemical reaction inside a failing lithium-ion cell that can cascade to neighboring cells/modules — the central failure mode that fire codes and BMS designs are built around preventing and containing. |

---

## 5. Commercial, Contracts & Procurement

| Term | Meaning |
|---|---|
| **RFP** | Request for Proposal — the formal solicitation document a utility/developer issues when procuring a BESS project; contains technical specs, commercial terms, and compliance requirements bidders must respond to. |
| **PPA** | Power Purchase Agreement — a contract where a buyer agrees to purchase the power (and/or capacity) output of a project over a long term, at agreed pricing. |
| **ESSA** | Energy Storage Services Agreement — a contract structure specific to storage, where the buyer typically pays for the *service* of dispatch/availability rather than purchasing energy outright the way a PPA does. |
| **EPC** | Engineering, Procurement, and Construction — the contract (and the contractor) responsible for designing and physically building the project. |
| **O&M** | Operations & Maintenance — the ongoing contract/service responsible for keeping the system running post-commissioning. |
| **COD** | Commercial Operation Date — the date a project is deemed ready to formally begin commercial operation. Often the date warranty terms and performance-guarantee clocks start running, which makes its exact contractual definition high-stakes. |
| **IE** | Independent Engineer — a third-party technical reviewer, selected by the lender (but often paid by the developer), who evaluates whether a project is sound enough to finance ("bankable"). Sits at the center of due diligence. |
| **LD** | Liquidated Damages — pre-agreed financial penalties owed if a contractual performance guarantee (capacity, RTE, schedule, etc.) isn't met. |
| **FEOC** | Foreign Entity of Concern — a US regulatory/tax-credit designation restricting eligibility for certain incentives (e.g., IRA tax credits) based on the nationality/ownership of equipment suppliers. Increasingly relevant to BESS sourcing decisions. |
| **ITC** | Investment Tax Credit — a US federal tax credit (expanded under the IRA) that reduces the effective cost of qualifying clean-energy and storage projects. |
| **IRA** | Inflation Reduction Act — the 2022 US legislation that significantly expanded clean-energy and storage tax incentives, including extending the ITC to standalone storage. |
| **Domestic Content Adder** | A bonus tax-credit % available under the IRA if a project meets domestic-manufacturing sourcing thresholds. |

---

## 6. Revenue Streams ("The Revenue Stack")

| Term | Meaning |
|---|---|
| **Energy Arbitrage** | Buying/charging when power prices are low and discharging/selling when prices are high — the most intuitive BESS revenue stream. |
| **Capacity Payments** | Revenue earned simply for being available and accredited (via ELCC/UCAP) in a capacity market like PJM's BRA — paid regardless of how much energy is actually dispatched. |
| **Ancillary Services** | A category of grid-support services (frequency regulation, spinning reserve, voltage support) that batteries are well-suited for because of their fast response time — historically a major early revenue source before markets saturated. |
| **Frequency Regulation** | A specific ancillary service: rapidly charging/discharging in small increments to help keep grid frequency at its nominal value (60 Hz in the US) — typically a fast, short-duration, high-C-rate application. |
| **Revenue Stack** | The combined mix of revenue streams (arbitrage + capacity + ancillary services, etc.) a project is designed and dispatched to capture. "Picking the revenue stack" is a core sizing and commercial-strategy decision. |

---

## A note on accuracy

This glossary reflects publicly available standards, market documentation, and industry reporting as of mid-2026. Capacity-market rules (especially ELCC methodologies) and tax/trade policy (especially FEOC and ITC eligibility) change frequently — verify current rules against the relevant ISO/RTO's own manuals or current federal guidance before relying on this for a proposal, contract, or compliance decision.
