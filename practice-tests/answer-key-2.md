# Answer Key — Practice Test 2

**Q1. Correct: A**

N+1 redundancy requires installed spare shelf capacity beyond the calculated N shelves needed to carry the full load, verified by an actual failover load test — not just paper capacity math.

---

**Q2. Correct: D**

The GB200 NVL72 reference architecture takes facility 3-phase AC into in-rack power shelves that rectify it to 48V DC, which is then distributed to compute trays via a DC busbar — this is the defining feature that makes it a 'DC rack' at the distribution level.

---

**Q3. Correct: C**

NVLink (via the NVLink Switch trays) forms the scale-up domain joining all 72 GPUs in the rack, while InfiniBand is the scale-out fabric that links multiple NVL72 racks into a larger cluster.

---

**Q4. Correct: D**

Even load distribution across all three phases, with rotated phase assignment between A-side and B-side rPDUs, minimizes phase imbalance and ensures a single-phase loss doesn't drop redundant power to any device.

---

**Q5. Correct: B**

A well-functioning CDU heat exchanger typically has only a small approach temperature (roughly 2–3°C) between facility supply and TCS supply; an 8°C gap points to reduced facility water flow, a fouled plate heat exchanger, or a valve/control issue that needs troubleshooting before production load.

---

**Q6. Correct: C**

Dissimilar metals in contact within a conductive coolant path create a galvanic corrosion risk; dielectric isolation or proper bonding at these joints, combined with standard rack-to-facility ground continuity, prevents both corrosion and electrical hazards.

---

**Q7. Correct: D**

Phase imbalance on a three-phase rPDU is corrected by physically redistributing which outlets (and therefore which IT loads) are wired to L1, L2, and L3, spreading current draw evenly across all three phases rather than modifying breaker ratings or the power topology.

---

**Q8. Correct: C**

The CDU performs heat exchange and fluid isolation between the primary facility water loop and the secondary TCS loop that feeds coolant directly to the compute tray cold plates in the NVL72 architecture, while also managing flow, pressure, and leak detection for the secondary loop.

---

**Q9. Correct: B**

The GB200 NVL72 rack uses dedicated NVLink Switch trays in the middle of the rack to create a single unified 72-GPU NVLink domain, giving every GPU direct all-to-all connectivity at NVLink speeds within the rack boundary.

---

**Q10. Correct: B**

Site assessment requires converting rack weight to actual floor loading (kg/m²) based on footprint and comparing it against the documented floor rating; ~2,500 kg/m² more than doubles the 1,200 kg/m² rating, so structural verification and possible reinforcement or slab mounting must occur before install, not after.

---

**Q11. Correct: C**

Site surveys for cable-management infrastructure must validate physical separation from liquid-carrying lines to prevent leak-related damage; a documented violation must be remediated (reroute or add protective separation) and the readiness report updated before installation proceeds.

---

**Q12. Correct: A**

Environmental readiness verification is the step in the site assessment process specifically focused on confirming power, cooling capacity, thermal zone design, and containment match the rack's rated TDP before installation.

---

**Q13. Correct: A**

In an A/B (2N) redundant power architecture, each independent feed must be sized to carry the full rack load on its own so that a single feed failure does not cause a derate or outage; verifying this independent full-load capacity per feed is a core pre-deployment power readiness check.

---

**Q14. Correct: A**

Inventory checks must cross-reference received cable specifications against the site survey's measured cable-run distances; a reach mismatch on active optical cables is a functional issue that will cause link failure or non-compliant BER performance if installed, so it requires escalation before deployment proceeds.

---

**Q15. Correct: D**

High-density liquid-cooled AI racks like the GB200 NVL72 require a full-body service zone at the rear (typically 1200 mm) so a technician can kneel, extend tools, and safely disconnect/reconnect quick-disconnect coolant lines and busbar connections without contorting around adjacent rack rear posts.

---

**Q16. Correct: A**

EMI mitigation best practice for high-density AI racks is physical separation of power and signal pathways — using dedicated vertical ducts or a grounded metallic divider — because optical/copper data links routed parallel to high-current DC busbars are susceptible to induced noise and crosstalk regardless of cable jacket material.

---

**Q17. Correct: A**

