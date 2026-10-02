## Chapter 4: Preparing the Rack for High-Density Install — Practice Questions

**Q1.** A facility is deploying GB200 NVL72 racks weighing up to 1,360 kg (3,000 lb) each. The raised-floor tiles are rated for 750 kg/m² static load. What must the architect do BEFORE installation?

A) Verify and, if needed, upgrade floor/structural load capacity or install reinforced plinths
B) Add extra cable trays underneath to spread the load
C) Reduce the rack's U-height to lower the total weight
D) Space racks 2 m apart so the average floor load stays low

<details>
<summary>Answer</summary>

**Correct: A**

High-density liquid-cooled AI racks exceed typical raised-floor ratings; structural verification/upgrade is mandatory before install.

**Why the others are wrong:**
- Cable trays do not add load-bearing capacity for rack weight.
- Reducing U-height does not reduce the mass of the compute/NVSwitch trays already installed.
- Spacing does not change the point load a single rack's casters/feet impose on the tiles beneath it.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A row design routes 480V busbar power whips and 400G DAC data cables in the same vertical manager, running parallel for 3 meters. What is the correct remediation per EMI mitigation best practice?

A) Route power and data in separate pathways/managers with minimum separation (e.g., 150mm), crossing at 90° when unavoidable
B) Tighten the cable ties to reduce cable movement
C) Bundle both cable types together inside a single shielded sleeve
D) No action needed — EMI only affects analog audio signals

<details>
<summary>Answer</summary>

**Correct: A**

TIA-569-C recommends a minimum 150mm (6in) separation between power and data pathways, with perpendicular crossing when parallel routing can't be avoided.

**Why the others are wrong:**
- Tie tightness has no effect on electromagnetic coupling.
- Bundling power and data together increases inductive/capacitive coupling and worsens EMI.
- High-speed differential data signals (e.g., DAC/twinax) are susceptible to EMI-induced noise and bit errors, not just audio.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A technician measures 600mm of front-post-to-front-door clearance on a newly installed GB200 NVL72 row, but the vendor reference spec requires a minimum of 1000mm. What is the direct consequence of leaving this uncorrected?

A) Improved airflow due to a tighter enclosure
B) Better fiber bend-radius compliance
C) Insufficient clearance to slide out compute/NVSwitch trays and route CDU coolant hoses for service
D) No impact — vendor clearance specs are only suggestions

<details>
<summary>Answer</summary>

**Correct: C**

Front clearance in liquid-cooled, tray-serviceable racks must accommodate tray slide-out and CDU hose routing; undersized clearance blocks maintenance access.

**Why the others are wrong:**
- Reduced clearance restricts airflow and service access rather than improving it.
- Front clearance is unrelated to fiber bend-radius compliance inside the rack.
- Vendor clearance specs for high-density liquid-cooled platforms are hard requirements tied to serviceability, not optional guidance.

</details>

---

**Q4.** Which cable management accessory should be installed to enforce a minimum bend radius on fiber trunk cables running vertically between rack U-positions?

A) A horizontal cable manager only
B) Standard zip ties applied every 1U
C) A bend-radius-controlled vertical cable guide/duct with radius fingers
D) An open cable tray with no guides

<details>
<summary>Answer</summary>

**Correct: C**

Vertical bend-radius managers use radius-limiting fingers/guides specifically designed to prevent fiber from being bent tighter than its minimum radius.

**Why the others are wrong:**
- Horizontal managers control lateral routing at a U-position, not vertical bend control between positions.
- Zip ties can crush or over-tighten fiber, causing micro-bend attenuation.
- An open tray provides no mechanical bend-radius enforcement.

</details>

---

**Q5.** Which platform typically requires a wider/deeper rack footprint (600mm x 1200mm) than a standard 600mm x 1000mm enterprise rack, primarily due to CDU manifolds and busbar routing?

A) A standard 1U pizza-box application server rack
B) A legacy top-of-rack network switch enclosure
C) A standalone UPS battery cabinet
D) An NVIDIA GB200 NVL72 liquid-cooled AI rack

<details>
<summary>Answer</summary>

**Correct: D**

The GB200 NVL72 rack-scale system integrates coolant distribution unit (CDU) manifolds and high-current busbars that require extra depth/width beyond a standard rack.

**Why the others are wrong:**
- Standard 1U servers fit within legacy rack depth and don't require CDU manifolds.
- Legacy switch enclosures are air-cooled and use standard rack dimensions.
- UPS cabinets have their own footprint standards unrelated to GPU rack cooling/power density.

</details>

---

**Q6.** Per TIA-569-C guidance, what is the minimum recommended parallel separation between power cabling and copper data cabling pathways to mitigate EMI in a high-density rack row?

A) 25mm (1 in)
B) 600mm (24 in)
C) No separation is required if the cabling is copper
D) 150mm (6 in)

<details>
<summary>Answer</summary>

**Correct: D**

150mm (6 in) is the standard minimum parallel separation distance recommended to reduce inductive/capacitive EMI coupling between power and copper data pathways.

**Why the others are wrong:**
- 25mm is insufficient to prevent meaningful EMI coupling at high current loads.
- 600mm is unnecessarily large and not the standard reference figure tested.
- Copper data cabling is the exact case that needs separation — it is NOT EMI-immune like fiber.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** When installing horizontal cable managers in a high-density AI rack, best practice is to install one approximately every how many U of active equipment?

A) Every 20U
B) Only at the very top and bottom of the rack
C) Horizontal managers should never be used with vertical managers present
D) Every 4-6U, between groups of switches/trays

<details>
<summary>Answer</summary>

**Correct: D**

Placing horizontal managers every 4-6U prevents cable congestion that blocks airflow and rear-door heat exchanger/service access in dense rack configurations.

**Why the others are wrong:**
- Every 20U leaves long unmanaged cable runs that sag and obstruct airflow.
- Top/bottom-only placement leaves mid-rack equipment cabling unmanaged.
- Horizontal and vertical managers are complementary, not mutually exclusive.

</details>

---

**Q8.** What is the primary purpose of a bend-radius manager (cable guide) in a rack cable pathway?

A) Increase EMI shielding on data cables
B) Provide rack branding and aesthetic finish
C) Eliminate the need for cable labeling
D) Prevent cable damage and signal loss by limiting how sharply a cable bends beyond its manufacturer-specified minimum radius

<details>
<summary>Answer</summary>

**Correct: D**

Bend-radius managers mechanically enforce the minimum bend radius, preventing attenuation, micro-fractures, or signal degradation in fiber and high-speed copper cabling.

**Why the others are wrong:**
- Bend-radius managers are mechanical, not EMI shielding devices.
- Aesthetics are a secondary benefit, not the exam-tested purpose.
- Labeling is a separate cable-management practice unrelated to bend radius.

</details>

---

