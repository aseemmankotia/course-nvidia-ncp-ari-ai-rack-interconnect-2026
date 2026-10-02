# Answer Key — Practice Test 1

**Q1. Correct: C**

GB200 NVL72 racks use a DC power architecture: facility AC is converted by power shelves into 48V DC, which is then distributed to compute and switch trays via a busbar — this is the defining characteristic of a DC rack versus a traditional AC rack that uses per-outlet rPDUs.

---

**Q2. Correct: B**

Intelligent rPDUs report per-phase current draw so technicians can redistribute equipment power cords across L1, L2, and L3, preventing any single phase from being overloaded while total capacity remains sufficient.

---

**Q3. Correct: B**

2N (also called N+N) redundancy provides two completely independent power paths — separate PDUs, separate upstream UPS/feeds — each capable of carrying the full rack load, so failure of an entire path does not interrupt operation.

---

**Q4. Correct: C**

The CDU sits between the facility (primary) water loop and the rack's technology (secondary) cooling loop, using a heat exchanger to isolate the two while continuously monitoring flow, pressure, temperature, and leak status for the liquid-cooled rack.

---

**Q5. Correct: A**

Proper grounding verification requires an actual resistance measurement between the rack chassis and the building ground system using a ground resistance meter, confirming the bond meets the facility's specified maximum resistance — a visual check alone is insufficient.

---

**Q6. Correct: B**

In the GB200 NVL72 architecture, NVLink (via NVLink Switch trays) forms the rack-scale GPU-to-GPU domain across all 72 GPUs, InfiniBand (e.g., Quantum-2 NDR) provides scale-out connectivity between racks/pods, and Ethernet is used for management and storage/east-west traffic.

---

**Q7. Correct: B**

Intelligent rPDUs provide per-phase (and often per-outlet) current metering specifically so load can be balanced evenly across all three phases. Even distribution across L1, L2, and L3 prevents any single phase from being overloaded while the others sit underutilized, which is the core purpose of load balancing on three-phase AC racks.

---

**Q8. Correct: D**

The CDU sits between the facility water system and the rack's technology cooling system (TCS) loop, providing a physical/hydraulic isolation point while actively monitoring and regulating flow rate, supply pressure, and coolant temperature delivered to the GPU/CPU cold plates.

---

**Q9. Correct: A**

NVLink, switched through NVSwitch trays, is purpose-built to connect the 72 GPUs in an NVL72 rack into a single high-bandwidth, low-latency, all-to-all memory domain. It vastly exceeds PCIe and Ethernet bandwidth for this intra-rack GPU-to-GPU role, which is exactly why NVL72 uses it for the rack-scale domain.

---

**Q10. Correct: A**

Structural floor load verification is a foundational physical-readiness check that must be confirmed before a multi-ton rack can be safely rolled in and positioned; failing this check can halt or damage the deployment before any electrical or network work begins.

---

**Q11. Correct: B**

Site surveys must verify rack spacing meets minimum clearance requirements for technician access, cable management, and CDU/manifold servicing; inadequate cold aisle clearance is a common deficiency that must be identified and remediated before installation to avoid rework.

---

**Q12. Correct: B**

The physical network design documentation, produced during site planning, specifies exact port mappings, cable lengths, and connectivity topology; it is the authoritative reference technicians must follow to install cabling correctly and avoid mis-wiring the fabric.

---

**Q13. Correct: D**

Environmental readiness verification requires that facility power capacity meet or exceed the rack's rated electrical draw for each redundant feed; an amperage shortfall (60A available vs. 63A required) is a hard failure that must be remediated by upgrading circuits before the rack can be safely installed and energized.

---

**Q14. Correct: A**

The inventory-check procedure exists to reconcile physically received items (racks, cables, transceivers, accessories) against the planned bill of materials, ensuring nothing is missing or damaged before installation work starts, which prevents delays mid-deployment.

---

**Q15. Correct: D**

NVIDIA's rack preparation guidance for GB200 NVL72 extra-wide racks specifies approximately 1200 mm (47 in) of front clearance so the cabinet door can fully open and compute/switch trays can be serviced or hot-swapped without obstruction.

---

**Q16. Correct: B**

Rack preparation guidance requires dedicated, separated pathways (e.g., vertical duct for power on one side, horizontal duct for data on the other) with a specified minimum lateral separation to reduce electromagnetic interference that can degrade high-speed InfiniBand/fiber signal integrity.

---

**Q17. Correct: C**

A bend-radius manager, often called a waterfall guide, is specifically designed to support cables through directional transitions (such as vertical-to-horizontal) while maintaining the cable's minimum bend radius, preventing signal loss or physical damage.

---

**Q18. Correct: B**

Industry cabling standards (aligned with TIA-568 practices referenced in rack preparation guidance) specify a minimum bend radius of approximately 10x the cable's outer diameter when unloaded and 15x when under tension, to prevent attenuation increases and physical fiber damage.

---

**Q19. Correct: D**

Front-post-to-rear-post clearance is an internal rack dimension ensuring adequate depth for power whips, CDU manifold connections, and cable routing behind compute trays so components fit without physical interference or airflow obstruction.

---

**Q20. Correct: C**

400G-FR4 optics are rated for up to 2 km over single-mode fiber, comfortably covering the 1.5 km run.

---

**Q21. Correct: B**

OSFP has a larger form factor with better thermal dissipation, allowing it to support the higher-power optics required for NDR/XDR speeds.

---

**Q22. Correct: A**

NVIDIA specifies a minimum bend radius of approximately 30 mm for high-density fiber cabling to prevent signal attenuation and physical fiber damage.