Standard fiber-optic handling practice (and NVIDIA cable installation guidance) specifies an unloaded/static minimum bend radius of approximately 20x the cable's outer diameter to prevent micro-bend attenuation and long-term fiber fatigue; under tension/loaded conditions this is tighter than the loaded minimum (~10x), so the manager must be sized for the larger static value.

---

**Q18. Correct: C**

GB200 NVL72 racks are extra-wide compared to standard 19-in EIA racks and include side cable channels and rear liquid-cooling infrastructure; reusing legacy air-cooled rack spacing typically leaves inadequate front-post-to-front-post and rear-post-to-rear-post clearance for cable routing, door swing, and CDU/manifold servicing, requiring the row layout to be re-measured and re-spaced per the platform's site-prep spec.

---

**Q19. Correct: D**

Front-post-to-front-door clearance is a fixed mechanical/service requirement, not a tunable or negotiable parameter — if the surveyed clearance falls short of spec, the row layout or containment placement must be corrected before rack installation proceeds, otherwise compute/switch trays cannot be fully withdrawn for service later.

---

**Q20. Correct: B**

Single-mode fiber with LR/FR transceivers supports reaches well beyond 100m (typically up to several kilometers), making it the only option in the list capable of reliably spanning a 150m run at NDR speeds.

---

**Q21. Correct: B**

At a 2m reach, passive copper DAC fully supports NDR speeds without the added power consumption or cost of active electronics or optics, making it the correct choice for short adjacent-rack links.

---

**Q22. Correct: A**

NVIDIA cabling guidance specifies a minimum bend radius of approximately 30 mm for high-density copper and fiber cabling to prevent attenuation increases, connector stress, and physical damage.

---

**Q23. Correct: B**

The 50/50 left-right routing strategy evenly distributes cable volume and weight across both trays, preventing airflow obstruction and avoiding overfilling any single tray, which is the documented best practice for high-density racks.

---

**Q24. Correct: C**

APC (Angled Physical Contact) connectors use an 8-degree angled ferrule polish, are color-coded green, and reduce back reflection, while UPC (Ultra Physical Contact) connectors use a flat polish and are color-coded blue.

---

**Q25. Correct: D**

Proper procedure requires an inspect-clean-inspect cycle using a fiber-optic microscope or scope to confirm the end-face is free of residue or contamination before mating; skipping this verification step allows undetected debris to cause elevated BER.

---

**Q26. Correct: C**

ACC uses embedded active signal-conditioning ICs at each end to overcome copper signal loss at NDR speeds, extending usable reach to roughly 5-7m while remaining an all-copper assembly, meeting the copper-only requirement.

---

**Q27. Correct: D**

OSFP (Octal Small Form-factor Pluggable) is the standard form factor for NDR 400Gb/s InfiniBand ports, providing the electrical lane density and thermal envelope needed for 400G optics and copper assemblies.

---

**Q28. Correct: C**

NVIDIA high-density fiber installation guidance specifies a minimum bend radius of approximately 30mm; tighter bends risk microbending loss and fiber breakage, while this value balances cable routing density with signal integrity.

---

**Q29. Correct: B**

At NDR speeds, SR8 multimode transceivers are limited to roughly 50-100m depending on OM4/OM5 grade, so a 500m run requires single-mode fiber paired with long-reach (LR) transceivers, which are rated for distances up to several kilometers.

---

**Q30. Correct: B**

The 50/50 strategy splits the port panel physically in half, sending the left-half ports to the left cable channel and the right-half ports to the right channel, minimizing cable crossing, balancing weight distribution, and simplifying dressing and future service.

---

**Q31. Correct: D**

APC connectors use an 8-degree angled end-face polish while UPC connectors use a flat polish; mating the two creates a physical air gap at the interface, causing excessive back reflection and insertion loss that degrades or breaks the optical link.

---

**Q32. Correct: C**

At NDR (400Gb/s) speeds, only SMF paired with DR4/FR4-class transceivers reliably supports an 80-meter run, with typical reach up to 2 km. This is the only option whose supported distance actually covers the required 80 meters.

---

**Q33. Correct: B**

APC and UPC connectors have physically incompatible ferrule end-face geometries (8-degree angled vs. flat). Mating them causes poor physical contact, excessive insertion/return loss, and can permanently damage the ferrule end faces. NVIDIA cabling practice requires matching polish types, verified visually by the standard color coding (green for APC, blue for UPC).

