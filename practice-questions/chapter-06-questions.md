## Chapter 6: Fiber Installation and Transceiver Handling — Practice Questions

**Q1.** A technician is terminating an MPO trunk cable that will connect two 100G QSFP28 SR4 transceivers over multimode fiber. Which connector polish type is REQUIRED at the MPO interface?

A) APC (8-degree angled)
B) PC (physical contact, non-angled, non-flat)
C) UPC (flat polish)
D) Either APC or UPC, technician's choice

<details>
<summary>Answer</summary>

**Correct: C**

MPO connectors used with SR4/multimode transceivers are almost always UPC (blue, flat polish); APC MPO (green) is reserved for single-mode applications requiring low back reflection.

**Why the others are wrong:**
- APC is used for single-mode long-reach links, not standard SR4 multimode trunks — mating APC to a UPC-terminated port causes ferrule damage.
- PC (non-angled/non-flat generic) is not a standard MPO polish designation used in structured cabling.
- Polish type is not interchangeable — angled and flat ferrules have different geometries and cannot mate reliably.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** During a fiber audit, a technician finds a green MPO connector plugged directly into a blue-keyed MPO adapter port. What is the immediate risk of leaving this connection mated?

A) Increased insertion loss only, no physical damage
B) Automatic link renegotiation to a lower speed
C) No risk — color coding is cosmetic only
D) Ferrule face damage from angle mismatch, requiring cable replacement

<details>
<summary>Answer</summary>

**Correct: D**

APC (green, 8-degree angle) and UPC (blue, flat) ferrules have incompatible geometries; forcing them together grinds the angled face against the flat face, physically damaging both endfaces.

**Why the others are wrong:**
- The damage is physical, not just a loss penalty — the connector may become unusable.
- Optical mismatches do not trigger speed renegotiation; the link will simply fail or show high errors.
- Color coding on APC/UPC connectors is a manufacturing standard specifically to prevent this exact mismatch.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A QSFP28 transceiver is inserted into a switch port, the latch clicks, but the link/activity LED remains off after 60 seconds and both ends have been reseated once. What should the technician check NEXT?

A) Replace the switch chassis
B) Immediately RMA the transceiver as defective
C) Increase the transceiver's TX power via CLI
D) Clean the fiber endfaces and inspect with a fiber scope before re-mating

<details>
<summary>Answer</summary>

**Correct: D**

Contaminated or damaged endfaces are the most common cause of no-link after correct seating; cleaning and inspecting the connector before further troubleshooting is the standard next step.

**Why the others are wrong:**
- Chassis replacement is a last resort disproportionate to symptoms after only one reseat.
- Jumping to RMA skips the standard fault-isolation sequence (seating → cleaning/inspection → loopback test).
- TX power is not user-adjustable on standard optical transceivers and is not a valid troubleshooting step.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** A link between two data halls spans 30 km over single-mode fiber at 100G. Which transceiver type is the correct minimum-reach selection?

A) 100GBASE-SR4
B) 100GBASE-LR4
C) 100GBASE-ER4
D) 100GBASE-CWDM4

<details>
<summary>Answer</summary>

**Correct: C**

100GBASE-ER4 is rated for up to 40 km on single-mode fiber, covering the required 30 km distance; it is the correct minimum-reach option among the choices.

**Why the others are wrong:**
- SR4 is multimode-only, rated to ~70-100 m, far short of 30 km.
- LR4 is rated to 10 km on single-mode fiber, insufficient for a 30 km span.
- CWDM4 is rated to 2 km (or 10 km variants in some specs), still insufficient for 30 km.

</details>

---

**Q5.** Which distance rating is correct for a standard 100GBASE-LR4 single-mode transceiver?

A) 100 meters
B) 2 kilometers
C) 10 kilometers
D) 40 kilometers

<details>
<summary>Answer</summary>

**Correct: C**

100GBASE-LR4 is standardized for up to 10 km reach over single-mode fiber (SMF) using a single fiber pair with WDM.

**Why the others are wrong:**
- 100 meters is the multimode SR4 range, not LR4.
- 2 kilometers describes CWDM4, a lower-cost single-mode alternative to LR4.
- 40 kilometers is the ER4 rating, which requires higher TX power and often an optical amplifier.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** A technician terminates a 12-fiber MPO trunk for a breakout application where both ends use identical straight-through connectors, but internal fiber pairs are physically crossed within the cable to preserve TX/RX signal flow. Which polarity method is this?

A) Method A
B) Method B
C) Method C
D) Method D

<details>
<summary>Answer</summary>

**Correct: B**

Method B uses key-up to key-up connectors on both ends with the fiber positions reversed inside the cable, maintaining polarity without needing a flipped connector.

**Why the others are wrong:**
- Method A uses a key-up to key-down (straight) connector configuration with no internal fiber crossing.
- Method C crosses adjacent fiber pairs at the connector level (pair-flipped patch cords), not a global reversal.
- Method D is not a recognized TIA/EIA polarity method.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** Before mating a fiber-optic connector, what is the correct cleaning sequence per standard field practice?

A) Wet-clean with isopropyl alcohol only, then mate immediately
B) Blow compressed air directly on the endface, then mate
C) Dry-clean with a click-type cleaner, inspect with a fiber scope, wet-clean only if contamination persists
D) Wipe with a cotton cloth and mate without inspection

<details>
<summary>Answer</summary>

**Correct: C**

Standard practice is dry cleaning first (click cleaner or cassette cleaner), inspecting the endface under magnification, and escalating to wet cleaning with isopropyl alcohol wipes only if dry cleaning fails to remove contamination.

**Why the others are wrong:**
- Wet cleaning alone can leave residue and streaking if not followed by a dry pass, and skips inspection.
- Compressed air does not remove oils or embedded particulates and can drive debris deeper into the ferrule.
- Cotton cloth is not lint-free and will leave fibers on the endface, increasing insertion loss.

</details>

---

**Q8.** An optical transceiver is removed from a switch for temporary storage. What is the correct handling procedure?

A) Install a dust cap on the optical port and store in an ESD-safe bag
B) Place it loose in a tool bag with no protection
C) Store it with the optical port facing upward and uncovered to allow airflow
D) Wrap it in standard bubble wrap without a dust cap

<details>
<summary>Answer</summary>

**Correct: A**

Dust caps prevent contamination of the optical bore/endface, and ESD-safe bags protect the transceiver's internal electronics from static discharge during storage or transport.

**Why the others are wrong:**
- Loose storage exposes the optical interface to dust and physical damage.
- Leaving the port uncovered defeats the purpose of contamination control regardless of orientation.
- Standard bubble wrap is not ESD-rated and does not protect against static discharge; a dust cap is still required.

</details>

---

