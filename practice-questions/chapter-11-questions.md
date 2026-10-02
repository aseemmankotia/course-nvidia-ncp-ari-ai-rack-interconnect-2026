## Chapter 11: Safety and Compliance in High-Power Environments — Practice Questions

**Q1.** A technician must service a power distribution unit feeding a 120kW GPU rack row. Per OSHA 1910.147, what is the correct FIRST step?

A) Prepare for shutdown by identifying all energy sources and notifying affected personnel
B) Apply the lock and tag immediately to the disconnect
C) Verify zero energy state with a rated multimeter
D) Put on arc-flash PPE and open the panel to inspect

<details>
<summary>Answer</summary>

**Correct: A**

The OSHA six-step LOTO sequence begins with preparation — identifying all energy sources (electrical, stored, mechanical) and notifying affected employees — before any de-energization occurs.

**Why the others are wrong:**
- Locks/tags are applied in step 4, after shutdown and isolation, not first
- Verification of zero energy is the final step (step 6), performed after isolation
- PPE is worn throughout the process but donning it is not the defined 'first step' of the procedure

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A cable run passes through an air-handling plenum space above a modular AI data center hall. Which NEC cable rating is required?

A) CMP (Plenum)
B) CM (General Purpose)
C) CMR (Riser)
D) CMX (Residential)

<details>
<summary>Answer</summary>

**Correct: A**

CMP (Communications Plenum) cable has the lowest smoke and flame spread rating and is the only type approved for installation in plenum air-handling spaces without conduit.

**Why the others are wrong:**
- CM is the lowest-rated cable and is prohibited in both plenum and riser spaces
- CMR is rated for vertical riser shafts, not plenum airflow spaces
- CMX is rated for limited residential use only and has no plenum approval

</details>

---

**Q3.** You are wiring a vertical shaft connecting two network cabinets on different floors of a data center. What is the MINIMUM acceptable NEC cable rating?

A) CM
B) CMR
C) CMX
D) No rating required if conduit is used

<details>
<summary>Answer</summary>

**Correct: B**

CMR (Communications Riser) is the minimum rating designed to prevent fire from spreading floor-to-floor in vertical shafts.

**Why the others are wrong:**
- CM cable is not rated to prevent floor-to-floor flame spread and is prohibited in risers
- CMX is a residential-only rating with no riser approval
- Conduit does not eliminate the NEC cable rating requirement for riser applications

</details>

---

**Q4.** Which statement correctly describes the NEC cable substitution hierarchy?

A) CM cable can substitute for CMR cable
B) CMR cable can substitute for CMP applications
C) CMP cable can substitute for both CMR and CM applications
D) All communications cable types are fully interchangeable

<details>
<summary>Answer</summary>

**Correct: C**

CMP has the highest fire-resistance rating in the hierarchy, so it may be used anywhere CMR or CM is permitted — but not vice versa.

**Why the others are wrong:**
- CM is the lowest-rated cable and cannot substitute upward for CMR
- CMR is lower-rated than CMP and cannot substitute for plenum applications
- Cable types follow a strict one-directional hierarchy, not full interchangeability

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** A technician is about to perform maintenance on a GB200 NVL72-class rack drawing approximately 120kW. Per NFPA 70E and NVIDIA DU-10438 guidance, what PPE requirement applies?

A) Standard cotton coveralls are sufficient
B) No PPE is needed once the breaker is switched off
C) Only an ESD wrist strap is required
D) Arc-rated PPE matching the site's calculated incident energy category is required

<details>
<summary>Answer</summary>

**Correct: D**

High-density power environments require arc-flash risk assessment; PPE must match the calculated incident energy (cal/cm²) category for the specific equipment and voltage class.

**Why the others are wrong:**
- Cotton is not arc-rated and can ignite/melt in an arc flash event
- Breaker position alone does not confirm zero energy state — verification and appropriate PPE are still required during the process
- ESD protection addresses component damage, not personnel electrical/arc-flash hazards

</details>

---

**Q6.** During installation of an NVIDIA reference architecture rack per DU-10438, a technician skips the specified torque values on busbar connections to save time. What is the primary risk?

A) No impact, since torque values are optional recommendations
B) Voided warranty and risk of loose connections causing overheating or arcing
C) Only a cosmetic issue affecting rack appearance
D) Improved airflow due to looser hardware

<details>
<summary>Answer</summary>

**Correct: B**

DU-10438 specifies mandatory torque values for power connections; deviation is a documented non-compliance that voids NVIDIA warranty support and creates a fire/overheating hazard from high-resistance connections.

**Why the others are wrong:**
- Torque specs are compliance-mandatory, not optional, in DU-10438
- Loose busbar connections are an electrical safety hazard, not merely cosmetic
- Loose hardware has no relation to airflow and instead increases resistance and heat

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** A technician removes a GPU module from its anti-static bag for installation. Which procedure correctly follows ESD protection standards?

A) Touch the metal chassis briefly; no wrist strap is needed
B) Work on a carpeted floor to insulate against ground faults
C) Wear a grounded ESD wrist strap connected to a common ground point and use an ESD mat
D) Store the module temporarily in a plain cardboard box

<details>
<summary>Answer</summary>

**Correct: C**

ANSI/ESD S20.20 requires a grounded wrist strap and ESD-safe work surface to maintain a continuous, verified path to ground for sensitive components like GPU modules.

**Why the others are wrong:**
- Momentary chassis contact does not maintain a continuous ground path during handling
- Carpet generates and holds static charge, increasing ESD risk
- Plain cardboard is not ESD-shielding and can allow static buildup

</details>

---

**Q8.** During LOTO on a shared busbar feeding multiple 120kW racks, one technician has already locked out the circuit. A second technician arrives to also work on the same circuit. What is the correct procedure?

A) Each technician applies their own individual lock and tag (group lockout)
B) The second technician relies on the first technician's lock and tag
C) The second technician skips lockout since the circuit is already de-energized
D) Only the site supervisor's lock is required for multi-person work

<details>
<summary>Answer</summary>

**Correct: A**

Group lockout procedures require every individual exposed to the hazard to apply their own personal lock and tag, ensuring the circuit cannot be re-energized until all workers have cleared and removed their locks.

**Why the others are wrong:**
- Relying on another person's lock removes individual accountability and control
- Prior de-energization by someone else does not verify zero energy state for the second worker
- A single supervisor lock does not satisfy the requirement for each exposed worker to control their own isolation

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

