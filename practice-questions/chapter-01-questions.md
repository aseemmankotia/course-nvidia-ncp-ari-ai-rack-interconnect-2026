## Chapter 1: AI Rack Power Fundamentals — Practice Questions

**Q1.** A colocation facility deploys GB200 NVL72 racks drawing ~120kW each, fed by 3-phase 208V rPDUs rated 60A/phase (~21.6kVA). Applying the 80% continuous-load derating rule, how many rPDUs are minimally required per rack to achieve 2N redundancy at full IT load?

A) 14 PDUs total (7 per side, independent A/B feeds)
B) 6 PDUs total (3 per side)
C) 7 PDUs total shared across both feeds
D) 12 PDUs total (6 per side)

<details>
<summary>Answer</summary>

**Correct: A**

2N requires each feed (A and B) to independently support the full 120kW load. Derated usable capacity per rPDU is 21.6kVA x 0.8 = 17.28kW. 120 / 17.28 = 6.94, rounded up to 7 PDUs per side, x2 sides = 14 total.

**Why the others are wrong:**
- 6 PDUs (3 per side) yields only ~51.8kW usable per side — far below the 120kW requirement.
- 7 PDUs on a single shared feed is N, not 2N — a single feed failure drops the entire rack.
- 12 PDUs (6 per side) yields only ~103.7kW usable per side, still under the 120kW draw.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A technician reviews an intelligent rPDU's per-phase metering: Phase A = 28A, Phase B = 14A, Phase C = 14A. What is the MOST likely operational risk?

A) The DC bus voltage will collapse across all connected servers
B) The rPDU firmware requires a mandatory update to continue operating
C) Phase A's breaker trips before B/C, causing partial rack power loss even though overall rack capacity remains available
D) The rack will automatically fail over to the redundant 2N feed

<details>
<summary>Answer</summary>

**Correct: C**

Unbalanced phase loading means one phase can hit its breaker's trip threshold while the other phases still have spare headroom, causing an avoidable partial outage.

**Why the others are wrong:**
- This is an AC 3-phase system, not a DC bus — DC bus voltage collapse is irrelevant here.
- Phase imbalance is an electrical loading issue, not a firmware issue, and does not require an update.
- Phase imbalance on one PDU does not trigger a 2N failover; failover only occurs on actual feed failure.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A hyperscale AI facility distributes -48VDC power via busbars directly to GPU racks instead of AC rPDUs feeding per-server PSUs. What is the primary benefit tested on the exam?

A) It eliminates the need for redundant power feeds entirely
B) It allows the rack to skip all grounding requirements
C) It increases the rack's total cooling load requirement
D) It reduces AC-DC-AC conversion losses by removing per-server PSU conversion stages, improving overall power efficiency

<details>
<summary>Answer</summary>

**Correct: D**

DC busbar distribution removes redundant AC-to-DC conversion stages present in per-server PSUs, cutting conversion losses and improving efficiency at scale — a key driver for high-density AI rack architectures.

**Why the others are wrong:**
- DC distribution has no bearing on whether redundant feeds (N+1/2N) are required — redundancy is still designed independently.
- Grounding is still mandatory in DC architectures; DC systems require their own bonding and fault-return path verification.
- DC distribution does not inherently change cooling load; cooling requirements are driven by IT power draw, not distribution voltage type.

</details>

---

**Q4.** Which redundancy configuration provides two fully independent, separately-sourced power paths PLUS one additional backup unit within each path?

A) N+1
B) 2N+1
C) 2N
D) N+2

<details>
<summary>Answer</summary>

**Correct: B**

2N+1 duplicates the entire power path (2N) and adds one spare unit within each independent path for extra fault tolerance.

**Why the others are wrong:**
- N+1 has only one spare unit on a single shared path, not two independent paths.
- 2N duplicates the path fully but has no additional spare unit beyond the duplicate path itself.
- N+2 adds two spare units to a single shared path; it does not describe independent duplicated paths.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** A rack requires exactly one extra power module beyond the minimum needed for full IT load, with all PDUs sharing a common feed. Which redundancy level does this describe?

A) 2N
B) 2N+1
C) N
D) N+1

<details>
<summary>Answer</summary>

**Correct: D**

N+1 adds a single spare unit to a shared infrastructure path, tolerating one component failure without duplicating the entire path.

**Why the others are wrong:**
- 2N requires two fully independent, separately-sourced paths, not a single shared path with one spare.
- 2N+1 requires both duplicated paths AND a spare in each — more than described here.
- N alone provides zero redundancy; any full-load failure causes an outage.

</details>

---

**Q6.** A 208V single-phase rPDU branch circuit is rated at 30A. Applying the 80% continuous-load derating rule, what is the maximum continuous IT load current that should be planned for this circuit?

A) 30A
B) 27A
C) 24A
D) 20A

<details>
<summary>Answer</summary>

**Correct: C**

80% of the 30A rated capacity is 24A (30 x 0.8 = 24), the maximum continuous load per NEC-style derating practice.

**Why the others are wrong:**
- 30A is the full rated (non-derated) capacity — planning to this level violates the continuous-load rule and risks nuisance tripping.
- 27A does not correspond to the standard 80% derating calculation.
- 20A under-derates the circuit and wastes available capacity, not matching the 80% rule.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** When verifying grounding on a high-density AI rack prior to energization, what is the exam-relevant acceptance criterion?

A) A continuous, low-resistance bonding path exists between the rack frame and the facility grounding grid
B) Grounding is optional if the rack uses redundant 2N power feeds
C) Only a visual inspection of the ground wire color is required
D) Grounding checks only apply to DC-powered racks, not AC racks

<details>
<summary>Answer</summary>

**Correct: A**

Proper bonding requires verifying a continuous, low-resistance electrical path from the rack frame to the facility grounding grid before energization, per standard data center bonding practices.

**Why the others are wrong:**
- Redundant power feeds address availability, not electrical safety/fault-return paths — grounding is always required regardless.
- Visual inspection alone does not confirm electrical continuity or resistance; measurement is required.
- Grounding verification applies to both AC and DC racks — DC systems still require a fault-return/bonding path.

</details>

---

**Q8.** What is the fundamental difference between N+1 and 2N redundancy tested on the exam?

A) N+1 adds one extra component to a shared infrastructure path, while 2N duplicates the entire infrastructure path
B) N+1 is more expensive to implement than 2N in every case
C) N+1 and 2N are functionally identical, differing only in naming convention
D) 2N redundancy applies only to cooling systems, not power systems

<details>
<summary>Answer</summary>

**Correct: A**

N+1 tolerates a single component failure within a shared path; 2N duplicates the entire path so that a full path failure (e.g., an entire feed) does not cause an outage.

**Why the others are wrong:**
- 2N is generally more capital-intensive than N+1 due to fully duplicated infrastructure, the reverse of this claim.
- The two redundancy levels provide materially different fault tolerance — they are not interchangeable naming conventions.
- 2N is a general redundancy design principle applied to power (and other) infrastructure, not exclusive to cooling.

</details>

---

