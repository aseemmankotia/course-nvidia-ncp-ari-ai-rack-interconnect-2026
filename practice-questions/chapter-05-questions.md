## Chapter 5: Cable and Transceiver Selection — Practice Questions

**Q1.** A high-density AI cluster connects two NVIDIA Quantum-2 switches at NDR (400Gb/s) within the same rack, with a cable run of 1.2 meters. Cost per link is the primary constraint and no active signal boosting is required. Which cable type BEST meets these requirements?

A) Active Optical Cable (AOC)
B) Active Copper Cable (ACC)
C) Passive Direct Attach Copper (DAC)
D) SMF transceiver pair with LC patch cable

<details>
<summary>Answer</summary>

**Correct: C**

At 1.2m, passive DAC is well within the ~2m signal-integrity limit for NDR (400Gb/s, 8x50G PAM4) and is the lowest-cost option with no electronics required.

**Why the others are wrong:**
- AOC is unnecessary and more expensive for a sub-2m in-rack run with no distance requirement.
- ACC adds cost for active equalization that isn't needed at this short reach.
- Fiber transceivers plus patch cable are far more expensive and add unneeded optical complexity for a 1.2m link.

</details>

---

**Q2.** An engineer needs to run an NDR (400Gb/s) InfiniBand link between two adjacent racks, a distance of 5 meters. Passive copper is out of specification at this length for NDR signaling. Which cable type should be selected?

A) Passive DAC rated for 5m
B) Active Copper Cable (ACC)
C) OM3 MMF patch cable with no transceivers
D) QSFP56 breakout cable

<details>
<summary>Answer</summary>

**Correct: B**

ACC extends usable copper reach at NDR speeds to roughly 5m by adding active equalization/re-timing electronics at each end, avoiding the cost of optics.

**Why the others are wrong:**
- Passive DAC at NDR signaling rates is only reliable to about 2m; a 5m passive run exceeds spec and will cause link errors.
- Bare fiber with no transceivers cannot carry an electrical signal and is not a valid standalone solution.
- A breakout cable changes port fan-out, not signal integrity at distance; it does not solve the reach problem.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** Which transceiver form factor is required to support NVIDIA XDR (800Gb/s) InfiniBand port speeds?

A) OSFP
B) QSFP56
C) QSFP-DD
D) SFP-DD

<details>
<summary>Answer</summary>

**Correct: A**

OSFP's larger mechanical envelope provides the higher thermal dissipation headroom needed to support 800G optics/electronics, and it is the form factor NVIDIA uses for NDR and the higher-power XDR generation.

**Why the others are wrong:**
- QSFP56 tops out around 200Gb/s (NDR200) per port and lacks the lane count/power budget for 800G.
- QSFP-DD is commonly used for 400G Ethernet but has a lower thermal envelope than OSFP, making it unsuitable for the highest-power 800G optics NVIDIA deploys.
- SFP-DD is a single/dual-lane low-speed form factor, far below the density required for 800G.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** Which statement correctly differentiates multimode fiber (MMF) from single-mode fiber (SMF) in an NVIDIA high-density cabling design?

A) MMF uses laser diodes and supports 40km links; SMF uses VCSELs and is limited to short reach
B) MMF uses VCSEL-based optics with shorter reach and lower cost; SMF uses laser-diode optics with longer reach and higher cost
C) MMF and SMF have identical reach but differ only in connector type
D) SMF is always cheaper than MMF because it uses a smaller core diameter

<details>
<summary>Answer</summary>

**Correct: B**

MMF (OM3/OM4) uses inexpensive VCSEL transceivers for short reach (tens to ~100m), while SMF uses more expensive laser-diode-based optics enabling reach from 500m up to 40km depending on the optic (DR/FR/LR/ER).

**Why the others are wrong:**
- This reverses the technology pairing — VCSELs are used for MMF, not SMF, and 40km is an SMF capability, not MMF.
- Reach differs significantly between the two fiber types; connector type is not the distinguishing factor.
- SMF optics are generally more expensive than MMF optics due to tighter laser tolerances, not cheaper.