---

**Q34. Correct: D**

Extreme AI-cluster cable loads require engineered trapeze/ladder rack systems whose load rating is verified for the actual span, and support spacing must be tightened (shorter intervals) beyond standard practice when loads approach or exceed the rack's per-foot rating to control sag and prevent long-term deformation of connectors and jackets.

---

**Q35. Correct: A**

Load ratings for cable support hardware are span-dependent — doubling the support spacing significantly increases deflection and bending stress on the rack (and on the cables it carries) even though the total weight is unchanged, so the published lbs/ft rating cannot be applied at a different, wider spacing without re-engineering.

---

**Q36. Correct: A**

A service loop's core weight-management function is mechanical decoupling: it isolates the connector/transceiver from tension and lateral movement caused by tray flex, thermal expansion, or bundle settling, preventing premature optical/electrical failure and physical damage at the most fragile point in the link.

---

**Q37. Correct: C**

A jump in insertion loss versus a known factory baseline almost always traces to something introduced during field installation — a contaminated end-face, a stress point/micro-bend, or a poor mechanical mating. Standard procedure is to inspect and clean the connectors with a fiber scope and re-test the OPM reading before ever connecting active optics, avoiding damage from a dirty or degraded link.

---

**Q38. Correct: A**

A LinkUp state with an elevated effective BER and high raw error counts on a DAC is a classic signature of a cable that cannot meet the signal-integrity budget for its rated speed/reach — commonly a non-NVIDIA-validated or mismatched-reach assembly. The correct fix is replacing it with a certified NVIDIA LinkX cable of the appropriate specification, not a switch-level or config-level change.

---

**Q39. Correct: D**

Recording the cable serial number and NVIDIA LinkX part number per link, tied to a specific port location, lets future technicians instantly confirm whether an installed cable is NVIDIA-validated, check it against known-defective lot numbers, and swap the exact physical asset when troubleshooting BER or link-down events — none of which is possible from a plain connectivity map alone.

---

**Q40. Correct: A**

Fiber cabling has two distinct minimum bend-radius requirements: a tighter, at-rest/installed radius (commonly ~10x outer diameter) and a larger radius required while the cable is under tension or being pulled (commonly ~20x outer diameter), because pulling tension combined with a sharp bend causes micro-fractures and attenuation that may not show up until the link is stressed later.

---

**Q41. Correct: C**

A link that never trains (stuck cycling Polling/Training) is a fundamentally different failure mode from a link that is up but has degraded BER, and the fastest, least disruptive way to isolate the failing component is a known-good swap: move the suspect optic/cable to a verified-good port, or insert a known-good cable into the suspect port. If the fault follows the cable/optic, it's the cable; if it stays with the port, it's the switch side.

---

**Q42. Correct: D**

OSHA and NFPA 70E LOTO procedures require an explicit 'try' step (test-before-touch) using a rated meter that is verified live-dead-live, because switchgear can fail closed, be backfed, or have capacitive storage even after the disconnect is opened and locked.

---

**Q43. Correct: B**

NEC Article 800.113 requires plenum-rated (CMP) cable in environmental air spaces such as return-air plenums because it has the lowest flame spread and smoke production, preventing toxic smoke from circulating through the HVAC return path during a fire.

---

**Q44. Correct: B**

NFPA 70E requires an arc-flash risk assessment (incident energy analysis) specific to the equipment; the resulting label specifies the required PPE category. Voltage alone does not determine incident energy, since fault current, clearing time, and bus configuration all affect the arc-flash hazard.

---

**Q45. Correct: A**

High-speed DAC/AOC interconnect cabling standards, including NVIDIA's installation guidance, specify a minimum bend radius of roughly 10x the cable's outer diameter to avoid micro-fractures in fiber strands or impedance discontinuities in copper pairs that degrade BER and can void warranty coverage.

---

**Q46. Correct: B**

ANSI/ESD S20.20 requires a wrist strap with a built-in ~1 MΩ resistor to safely bleed off static charge while limiting current in the event of accidental contact with a live circuit, combined with a grounded ESD mat to control charge on the work surface — this protects both the technician and the sensitive component.

---

