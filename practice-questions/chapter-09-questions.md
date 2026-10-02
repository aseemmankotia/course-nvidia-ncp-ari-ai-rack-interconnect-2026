## Chapter 9: Continuity and Link Testing — Practice Questions

**Q1.** A technician runs an optical power meter test on a newly installed OM4 multimode fiber link and measures 4.8 dB total loss, but the calculated link loss budget for this run is 2.9 dB. What should the technician do NEXT?

A) Inspect and clean the connectors, re-terminate if needed, and re-test before escalating
B) Mark the link as passing since fiber links tolerate loss above budget
C) Immediately replace the switch port transceiver without re-testing the cable
D) Log the result as passed and proceed to the post-install verification pass

<details>
<summary>Answer</summary>

**Correct: A**

Excess loss above the calculated budget is most often caused by dirty or poorly terminated connectors; TIA-568.3-D procedure requires inspection/cleaning and re-test before condemning cable or hardware.

**Why the others are wrong:**
- A measured loss exceeding budget is a fail condition, not an acceptable variance
- Replacing the transceiver skips the required troubleshooting sequence and wastes hardware
- Logging a failing measurement as passed falsifies the test record

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** During diagnostics, a technician runs `mlxlink -d mlx5_0 -m` to identify a suspect cable before an RMA is filed. Which output field is used to confirm whether the cable is NVIDIA-certified versus a third-party cable?

A) Vendor Name / Vendor Part Number field from the cable EEPROM
B) Cable temperature reading
C) Link speed negotiated on the port
D) The switch port number the cable is plugged into

<details>
<summary>Answer</summary>

**Correct: A**

The cable EEPROM stores vendor identity data (Vendor Name/PN) readable via mlxlink or ethtool -m; this is the authoritative field for confirming NVIDIA LinkX origin versus a non-NVIDIA cable.

**Why the others are wrong:**
- Temperature indicates operating condition, not cable origin
- Negotiated link speed is a capability match, not vendor identity — a non-NVIDIA cable can still negotiate the same speed
- Port number is a physical location identifier, unrelated to cable vendor

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A data center is running structured cabling installation. Which sequence correctly reflects proper pre-test vs post-install test order?

A) Test only after full rack installation and cable management is complete
B) Post-install test first to save time, then pre-test only if the post-install test fails
C) Bare-fiber/reel test before installation, then a full end-to-end test after termination and installation
D) Pre-test and post-install test are interchangeable and either order is acceptable

<details>
<summary>Answer</summary>

**Correct: C**

Standard practice tests raw cable/reel integrity before installation (catches manufacturing defects early), then re-tests the complete terminated link after install to capture connector and routing-induced loss.

**Why the others are wrong:**
- Skipping pre-test risks installing a defective cable and wasting labor
- Reversing the order means defects are found only after full installation, increasing rework cost
- The order matters because each stage catches different fault categories

</details>

---

**Q4.** Which command-line tool is used specifically to check InfiniBand physical link status (LinkUp/LinkDown/Polling states) on a host with a Mellanox/NVIDIA HCA?

A) ethtool
B) nvidia-smi
C) traceroute
D) ibstat

<details>
<summary>Answer</summary>

**Correct: D**

ibstat reports InfiniBand port physical and logical link state (e.g., LinkUp/Active) directly from the HCA driver.

**Why the others are wrong:**
- ethtool reports Ethernet NIC link status, not native InfiniBand port state
- nvidia-smi reports GPU status/utilization, not network link state
- traceroute tests Layer 3 path reachability, not physical link state

</details>

---

**Q5.** Which tool reads the SFP/QSFP transceiver or DAC cable EEPROM on a Linux Ethernet host to expose vendor name, part number, and revision?

A) ip link show
B) ping -f
C) ethtool -m <interface>
D) iperf3

<details>
<summary>Answer</summary>

**Correct: C**

ethtool -m dumps the module EEPROM data (vendor, part number, serial, DOM info), which is used to confirm cable authenticity and specs.

**Why the others are wrong:**
- ip link show only shows interface state/MTU/MAC, not module EEPROM data
- ping -f is a flood ping for reachability/loss testing, unrelated to module identity
- iperf3 measures throughput, not module identity data

</details>

---

**Q6.** A copper DAC cable fails a continuity test with an open detected on pin 4 of one connector. What does this result indicate?

A) The cable has excessive optical insertion loss
B) The cable has a broken conductor or bad termination on that pin and must be replaced
C) The link is up but running at reduced speed
D) The switch port needs a firmware update

<details>
<summary>Answer</summary>

**Correct: B**

An 'open' on continuity testing means no electrical path exists on that conductor — a physical break or termination fault that requires cable replacement.

**Why the others are wrong:**
- Optical insertion loss applies to fiber, not copper conductor continuity
- A continuity open prevents proper signaling; the port would not show a normal reduced-speed link, it would typically show link down or errors
- Firmware does not resolve a physical conductor fault

</details>

---

**Q7.** During a verification pass, which of the following MUST be included in the test documentation log for audit/traceability purposes?

A) Only the pass/fail result
B) Only the switch model number
C) Cable ID, connector locations, measured value (loss/continuity result), test equipment used, technician, and timestamp
D) Only a photo of the rack

<details>
<summary>Answer</summary>

**Correct: C**

Complete traceable documentation requires cable identifier, endpoints, the actual measured value, the equipment/calibration reference, who performed it, and when — a bare pass/fail is insufficient for audit.

**Why the others are wrong:**
- Pass/fail alone lacks traceability and measured evidence needed for troubleshooting or audits
- Switch model alone does not identify the specific cable run tested
- A photo alone provides no measured data or identifiers

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** In link status terminology, what does a 'Link Down' state most precisely indicate, as opposed to 'Polling' or 'Disabled'?

A) The port is administratively shut down by configuration
B) The port is actively negotiating speed and will come up shortly
C) No physical layer connection has been established/negotiated between the two ends
D) The link is up but experiencing high symbol error rate

<details>
<summary>Answer</summary>

**Correct: C**

Link Down specifically means the physical layer link has not been established — distinct from an admin-disabled port or a port still in the polling/negotiation phase.

**Why the others are wrong:**
- Administrative shutdown is typically reported as a distinct 'Disabled' state, not generic Link Down
- Polling is an active negotiation state, not yet a final down/up determination
- High symbol errors occur on an established (up) link, which is a different diagnostic condition than down

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

