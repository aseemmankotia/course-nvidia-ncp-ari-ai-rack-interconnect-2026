## Chapter 10: Final Inspection, Documentation, and BER Troubleshooting — Practice Questions

**Q1.** A technician completes a fiber run and the link comes up immediately at full negotiated speed, but the switch reports intermittent CRC errors that increase under load. An OTDR trace shows no fault events along the length, and cleaning both connector ends with a one-click cleaner resolves the errors for several hours before they return. What is the MOST likely root cause?

A) Contamination is being reintroduced at the connector interface (dirty adapter, cap, or patch cord end-face)
B) The fiber has a macrobend exceeding the minimum bend radius somewhere in the run
C) The transceiver is mismatched to the fiber type (single-mode optic in multimode fiber)
D) The link is experiencing a duplex mismatch at the switch port

<details>
<summary>Answer</summary>

**Correct: A**

Errors that clear after cleaning and then recur are the signature of contamination — dust or oil recontaminating the end-face or a dirty bulkhead adapter — not a fixed physical defect.

**Why the others are wrong:**
- A macrobend would show as a loss event on the OTDR trace and would not be temporarily fixed by cleaning
- A transceiver/fiber mismatch causes link-down or no-link conditions, not intermittent CRC errors that respond to cleaning
- A duplex mismatch causes late collisions and throughput issues, not something resolved by physically cleaning connectors

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** During final inspection, a candidate finds a fiber patch cord looped tightly around a cable manager post with a visible kink at the bend point. Which quality issue does this violate?

A) Minimum bend radius requirement
B) Airflow clearance requirement
C) Cable labeling requirement
D) Grounding and bonding requirement

<details>
<summary>Answer</summary>

**Correct: A**

A visible kink at a tight loop is a classic bend-radius violation, which induces macrobend attenuation and can permanently damage the glass core.

**Why the others are wrong:**
- Airflow clearance concerns equipment ventilation, not cable curvature
- Labeling concerns cable ID tags, unrelated to the physical kink described
- Grounding/bonding applies to copper/shielded cabling and chassis, not to fiber bend geometry

</details>

---

**Q3.** A newly installed 10GbE link reports a measured bit error rate of 1 x 10^-8. The link stays up and passes traffic, but the vendor's acceptance criteria requires a BER at or below 1 x 10^-12 before FEC. What should the technician do?

A) Accept the link since it is passing traffic without dropping
B) Treat this as a failed test and troubleshoot signal integrity before sign-off
C) Reboot the switch to reset the error counters and re-test
D) Increase the FEC threshold setting until the BER reads as passing

<details>
<summary>Answer</summary>

**Correct: B**

1 x 10^-8 is several orders of magnitude worse than the 1 x 10^-12 acceptance threshold; the exam treats BER against the documented pass/fail limit, not link-up status, as the acceptance criterion.

**Why the others are wrong:**
- Passing traffic does not equal meeting the BER acceptance threshold — link-up and low BER are independent conditions
- Resetting counters hides the problem temporarily; it does not fix the underlying signal-integrity issue and the error rate will reappear
- Adjusting FEC thresholds to force a pass is a documentation/procedural violation, not a valid troubleshooting step

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** Which pair of symptoms correctly differentiates a link-down condition from a high-BER condition?

A) Link-down: slow throughput; High-BER: no light detected
B) Link-down: high error counters; High-BER: interface administratively disabled
C) Link-down and high-BER always occur together and cannot be differentiated
D) Link-down: no light detected/LOS alarm; High-BER: link is up but throughput/error counters degrade

<details>
<summary>Answer</summary>

**Correct: D**

Link-down is a total loss-of-signal condition (LOS), while high BER is a degraded-but-present signal — the link negotiates and stays up but data integrity suffers.

**Why the others are wrong:**
- Swaps the definitions — slow throughput without LOS is a BER symptom, not link-down
- Also swaps the definitions incorrectly
- The two are distinct fault classes with different root causes and troubleshooting paths

</details>

---

**Q5.** A technician has cleaned all connectors, verified bend radius, re-terminated both ends, and replaced the patch cords on a link, but BER remains above threshold. What is the correct next step per standard escalation procedure?

A) Continue re-terminating the same connectors repeatedly until the BER improves
B) Mark the link as passed and let the network team monitor it post-deployment
C) Replace the entire cable run without documenting any of the prior troubleshooting steps
D) Escalate to Tier 2/engineering with the OTDR trace, test results, and steps already performed

<details>
<summary>Answer</summary>

**Correct: D**

Once standard field remediation (cleaning, bend check, re-termination) is exhausted without resolving a persistent signal-integrity fault, the documented escalation path requires handing off with full test evidence to the next tier rather than guessing further.

**Why the others are wrong:**
- Repeating the same fix without new diagnostics wastes time and is not the documented escalation step
- Signing off a link that fails the BER threshold violates the final inspection quality checklist
- Cable replacement is a valid remediation but must be documented and is typically an engineering-approved step, not a blind first move

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** Which item is a REQUIRED component of as-built documentation photo standards for a completed rack installation?

A) A photo of the rack taken before any cables were installed
B) A single wide-angle photo of the data center floor
C) A close-up photo showing cable labels legible at both ends of each run, plus an overall rack/patch panel photo
D) A photo of the technician holding the test equipment

<details>
<summary>Answer</summary>

**Correct: C**

As-built photo documentation must show legible label IDs at both cable ends along with overall panel/rack context so the installation can be verified against the as-built diagram later.

**Why the others are wrong:**
- A before-photo doesn't document the completed, labeled state required for as-built records
- A wide floor shot has no verifiable detail on labeling or termination quality
- A photo of the technician provides no documentation value for the installation itself

</details>

---

**Q7.** A rack passes cabling inspection but the technician notices patch cords bundled so tightly against the rear of an active switch that the exhaust vents are partially blocked. Under the final deployment quality checklist, this is flagged as a failure of which category?

A) Labeling
B) Airflow clearance
C) Bend radius
D) As-built accuracy

<details>
<summary>Answer</summary>

**Correct: B**

Blocked exhaust vents from cable bundling is specifically an airflow clearance failure, one of the three named checklist items (bend radius, labeling, airflow).

**Why the others are wrong:**
- Labeling concerns cable/port identification tags, not physical obstruction
- Bend radius concerns the curvature of the cable itself, not vent blockage
- As-built accuracy concerns whether documentation matches the physical install, not a physical safety/thermal issue

</details>

---

**Q8.** What is the conceptual difference between troubleshooting a signal-integrity issue caused by a dirty connector versus one caused by over-bending?

A) Dirty connectors cause permanent core damage; over-bending is always temporary and self-resolves
B) Both faults are resolved identically by rebooting the connected switch port
C) Over-bending only affects copper cabling, so it is irrelevant to fiber troubleshooting
D) Dirty connectors are resolved by cleaning and re-inspecting the end-face; over-bending requires locating and correcting/removing the excessive bend, and damage may be permanent

<details>
<summary>Answer</summary>

**Correct: D**

Contamination is a surface-level, cleanable fault, while over-bending is a physical/geometric fault requiring the bend to be found and corrected, and may have caused irreversible microfracture or attenuation.

**Why the others are wrong:**
- Reverses the facts — it's over-bending, not dirt, that can cause permanent damage
- Neither fault is fixed by a switch reboot; both are physical-layer issues
- Bend radius limits apply to fiber cabling specifically and are heavily tested for fiber, not just copper

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

