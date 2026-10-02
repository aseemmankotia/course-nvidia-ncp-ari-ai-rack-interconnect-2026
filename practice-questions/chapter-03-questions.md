## Chapter 3: Site Assessment Before Deployment — Practice Questions

**Q1.** A data center hall has a raised floor rated for 250 lbs/sq ft (1,220 kg/m²) concentrated load. A new NVIDIA GB200 NVL72 rack weighs approximately 3,000 lbs (1,362 kg) and has a footprint of roughly 0.72 m² (7.75 sq ft). What should the technician do BEFORE scheduling the install?

A) Proceed with install since the rack fits within the tile dimensions
B) Reduce power draw on the rack to lower its effective weight rating
C) Move the rack to a corner of the room where floor support is assumed to be stronger
D) Escalate to a structural engineer for a floor load assessment, since the calculated load (~387 lbs/sq ft) exceeds the floor's rated capacity

<details>
<summary>Answer</summary>

**Correct: D**

Dividing rack weight by footprint gives a concentrated load far above the floor's rating, which is a structural safety issue requiring engineering sign-off before install, not a decision the technician makes alone.

**Why the others are wrong:**
- Fitting on the tile is irrelevant — load capacity is about weight per area, not physical dimensions
- Power draw and weight are unrelated; reducing power does not change physical mass
- Corner placement is not a validated engineering solution and floor support does not vary by assumption

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** During a site survey, a technician measures 30 inches (762 mm) of clear space in front of an electrical panel operating at 120V to ground. Per NEC 110.26(A)(1) working space requirements, is this compliant?

A) Yes, 30 inches meets the minimum requirement for all voltage conditions
B) No, the minimum required working clearance is 36 inches (914 mm) for this voltage condition
C) Yes, because working clearance only applies to panels above 600V
D) No, the minimum required clearance is 48 inches regardless of voltage

<details>
<summary>Answer</summary>

**Correct: B**

NEC 110.26(A)(1) Condition 1 requires a minimum of 36 inches (914 mm) of working space in front of electrical equipment at this voltage-to-ground range.

**Why the others are wrong:**
- 30 inches is below the code minimum for this condition
- NEC working clearance applies at low voltage too — it's not exclusive to high-voltage equipment
- 48 inches is not the standard minimum for Condition 1; that figure would overstate the requirement

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A liquid-cooled AI rack requires connection to a facility Coolant Distribution Unit (CDU) before power-on. During environmental readiness verification, which check is MOST critical before the install team proceeds?

A) Confirming the rack's paint color matches other racks in the row
B) Confirming facility water loop supply temperature and flow rate meet the rack's specified operating range
C) Confirming the rack has been unboxed in a hallway near the loading dock
D) Confirming the rack ships with a printed user manual

<details>
<summary>Answer</summary>

**Correct: B**

Liquid-cooled high-density racks specify required supply water temperature and flow rate ranges; if the facility CDU cannot meet these, the rack cannot be safely powered on regardless of physical placement.

**Why the others are wrong:**
- Cosmetic details have no bearing on environmental readiness
- Unboxing location is a logistics detail, not an environmental readiness gate
- Documentation presence is part of inventory check, not thermal/cooling readiness

</details>

---

**Q4.** Before beginning physical rack installation, which document should the technician review FIRST to confirm cable pathway routing, power drop locations, and rack placement match the intended design?

A) The vendor's marketing spec sheet
B) The shipping manifest
C) The warranty registration form
D) The physical network design documentation (site-specific install drawings)

<details>
<summary>Answer</summary>

**Correct: D**

Physical network design documentation contains the site-specific layout for cable pathways, power drops, and rack positions, and must be validated against actual site conditions before install begins.

**Why the others are wrong:**
- Marketing spec sheets describe generic product capabilities, not site-specific layout
- A shipping manifest confirms what arrived, not where or how it should be installed
- Warranty forms are administrative and unrelated to physical placement

</details>

---

**Q5.** A technician needs an authoritative determination of whether a data hall's raised floor can support a new row of high-density racks. Which resource should be used to make this determination?

A) A visual inspection of the tile surface for cracks
B) A structural engineer's floor load assessment referencing the building's certified load rating
C) The rack vendor's shipping weight sticker alone
D) An estimate based on how the existing racks in the room appear to be holding up

<details>
<summary>Answer</summary>

**Correct: B**

Floor load capacity is a structural engineering determination based on the building's certified static and dynamic load ratings, not a visual or comparative judgment call.

**Why the others are wrong:**
- Visual inspection cannot detect load-bearing capacity, only surface damage
- The weight sticker gives rack weight but not whether the floor can support it
- Comparing to existing racks ignores that new racks may be significantly heavier or differently distributed

</details>

---

**Q6.** Per common data center service clearance practice, what is the typical MINIMUM rear clearance required behind high-density racks to allow for airflow and hot-swap service access?

A) 30 inches (762 mm)
B) 12 inches (305 mm)
C) 18 inches (457 mm)
D) 60 inches (1,524 mm)

<details>
<summary>Answer</summary>

**Correct: A**

30 inches (762 mm) of rear clearance is the typical vendor and industry-standard minimum for exhaust airflow and rear-access serviceability on high-density racks.

**Why the others are wrong:**
- 12 inches is far too tight for exhaust airflow or technician access
- 18 inches is still commonly insufficient for full rear panel removal and cable service
- 60 inches is excessive for rear clearance and is not the standard minimum

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** During environmental readiness verification, a cold aisle is measured at 30°C (86°F) intake temperature. Per ASHRAE Class A1 recommended (not allowable) operating range, is this within the RECOMMENDED envelope for standard IT equipment?

A) No, 30°C exceeds the ASHRAE A1 recommended range of 18-27°C, though it may still be within the wider allowable range
B) Yes, 30°C is within the ASHRAE A1 recommended range
C) No temperature above 20°C is acceptable in any data center
D) Yes, because ASHRAE only regulates humidity, not temperature

<details>
<summary>Answer</summary>

**Correct: A**

ASHRAE Class A1 defines a recommended operating range of 18-27°C; 30°C falls outside recommended (though still within the broader allowable range up to ~32°C for A1), so it should be flagged during readiness verification.

**Why the others are wrong:**
- 30°C is above, not within, the recommended (not allowable) range
- 20°C as an absolute cutoff is incorrect — ASHRAE defines a range, not a single ceiling
- ASHRAE thermal guidelines explicitly cover both temperature and humidity

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** What is the key difference between a 'site survey' and a 'site assessment' in pre-deployment planning?

A) A site survey is a physical, on-site measurement and observation activity, while a site assessment is the broader evaluation combining survey data with design and readiness documentation
B) They are interchangeable terms with no meaningful difference
C) A site survey only applies to networking, while site assessment only applies to power
D) A site assessment happens after equipment is installed, while a site survey happens before

<details>
<summary>Answer</summary>

**Correct: A**

The site survey is the hands-on data-gathering step (measuring clearances, pathways, power drops); the site assessment synthesizes survey findings with design documents and readiness criteria to determine deployment go/no-go.

**Why the others are wrong:**
- The terms describe related but distinct activities in the process, not synonyms
- Both activities span all infrastructure domains, not a single discipline
- Both occur before install — assessment does not follow installation

</details>

---

