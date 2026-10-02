## Chapter 7: Routing, Bend Radius, and Professional Dressing — Practice Questions

**Q1.** An NVL72-class rack has copper cable trays on both the left and right vertical channels. During install, a technician routes all 72 compute tray cables down the left channel only to save time. What is the MOST likely consequence?

A) No consequence, since total cable count is unchanged
B) The switch will automatically load-balance signal paths regardless of physical routing
C) Only the fiber cables are affected; copper cables are immune to fill-density issues
D) Left-channel congestion causes airflow obstruction and exceeds the tray's cable-fill limit, risking bend-radius violations and thermal hotspots

<details>
<summary>Answer</summary>

**Correct: D**

The 50/50 left-right strategy exists specifically to prevent single-channel overfill, which causes airflow blockage, forces tight bends at the tray egress points, and creates thermal hotspots in NVL72 racks.

**Why the others are wrong:**
- Cable count doesn't change but physical density per channel doubles, directly causing fill and bend issues
- Physical routing has no relationship to logical switch load-balancing
- Fiber and copper are both subject to fill-density and bend-radius constraints

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A rack passes cable management inspection, but a fiber trunk was found looped with a radius of 18mm at a tray exit point. What is the direct technical risk?

A) Increased latency only, with no physical damage
B) Micro-bend and macro-bend attenuation causing signal loss or link failure, and possible fiber fracture over time
C) The connector will physically disconnect within 24 hours
D) No risk if the fiber is single-mode rather than multi-mode

<details>
<summary>Answer</summary>

**Correct: B**

Bending fiber tighter than the ~30mm minimum bend radius induces micro-bend/macro-bend loss, degrading signal integrity and risking permanent fiber damage or fracture.

**Why the others are wrong:**
- Latency is not the primary effect; attenuation and link errors are
- Fracture is a long-term risk, not an immediate guaranteed failure within a fixed time window
- Both single-mode and multi-mode fiber are subject to bend-radius limits; single-mode is often MORE sensitive

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** During final dressing of an NVL72 rack, a technician must bundle a group of 12 active optical cables (AOCs) running side-by-side in a vertical channel. Which bundling method should be used?

A) Zip ties, tightened firmly to prevent movement
B) Adhesive cable clips directly on the fiber jacket
C) No bundling; cables should be left loose for airflow
D) Hook-and-loop (Velcro) straps, applied loosely enough to avoid compressing the cable jackets

<details>
<summary>Answer</summary>

**Correct: D**

Hook-and-loop ties allow secure bundling without the crushing force zip ties apply, protecting fiber cores and copper conductors from deformation.

**Why the others are wrong:**
- Zip ties can over-compress cable jackets, risking fiber core damage and impedance changes in copper
- Adhesive clips directly on fiber jackets can stress the cable and are not a standard dressing method
- Leaving cables completely unbundled fails professional dressing standards and creates strain/snag risk

</details>

---

**Q4.** Which bundling approach is preferred for high-density fiber trunks specifically because it minimizes point-load pressure that could crack fiber cores?

A) Standard nylon zip ties
B) Metal cable clamps
C) Soft hook-and-loop ties
D) Duct tape wrapping

<details>
<summary>Answer</summary>

**Correct: C**

Soft hook-and-loop ties distribute pressure evenly across the bundle, avoiding the concentrated point-load that rigid fasteners like zip ties or clamps create on fiber cores.

**Why the others are wrong:**
- Nylon zip ties create concentrated pressure points that can micro-fracture fiber
- Metal clamps are far too rigid and risk crushing cable bundles
- Duct tape is not an approved dressing material and leaves adhesive residue

</details>

---

**Q5.** Per TIA-606 labeling conventions applied during rack dressing, what information MUST a cable label include at minimum?

A) A unique identifier linking the cable to both its origin and destination endpoints
B) Only the cable manufacturer's part number
C) The technician's initials who installed the cable
D) The date of manufacture only

<details>
<summary>Answer</summary>

**Correct: A**

TIA-606 requires a unique administrative identifier that traces each cable to its origin and destination, enabling troubleshooting and moves/adds/changes without physical tracing.

**Why the others are wrong:**
- Manufacturer part numbers aid inventory but don't satisfy traceability requirements
- Installer initials are not a TIA-606 requirement
- Manufacture date alone provides no endpoint traceability

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** What is the minimum bend radius constraint typically enforced for high-density cabling in NVL72-class rack installations?

A) 10mm
B) ~30mm
C) 75mm
D) 150mm

<details>
<summary>Answer</summary>

**Correct: B**

The exam-tested minimum bend radius benchmark for NVL72-class high-density copper and fiber harnesses is approximately 30mm; violating this threshold risks attenuation, signal degradation, or physical fiber damage.

**Why the others are wrong:**
- 10mm is far below the safe minimum and would virtually guarantee fiber damage
- 75mm is more than double the exam-tested minimum and overstates the requirement
- 150mm dramatically overstates the constraint and is not the tested figure

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** When routing cables in an NVL72 rack, how much slack should be allocated at each termination point?

A) Zero slack, cables must be pulled taut for a clean appearance
B) Enough slack to allow for one service loop and future re-termination without full replacement, without creating excess bulk that violates bend radius at the tray
C) At least 1 meter of slack per cable regardless of rack size
D) Slack should only be allocated on fiber, never on copper

<details>
<summary>Answer</summary>

**Correct: B**

Proper slack allocation allows for a service loop (re-termination, maintenance access) while remaining tight enough not to violate bend-radius limits or overfill trays.

**Why the others are wrong:**
- Zero slack prevents re-termination and can create tension damage or hidden tight bends
- A fixed 1 meter figure is not a real spec and would create excessive, unmanageable bulk in dense trays
- Slack allocation applies to both fiber and copper cabling for serviceability

</details>

---

**Q8.** What is the primary purpose of color-coding conventions during cable dressing in a high-density rack?

A) To enable rapid visual identification of cable function or path (e.g., management vs. data vs. inter-rack) without tracing individual runs
B) To indicate cable manufacturer for warranty purposes
C) To satisfy fire code requirements only
D) To indicate which cables can be routed without bend-radius constraints

<details>
<summary>Answer</summary>

**Correct: A**

Color-coding provides fast, at-a-glance identification of cable function or destination, drastically reducing troubleshooting and maintenance time in dense NVL72 environments.

**Why the others are wrong:**
- Color-coding is not used for manufacturer/warranty identification
- Fire code compliance relates to plenum-rated jackets, not color-coding conventions
- Bend-radius constraints apply uniformly regardless of cable color

</details>

---