---

**Q23. Correct: D**

Active Copper Cables (ACC) include signal-conditioning electronics that extend reach beyond passive DAC limits, typically covering the 5-7 meter range at NDR speeds while remaining copper.

---

**Q24. Correct: C**

Splitting cabling evenly between the left and right sides of the rack prevents overloading one side, keeps airflow paths clear, and makes individual cables easier to trace and service.

---

**Q25. Correct: C**

APC and UPC connectors have different end-face geometries; mating them together creates a poor physical contact that increases insertion loss and can chip or damage the ferrule, so they must never be mixed.

---

**Q26. Correct: D**

At NDR (400Gb/s) speeds, MMF reach is limited to well under 70m, and copper DAC/ACC cables are only rated for a few meters (DAC ~3m, ACC ~5-7m). SMF paired with OSFP transceivers operating at 1310nm supports the long reach needed for inter-row/switch connections at NDR/XDR speeds.

---

**Q27. Correct: A**

OSFP (Octal Small Form Factor Pluggable) provides the higher lane count and thermal dissipation capability required for NDR/XDR InfiniBand speeds used in GB200 NVL72 switch trays.

---

**Q28. Correct: A**

NVIDIA specifies a minimum bend radius of approximately 30mm for high-density cabling; bending tighter than this can cause fiber micro-fractures/signal loss or damage copper conductors and connectors.

---

**Q29. Correct: B**

APC connectors require cleaning tools designed for their 8-degree angled polish, followed by inspection under a fiber-optic microscope to confirm the end-face is free of contamination or scratches before mating.

---

**Q30. Correct: A**

Industry and NVIDIA cabling convention uses yellow jackets with green APC connectors for SMF, and aqua/OM4 jackets with blue UPC/PC connectors for MMF, allowing quick visual identification during installation.

---

**Q31. Correct: D**

The 50/50 left-right routing strategy evenly distributes cable bundles across both sides of the rack, balancing mechanical weight load and preventing airflow obstruction on any single side, which is critical in high-density liquid-cooled racks.

---

**Q32. Correct: C**

At 300 meters, only single-mode fiber (SMF) paired with DR4 (up to ~500m) or FR4 (up to ~2km) rated OSFP transceivers has the optical budget to support NDR speeds over that distance.

---

**Q33. Correct: D**

NVIDIA high-density fiber cabling guidance specifies a minimum bend radius of approximately 30 mm for fiber-optic cabling to avoid microbending losses and physical damage to the fiber core.

---

**Q34. Correct: C**

Ultra-high-density AI clusters require an engineered support system sized to the actual calculated cable load, not an ad hoc solution. Trapeze/ladder racks are structurally rated for heavy bundled loads and their support spacing must be validated against the calculated weight per section.

---

**Q35. Correct: C**

Trapeze/ladder racks use rung-style construction supported at regular structural intervals, giving them the load rating needed to carry heavy bundled AI cluster cabling (power whips plus dense InfiniBand/AOC bundles) safely across a row.

---

**Q36. Correct: B**

Service loops are planned slack intended to accommodate future MACs (moves, adds, changes)—allowing a connector to be re-terminated, relocated to an adjacent port, or repaired without pulling a brand-new cable run through the support structure.

---

**Q37. Correct: B**

Contaminated or dirty connector end-faces are the most common and least invasive cause of link-up-but-high-BER symptoms. Inspection and cleaning is the standard first troubleshooting step before more drastic hardware changes.

---

**Q38. Correct: A**

An optical power meter measures transmit/receive optical power in dBm, which is compared against the transceiver's specified operating range to verify link quality.

---

**Q39. Correct: D**

The widely accepted industry standard for installed, at-rest fiber optic cable is a minimum bend radius of 10x the cable's outer diameter, to prevent microbending loss and long-term signal degradation.

---

**Q40. Correct: C**

Link-down with no detected light points to a complete physical-layer failure (break, unseated connector, or failed transceiver), whereas link-up with elevated BER points to a degraded but functioning signal path, typically caused by contamination or minor cable stress.

---

**Q41. Correct: D**

As-built photos and diagrams create a reliable reference of the actual physical installation, which is essential for future troubleshooting, compliance audits, and maintenance activities.

---

**Q42. Correct: A**

Standard electrical safety practice requires a formal lockout/tagout (LOTO) procedure: isolate the energy source, apply lock and tag, and confirm zero energy state with a rated tester before any hands-on work begins. This is mandatory in high-power (120 kW+) AI rack environments where residual energy or misidentified circuits pose lethal risk.

---

**Q43. Correct: D**

NEC Article 800/770 requires plenum-rated (CMP) cable for installation in air-handling spaces because it has the lowest flame spread and smoke production rating, preventing rapid fire propagation through HVAC return air paths.

---

**Q44. Correct: C**

Energized work on high-power distribution equipment requires arc-flash rated protective clothing, voltage-rated insulated gloves matched to the circuit class, and insulated/voltage-rated tools to protect against both shock and arc flash energy release.

---

**Q45. Correct: A**

NVIDIA's installation and compliance standard specifies that only NVIDIA-qualified optical transceivers and cable assemblies may be used in the InfiniBand fabric; using unqualified third-party optics can cause link instability, exceed vendor-tested BER thresholds, and voids warranty coverage.

---

**Q46. Correct: A**

Personnel must be bonded to the same ground reference as the equipment via a grounded ESD wrist strap connected at the designated EPA (ESD Protected Area) ground point, preventing static discharge into sensitive components like NVLink modules and compute trays during handling.

---