</details>

---

**Q5.** A design requires connecting compute nodes to a leaf switch across three rows of racks, approximately 30 meters, using multimode fiber. Which cable type is appropriate for this distance at high port speed?

A) Active Optical Cable (AOC) with OM4 fiber
B) Passive DAC
C) Active Copper Cable (ACC)
D) SFP+ with Cat6a copper

<details>
<summary>Answer</summary>

**Correct: A**

AOC integrates transceivers on each end of an MMF cable and reliably reaches up to ~30m, making it the standard choice for medium-distance high-speed links where copper reach limits are exceeded.

**Why the others are wrong:**
- Passive DAC cannot reliably signal beyond roughly 2m at high port speeds and is invalid at 30m.
- ACC extends copper reach to only about 5m at NDR speeds, well short of 30m.
- SFP+ over Cat6a is a low-speed Ethernet solution, not applicable to high-density InfiniBand/high-speed fabric design.

</details>

---

**Q6.** During a rack audit, a technician discovers a third-party DAC cable installed between an NVIDIA ConnectX-7 NIC and a Quantum-2 switch port. What is the MOST likely operational impact?

A) No impact — all DAC cables are fully interoperable regardless of vendor
B) The switch firmware may log the cable as unqualified/unrecognized, and NVIDIA support and cable diagnostics may not be honored
C) The link speed will automatically upgrade to XDR
D) The cable will physically fail to insert into the port

<details>
<summary>Answer</summary>

**Correct: B**

NVIDIA validates cables/transceivers via an identification EEPROM. Non-NVIDIA-branded (non-LinkX) cables can insert and sometimes link but are typically flagged as unqualified in logs, and NVIDIA support/warranty coverage and full diagnostic reporting are not guaranteed.

**Why the others are wrong:**
- Cable interoperability is not guaranteed — signal integrity, EEPROM identification, and support coverage differ by vendor.
- Cable vendor has no effect on negotiated link speed capability; speed is determined by hardware/cable rating, not brand.
- Mechanically, most third-party DAC cables use the same connector standard and will physically insert.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** An NVIDIA Quantum-2 (NDR) switch port needs to be split to connect two separate lower-speed hosts. What is the maximum number of independent 200Gb/s (NDR200) links a single 400Gb/s NDR port can be split into using a Y-cable/splitter?

A) 1
B) 4
C) 2
D) 8

<details>
<summary>Answer</summary>

**Correct: C**

An NDR (400Gb/s) port uses 8 lanes; a splitter cable divides these into two groups of 4 lanes, producing two independent NDR200 (200Gb/s) links.

**Why the others are wrong:**
- A value of 1 describes an unsplit port, not a splitter configuration.
- 4-way splitting would require splitting to 2 lanes per link (100Gb/s), which is not the standard NDR200 splitter configuration.
- 8-way splitting would leave a single lane per link, which does not match NDR's PAM4 lane-group breakout design.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** A cluster architect must choose between OSFP and QSFP-DD transceivers for a 400Gb/s Ethernet fabric where switch port density and lower per-port power draw are the top priorities. Which form factor BEST fits this requirement?

A) OSFP, because it has the largest thermal envelope
B) SFP-DD, because it natively supports 400Gb/s
C) Both are functionally identical and interchangeable in the same cage
D) QSFP-DD, because it has a smaller footprint enabling higher port density and lower power per port

<details>
<summary>Answer</summary>

**Correct: D**

QSFP-DD's smaller mechanical size allows higher switch face-plate port density and generally lower power draw per port compared to OSFP, making it the preferred choice when density and power efficiency at 400G are prioritized over the highest thermal headroom.

**Why the others are wrong:**
- A larger thermal envelope benefits highest-power (e.g., 800G) optics, not density or lower power draw — this describes the wrong priority for the stated requirement.
- SFP-DD is a low-lane-count form factor and does not support 400Gb/s.
- OSFP and QSFP-DD are mechanically different and not interchangeable in the same cage without an adapter, and even then only in one direction.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

