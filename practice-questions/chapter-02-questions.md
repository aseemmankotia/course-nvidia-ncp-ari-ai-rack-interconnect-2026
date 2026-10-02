## Chapter 2: Cooling and GB200 NVL72 Rack Anatomy — Practice Questions

**Q1.** A facility is deploying GB200 NVL72 racks with a total draw of approximately 120kW per rack, but existing CRAH units are rated for only 20kW of heat rejection per rack footprint. Which addition BEST resolves this mismatch?

A) Increase CRAH fan speed and add more perforated floor tiles
B) Add hot-aisle containment only, without changing the cooling source
C) Reduce GPU clock speeds until air cooling can keep up
D) Install a Coolant Distribution Unit (CDU) to bridge the facility water loop to the rack's direct-to-chip liquid cooling loop

<details>
<summary>Answer</summary>

**Correct: D**

GB200 NVL72's ~120kW density exceeds what air cooling can economically reject; a CDU interfaces the facility chilled/condenser water loop with the rack's isolated technology cooling loop, enabling direct-to-chip liquid cooling at scale.

**Why the others are wrong:**
- Air-only remediation (fans/tiles) cannot reject 120kW/rack — physically insufficient for this density
- Containment manages airflow, not the primary cooling capacity gap at this density
- Underclocking sacrifices performance and is not a supported exam-recommended architecture solution

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** In a datacenter mixing legacy air-cooled racks with new GB200 NVL72 liquid-cooled racks in the same row, which containment strategy is generally preferred to prevent hot exhaust from high-density racks from raising ambient room temperature?

A) Cold-aisle containment, sealing only the cold aisle
B) No containment, relying on raised-floor pressure alone
C) Cold-aisle containment combined with lowering CRAH setpoint room-wide
D) Hot-aisle containment, ducting hot exhaust directly back to the CRAH return

<details>
<summary>Answer</summary>

**Correct: D**

Hot-aisle containment captures and ducts hot exhaust air directly back to the CRAH unit, keeping the rest of the room at comfortable cold-aisle temperature — preferred for high-density racks mixed with other equipment.

**Why the others are wrong:**
- Cold-aisle containment leaves hot exhaust free in the room, raising ambient temperature near high-density racks
- No containment allows hot/cold air mixing and reduces cooling efficiency significantly
- Lowering setpoint room-wide wastes energy and doesn't solve the mixing problem directly

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** You need maximum bandwidth for GPU-to-GPU all-to-all communication among all 72 GPUs within a single GB200 NVL72 rack. Which interconnect is used for this domain?

A) InfiniBand NDR at 400Gb/s per port
B) Standard Ethernet with RoCE
C) PCIe Gen5 fabric between compute trays
D) NVLink, via the NVSwitch trays within the rack

<details>
<summary>Answer</summary>

**Correct: D**

NVLink (5th generation) connects all 72 GPUs through 9 NVSwitch trays inside the rack, providing the highest intra-rack bandwidth (1.8TB/s per GPU) for all-to-all communication.

**Why the others are wrong:**
- InfiniBand is used for scale-out between racks/nodes, not the primary intra-rack GPU fabric
- Ethernet/RoCE is a scale-out or alternative fabric option, not the NVL72 intra-rack interconnect
- PCIe connects components at lower bandwidth than NVLink and is not the GPU-to-GPU fabric here

</details>

---

**Q4.** Which component sits physically between the datacenter's facility water loop and a GB200 NVL72 rack's internal technology cooling loop, managing heat exchange, flow rate, and coolant quality?

A) Rear-door heat exchanger
B) NVSwitch tray
C) Coolant Distribution Unit (CDU)
D) Power shelf

<details>
<summary>Answer</summary>

**Correct: C**

The CDU isolates and exchanges heat between the facility water system (FWS) and the rack's closed technology cooling system (TCS) loop, while also managing pressure, flow, and coolant conditioning.

**Why the others are wrong:**
- A rear-door heat exchanger is an air-assist device, not the primary facility-to-rack liquid interface for direct-to-chip cooling
- NVSwitch trays handle GPU interconnect, not cooling loop management
- Power shelves supply DC power to compute trays, unrelated to coolant loop isolation

</details>

---

**Q5.** How many NVLink Switch trays are present in a single GB200 NVL72 rack?

A) 4
B) 18
C) 9
D) 36

<details>
<summary>Answer</summary>

**Correct: C**

GB200 NVL72 contains 9 NVLink Switch trays that interconnect all 72 GPUs into a single non-blocking NVLink domain.

**Why the others are wrong:**
- 4 is too low to support the required switching bandwidth for 72 GPUs
- 18 is the number of compute trays, not switch trays — a common mix-up
- 36 corresponds to the number of Grace CPUs in the rack, not switch trays

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** A GB200 NVL72 rack has 18 compute trays. Each compute tray uses a 'Bianca' board with 2 Grace CPUs and 4 Blackwell GPUs. How many total GPUs and Grace CPUs does the full rack contain?

A) 36 GPUs, 18 Grace CPUs
B) 144 GPUs, 72 Grace CPUs
C) 18 GPUs, 36 Grace CPUs
D) 72 GPUs, 36 Grace CPUs

<details>
<summary>Answer</summary>

**Correct: D**

18 trays × 4 GPUs = 72 GPUs; 18 trays × 2 Grace CPUs = 36 Grace CPUs — the defining NVL72 configuration.

**Why the others are wrong:**
- This halves the correct counts, likely from miscounting GPUs per tray
- This doubles the correct counts, a common overcounting error
- This inverts GPU and CPU counts per tray incorrectly

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** Which statement correctly differentiates NVLink, InfiniBand, and Ethernet in a GB200 NVL72-based AI cluster?

A) InfiniBand is used only inside the rack; NVLink connects racks together for scale-out
B) NVLink connects GPUs within the rack domain at the highest bandwidth; InfiniBand or Ethernet is used for scale-out connectivity between racks/nodes
C) Ethernet replaces NVLink entirely in Blackwell-based systems
D) NVLink and InfiniBand serve identical roles and are interchangeable at the rack level

<details>
<summary>Answer</summary>

**Correct: B**

NVLink is the intra-rack, GPU-to-GPU fabric with the highest bandwidth; InfiniBand (e.g., Quantum-2 NDR) or Ethernet (e.g., Spectrum-X) handles scale-out between racks/nodes.

**Why the others are wrong:**
- This reverses the actual roles — InfiniBand/Ethernet are scale-out, not intra-rack
- Ethernet is an alternative scale-out fabric, not a replacement for NVLink's intra-rack role
- The two fabrics serve different topological purposes and are not interchangeable

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** A team is validating a new GB200 NVL72 deployment before go-live. Which check is MOST directly relevant to confirming the liquid cooling infrastructure is adequate for the rack?

A) Confirming the CDU's rated heat rejection capacity meets or exceeds the rack's total power draw (~120kW)
B) Confirming the number of NVLink switch trays matches the GPU count
C) Confirming hot-aisle containment doors close automatically on fire alarm
D) Confirming Ethernet switch firmware is up to date

<details>
<summary>Answer</summary>

**Correct: A**

Since nearly all power drawn becomes heat, the CDU's rated cooling capacity must match or exceed the rack's total power draw to prevent thermal throttling or shutdown.

**Why the others are wrong:**
- NVLink switch count is a compute/interconnect concern, not a cooling capacity validation
- Fire-safety compliance is important but not a cooling-capacity verification step
- Ethernet firmware relates to networking, not thermal capacity

</details>

---

