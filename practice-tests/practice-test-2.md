# Practice Test 2: NCP-ARI: AI Rack & Interconnect Exam Prep

- **Questions:** 46
- **Time limit:** 90 minutes
- **Passing score:** 70%%

> Answers are in `answer-key-2.md`. Track results in `score-tracker.md`.

---

**Q1.** A data-center team is commissioning a GB200 NVL72 rack with a critical IT load of 132 kW. The facility power design calls for N+1 power-shelf redundancy. Which configuration correctly verifies power redundancy at the rack level?

A) Confirm each power shelf can supply its rated share of rack load and that at least one additional shelf beyond the calculated N is installed and load-tested to fail over without service interruption.
B) Confirm two separate PDUs are installed on the same electrical panel to protect against shelf failure.
C) Confirm total installed power shelf capacity equals exactly 132kW with no spare shelves, since redundancy is provided by the utility feed.
D) Confirm the busbar amperage rating exceeds the rack's nameplate power by 10%; redundancy is not required for DC racks.

---

**Q2.** Which statement accurately differentiates the AC and DC power architecture used in an NVIDIA GB200 NVL72 rack?

A) The rack is entirely DC end-to-end; facility 3-phase AC never enters the rack enclosure.
B) The rack uses 400V DC delivered directly from the facility, eliminating power shelves entirely.
C) AC and DC racks differ only in cooling method, not in power distribution.
D) The rack receives 3-phase AC at the rack's power shelves, which rectify it to 48V DC distributed to compute trays over a DC busbar.

---

**Q3.** In the GB200 NVL72 architecture, what is the primary distinction between the roles of NVLink and InfiniBand?

A) NVLink is used only for storage traffic, while InfiniBand handles GPU-to-GPU communication.
B) NVLink and InfiniBand are interchangeable within the rack and can be used for either scale-up or scale-out traffic.
C) NVLink connects all 72 GPUs into a single high-bandwidth memory-coherent domain within the rack, while InfiniBand provides scale-out fabric connecting multiple racks together.
D) InfiniBand connects GPUs within the NVLink Switch tray, while NVLink is used for rack-to-rack networking.

---

**Q4.** During rPDU installation for an AC-powered AI rack, a technician must balance a three-phase 415V feed across intelligent rPDUs feeding the rack's redundant power inputs. Which configuration correctly balances the load?

A) Connect only the A-side rPDU to all three phases and leave the B-side rPDU on a single phase for simplicity.
B) Connect all compute trays' redundant power inputs to the same phase to simplify monitoring.
C) Balance phases only at the panel level; rPDU-level phase balance is not measurable or necessary.
D) Distribute the rack's total load as evenly as possible across L1, L2, and L3, alternating phase rotation between the A-side and B-side rPDUs so that a single-phase loss doesn't fully de-power any device.

---

**Q5.** A liquid-cooled GB200 NVL72 deployment uses a rack-level CDU that isolates the facility water loop from the technology cooling system (TCS) loop. During commissioning, the technician measures a facility loop supply temperature of 32°C and a TCS loop supply temperature of 40°C at the manifold. What does this indicate?

A) This is normal because the TCS loop must always run warmer than the facility loop to protect GPU dies from thermal shock.
B) The 8°C difference is larger than the typical 2–3°C approach temperature for a properly functioning CDU heat exchanger, and should be investigated for reduced facility flow rate or a fouled heat exchanger.
C) The measurement indicates the facility loop and TCS loop are cross-connected and must be swapped immediately.
D) This confirms the rack is undersized for the IT load and additional CDUs must be added.

---

**Q6.** A GB200 NVL72 rack uses liquid cooling manifolds where stainless steel fittings mate to copper cold plates. During installation, what is the PRIMARY grounding/bonding concern the technician must verify to prevent long-term system failure?

A) That the rack frame is grounded, but manifold bonding is not necessary because liquid cooling loops are electrically isolated by design.
B) That only the CDU chassis requires grounding since it is the only component that draws AC power.
C) That dielectric isolation fittings or proper bonding straps are installed at dissimilar-metal joints to prevent galvanic corrosion, in addition to verifying overall rack ground continuity to the facility ground bus.
D) That the manifold is left ungrounded to avoid stray current buildup from the rack's DC busbar.

---

**Q7.** A GB200 NVL72 rack is fed by dual three-phase AC rPDUs configured as redundant A/B feeds. Power monitoring shows L1 is drawing 38A while L2 and L3 are drawing 24A and 22A respectively, all within the rPDU's per-phase rating but creating a significant imbalance. What should the technician do to correct this?

A) Increase the breaker rating on the L1 phase circuit to accommodate the higher measured current draw
B) Disable the outlets on L2 and L3 to force the load distribution to match L1
C) Replace the AC rPDU with a DC busbar power shelf to eliminate phase imbalance
D) Redistribute IT equipment power connections across the L1, L2, and L3 outlets on the rPDU to balance phase loading

---

**Q8.** In a direct-to-chip liquid-cooled GB200 NVL72 deployment, which component isolates the facility (building) chilled water loop from the closed technology cooling system (TCS) loop that circulates coolant directly to the GPU/CPU cold plates?

A) Rear Door Heat Exchanger (RDHx)
B) Intelligent rack PDU (rPDU)
C) Coolant Distribution Unit (CDU)
D) In-row Computer Room Air Handler (CRAH)

---

**Q9.** Within a single GB200 NVL72 rack, which interconnect layer provides the 72-GPU NVLink domain that enables full all-to-all GPU-to-GPU communication inside the rack, as distinct from the fabric used to scale out compute between racks?

A) 800G InfiniBand NDR fabric connecting each GPU tray to the spine switches
B) NVLink Switch trays providing a single 72-GPU NVLink domain for all-to-all GPU communication within the rack
C) 100GbE RoCE v2 Ethernet fabric distributed via the rack's leaf switches
D) PCIe Gen5 switch fabric routed through the compute tray backplane

---

**Q10.** A site survey reports that the data center's raised-floor system is rated for a static load of 1,200 kg/m² (245 lb/ft²). The planned GB200 NVL72 rack has a footprint of 600 mm x 1200 mm (0.72 m²) and a fully configured weight of 1,800 kg. What is the correct pre-deployment action?

A) Proceed with installation since the rated floor capacity comfortably exceeds typical rack loads in most data centers
B) Calculate the point/static load (1,800 kg ÷ 0.72 m² ≈ 2,500 kg/m²), determine it exceeds the 1,200 kg/m² floor rating, and engage a structural engineer to verify slab-mounting or floor reinforcement before installation
C) Distribute the rack's weight across two adjacent floor tiles to stay under the per-tile limit
D) Reduce the rack to a partial GPU configuration to lower the total weight below the floor rating

---

**Q11.** During a site survey for InfiniBand cable installation, the technician finds that the underfloor pathway intended for NVLink and InfiniBand trunk cables crosses over three CRAC unit chilled-water supply lines with only 5 cm of vertical separation. What is the correct next step per pre-deployment site assessment procedure?

A) Proceed with cable installation since fiber and copper cables are unaffected by nearby water leaks
B) Install the cables directly above the CRAC lines using a temporary cable tray with no additional separation
C) Document the clearance violation, reroute the pathway or add physical separation/protection meeting minimum separation standards, and revise the site readiness report before proceeding
D) Skip the InfiniBand run in that pathway and route only copper DAC cables instead

---

**Q12.** Which pre-deployment activity specifically validates that a data hall's CRAC/CDU cooling capacity and hot-aisle containment are correctly sized for the planned rack's thermal design power (TDP) before any hardware arrives?

A) Environmental readiness verification (cooling and thermal load assessment)
B) Physical network design documentation review
C) Inventory-check procedure
D) Cable pathway floor-load survey

---

**Q13.** A GB200 NVL72 rack has a maximum rated power draw of 120 kW. The facility's power design provides two independent 415V three-phase feeds per rack in an A/B redundant configuration. During pre-deployment power readiness verification, what should the technician confirm?

A) That EACH feed independently is rated to carry the full 120 kW load in an N+N configuration, so either feed alone can support the rack during a single feed failure without derating
B) That only one feed needs to support the full 120 kW load, since the second is a cold spare rated for less power
C) That the combined capacity of both feeds together must equal at least 120 kW, regardless of redundancy configuration
D) That the feeds only need to support the rack's idle power draw, since full load rarely occurs in production

---

**Q14.** During the pre-deployment inventory-check procedure for an NVLink Switch tray and InfiniBand cable shipment, which discrepancy would MOST likely require escalation before installation begins?

A) The shipment includes OSFP active optical cables rated for a shorter reach than required by the site's measured rack-to-rack fiber run distances documented in the site survey
B) Packaging labels showing a different revision date than the packing slip
C) Cable ties included in the box being a different color than expected
D) The rack unit numbering on the shipping manifest differing from the internal NVIDIA tracking number

---

**Q15.** A data-center technician is site-prepping a row of NVIDIA GB200 NVL72 extra-wide racks. The rack's rear compartment houses the CDU manifold, hoses, and busbar risers that require periodic hands-on service. Per standard high-density AI rack site-prep guidance, what is the MINIMUM clear service depth that must be maintained behind the rack for safe manifold and busbar servicing?

A) 300 mm (12 in), matching a standard networking cabinet
B) No rear clearance is required since GB200 NVL72 is front-serviceable only
C) 600 mm (23.6 in), matching the rack's own width
D) 1200 mm (47.2 in) clear rear service zone

---

**Q16.** During cable-pathway planning for an InfiniBand NDR fabric feeding a GB200 NVL72 pod, the design routes 54V DC busbar power risers and active optical/copper NDR cable bundles through the same vertical channel on one side of the rack. What is the BEST corrective action to mitigate EMI coupling before cabling installation proceeds?

A) Separate power and data into independent vertical channels (or use a grounded metal divider) with recommended physical spacing between them
B) Wrap the fiber bundles in aluminum foil tape and leave the routing as-is
C) Twist the optical cables around the busbar risers to cancel induced fields
D) Increase the fiber transceiver launch power to overcome any induced noise

---

**Q17.** A vertical fiber duct is being installed to carry OSFP-based 400G/800G InfiniBand cable bundles up the side of a GB200 NVL72 rack. The duct's built-in bend-radius manager guides cables around a corner. Which spacing rule should the manager enforce to protect the fiber under normal installed (unloaded/static) conditions?

A) A bend radius of roughly 20x the cable's outer diameter
B) No minimum bend radius applies once the cable is seated in a duct
C) A bend radius equal to the cable's own outer diameter
D) A bend radius of roughly 4x the cable's outer diameter

---

**Q18.** A site-readiness inspector reviews a newly delivered row of extra-wide GB200 NVL72 racks and finds that adjacent racks in the row are spaced with only the standard 600 mm (19-in EIA) rack-to-rack gap used on the previous-generation air-cooled deployment. What is the MOST likely site-prep deficiency this creates?

A) None — GB200 NVL72 racks use the same footprint as standard 19-in racks, so no change is needed
B) Excess spacing that wastes floor space but causes no functional issue
C) Insufficient front-post-to-front-post and rear-post-to-rear-post clearance to accommodate the rack's wider footprint, cable channels, and CDU service access
D) A cooling airflow issue only, unrelated to physical clearance

---

**Q19.** A facility is retrofitting an existing white space to host GB200 NVL72 pods behind a perforated hot-aisle containment door. Site survey shows the front rack posts will sit 900 mm from the containment door once installed. The AI rack platform's front-post-to-front-door clearance requirement calls for 1200 mm minimum to allow full extension of front-loaded compute/switch trays during service. What should the technician do BEFORE proceeding with rack installation?

A) Install the racks as planned and service trays through the rear compartment instead
B) Proceed with installation; 900 mm is close enough and trays can be angled out partially
C) Reduce the tray depth setting in NVIDIA firmware to compensate for the shorter clearance
D) Halt installation and re-plan the row layout or containment door position to meet the required front clearance before racks are set

---

**Q20.** A technician must connect two NVLink Switch trays located 150 meters apart in a large-scale GB200 NVL72 SuperPOD deployment, spanning across two rows of the data center. Which cabling solution BEST meets this requirement?

A) OM4 multimode DAC copper cable rated to 3m
B) Single-mode fiber cable with LR/FR-rated OSFP transceivers
C) OM4 multimode fiber patch cable with SR4 transceivers
D) Active Copper Cable (ACC) rated to 7m

---

**Q21.** A rack pair sits directly adjacent within the same NVL72 pod, requiring a 2-meter NDR (400Gb/s) InfiniBand link between leaf switches. To minimize power draw and cost while following NVIDIA's supported cabling guidance, which cable type should be selected?

A) Active Optical Cable (AOC)
B) Passive Copper DAC
C) Active Copper Cable (ACC)
D) Single-mode fiber with LR transceivers

---

**Q22.** During cable dressing in a high-density GB200 NVL72 rack, what is the minimum bend radius that must be maintained for InfiniBand copper and fiber cabling to avoid signal degradation or physical damage, per NVIDIA cabling guidance?

A) 30 mm
B) 15 mm
C) 50 mm
D) 10 mm

---

**Q23.** While installing 72 NDR cables into a GB200 NVL72 rack, a technician routes all cables down the left side of the rack to save time, resulting in a cable bundle that partially blocks front-door airflow and exceeds the tray's rated fill capacity on that side. What should the technician do to correct this installation per NVIDIA best practice?

A) Add additional hook-and-loop ties to compress the bundle further
B) Redistribute cables using the 50/50 left-right routing strategy across both cable trays
C) Reroute all cables to the right side instead
D) Leave the routing as-is since airflow impact is negligible at this density

---

**Q24.** Which statement correctly differentiates APC and UPC fiber-optic connector polish types as used in high-density MPO cabling deployments?

A) UPC connectors are angled at 8 degrees and colored green, while APC connectors are flat-polished and colored blue
B) APC and UPC connectors are interchangeable and mate correctly regardless of type
C) APC connectors are angled at 8 degrees and colored green, reducing back reflection, while UPC connectors are flat-polished and colored blue
D) APC connectors are used only for multimode fiber, while UPC connectors are used only for single-mode fiber

---

**Q25.** Before mating an MPO/APC fiber connector during a GB200 NVL72 InfiniBand cabling installation, a technician wipes the ferrule end-face with an isopropyl-alcohol-soaked cloth and immediately connects it. Link testing later shows elevated BER on that link. What was most likely done incorrectly?

A) The technician should have used a dry lint-free wipe instead of isopropyl alcohol
B) The technician should have cleaned the connector after mating rather than before
C) The technician used the wrong alcohol concentration, which should always be 70% rather than 99%
D) The technician failed to inspect the ferrule end-face with a fiber-optic microscope after cleaning and before mating

---

**Q26.** A GB200 NVL72 rack-to-rack InfiniBand NDR (400Gb/s) interconnect requires a 5-meter run between two leaf switches in adjacent racks. The site standard mandates copper-only cabling for this run (no optics), and passive DAC cables are only rated to 2m at this speed. Which cable type should be selected?

A) Re-terminate a passive DAC assembly in the field to extend it to 5m
B) Active Optical Cable (AOC)
C) Active Copper Cable (ACC)
D) Standard passive DAC cable rated for 2m, run anyway since it is close enough

---

**Q27.** Which transceiver form factor is the NVIDIA standard for Quantum-2 InfiniBand switch ports operating at NDR (400Gb/s per port)?

A) QSFP-DD
B) SFP+
C) QSFP56
D) OSFP

---

**Q28.** During installation of high-density InfiniBand fiber trunks inside a GB200 NVL72 rack, what is the minimum bend radius that must be maintained to prevent attenuation and physical fiber damage?

A) 100 mm
B) 10 mm
C) 30 mm
D) 60 mm

---

**Q29.** A data hall design requires a 500-meter InfiniBand NDR (400Gb/s) link between two switches in separate rows. Which cabling and transceiver combination correctly meets this reach requirement?

A) Active Copper Cable (ACC) assembly rated for extended reach
B) Single-mode fiber (SMF) with LR transceivers
C) Multimode fiber (OM4) with SR8 transceivers
D) Passive DAC copper cable with signal boosters

---

**Q30.** For a GB200 NVL72 switch tray with 72 InfiniBand ports, which implementation correctly follows the 50/50 left-right cable-routing strategy?

A) Route all copper DAC cables to the left channel and all fiber cables to the right channel regardless of port location
B) Route ports 1-36 to the left vertical cable channel and ports 37-72 to the right channel, matching physical port position
C) Alternate ports left-right by odd/even numbering (port 1 left, port 2 right, port 3 left, etc.) to evenly distribute bend stress
D) Route cables based solely on destination switch tier, ignoring physical port position on the panel

---

**Q31.** Why must APC (Angled Physical Contact) MPO fiber connectors never be mated with UPC (Ultra Physical Contact) connectors in a high-density NVIDIA fiber installation?

A) Mixing connector polish types trips the NVIDIA DU-10438 safety interlock and automatically disables the port
B) Color coding (green vs. blue) is purely cosmetic; the end faces are mechanically identical and can be freely mixed
C) APC and UPC connectors are built for different core fiber types (multimode vs. single-mode), making them optically incompatible
D) The 8-degree angled polish on APC versus the flat polish on UPC creates a physical air gap, causing severe back reflection and high insertion loss

---

**Q32.** A technician is planning an InfiniBand NDR (400Gb/s) interconnect between two GB200 NVL72 racks located in different rows of the same data hall, 80 meters apart. Which cabling solution BEST meets this requirement?

A) NDR passive copper DAC cable rated for links up to 2 meters
B) NDR active copper cable (ACC) rated for links up to 5 meters
C) OSFP transceivers with duplex single-mode fiber (SMF) using DR4/FR4 optics rated for distances up to 2 km
D) OSFP transceivers with duplex OM4 multi-mode fiber (MMF) using SR8 optics rated for up to 50 meters at NDR speeds

---

**Q33.** During installation, a technician needs to terminate an MPO trunk cable with APC (angled physical contact) connectors into a switch line card port designed for UPC (ultra physical contact) connectors. What is the correct action?

A) Mate the connectors as-is, since polish type does not affect optical performance in MPO trunk cables
B) Never mate APC to UPC connectors; source an MPO cable whose polish type matches the port (APC-to-APC or UPC-to-UPC), verifying by connector color (APC = green, UPC = blue) before installation
C) Clean both connector end faces with an isopropyl wipe and mate them together to reduce return loss
D) Insert an 8-degree angled adapter between the two connectors to compensate for the polish mismatch

---

**Q34.** A row of eight GB200 NVL72 racks requires overhead cable support for roughly 1,200 individual 400G DAC and AOC runs exiting the top of each rack toward the spine layer. Engineering calculations show the resulting bundle weight will exceed 900 lbs across a 10-foot span. Which support approach is correct?

A) Route the bundle through wire basket tray sections rated for standard IT cabling loads
B) Use J-hooks spaced every 4 feet along the row to distribute the load evenly
C) Use a single continuous cable tray run with no intermediate bracing, relying on the tray's overall length rating
D) Install engineered trapeze-style ladder rack rated for the calculated load, with support spacing reduced below the manufacturer's standard interval

---

**Q35.** A ladder rack section is rated for 50 lbs per linear foot when installed with supports every 5 feet, per the manufacturer's engineering data. To reduce material cost, the installation plan specifies supports every 10 feet instead, and the calculated cable load is 45 lbs per linear foot. What is the correct action?

A) Restore supports to the tested 5-foot interval, since the published load rating is only valid at the support spacing it was tested against
B) Proceed with 10-foot spacing since 45 lbs/ft is under the 50 lbs/ft rating
C) Increase spacing further to 15 feet since the load is comfortably under the rated capacity
D) Switch to J-hooks at 10-foot intervals to lower material cost while keeping the same load

---

**Q36.** During InfiniBand cable installation for a GB200 NVL72 pod, technicians leave a properly sized service loop at the transition point where cables exit the overhead tray and drop into the rack. What is the primary engineering purpose of this service loop, as distinct from simply reserving extra length for future re-terminations?

A) It provides strain relief so the weight and movement of the cable run are not transferred onto the connector and transceiver housing at the transition point
B) It gives installers spare cable length so runs can be re-terminated multiple times without pulling new cable
C) It reduces the total number of cable reels required for the bulk material order
D) It makes cable labels easier to read during and after installation

---

**Q37.** A field technician is verifying continuity and insertion loss on a newly installed 400G fiber trunk between two NVIDIA Quantum-2 switches using an optical power meter, prior to connecting any live transceivers. The measured insertion loss is 1.8 dB higher than the reference loss recorded during the cable's factory acceptance test. What does this most likely indicate, and what is the correct next action?

A) The trunk cable degraded due to normal aging; replace the entire trunk
B) This is within acceptable tolerance; proceed to connect transceivers and monitor
C) An additional splice, dirty connector, or micro-bend was likely introduced during installation; clean and inspect the connectors with a fiber-inspection scope before re-measuring
D) The optical power meter itself is miscalibrated; ignore the reading and rely on link status alone

---

**Q38.** During post-install validation of a newly cabled 400G copper DAC link on an NVIDIA Quantum-2 switch, `mlxlink` reports Physical state: LinkUp, but Effective BER is 4.2E-09 with a high raw symbol-error count — well outside the expected effective BER spec. What is the most likely root cause and correct remediation?

A) Excessive attenuation is likely caused by using a non-NVIDIA-validated cable that does not meet the signal-integrity spec for that reach/speed combination; replace it with a certified NVIDIA LinkX DAC of the correct reach
B) The switch port is misconfigured for the wrong speed; manually change the port speed
C) This reading is normal and expected for a LinkUp state; no action is required
D) The switch ASIC has failed; replace the entire Quantum-2 switch chassis

---

**Q39.** Which piece of information MUST be captured in the as-built cabling documentation for a GB200 NVL72-class deployment to properly support future signal-integrity troubleshooting, beyond a basic port-to-port connectivity map?

A) The MAC address of every NIC installed in the rack
B) The ambient temperature recorded at the moment of cable installation
C) The names of the technicians who terminated each fiber connector
D) The cable serial number and NVIDIA LinkX part number for each optical/DAC link, cross-referenced to its exact port location

---

**Q40.** During final quality inspection of a fiber trunk cable that is currently under tension while being pulled through a cable tray, which minimum bend-radius rule applies to avoid introducing latent signal-integrity degradation?

A) 20x the cable's outer diameter, since the cable is currently under tension/pulling load
B) 10x the cable's outer diameter, regardless of tension
C) 4x the cable's outer diameter, matching the minimum rack-unit bend clearance
D) There is no bend-radius requirement once the cable is secured in a cable tray

---

**Q41.** A newly cabled 800G OSFP port cycles repeatedly between Polling and Training states and never reaches LinkUp — a clearly different symptom from a link that reaches LinkUp with elevated BER. What is the single best first diagnostic step to isolate whether the fault is the transceiver/cable or the switch-side port ASIC?

A) Immediately change the port's FEC mode from RS-FEC to a different FEC scheme and retest
B) Restart the entire switch chassis and wait for all ports to re-train
C) Swap the suspect OSFP transceiver/cable into a known-good port, and/or insert a known-good cable into the suspect port, to isolate the cable/optic from a switch-side fault
D) File an RMA for the entire rack without further diagnosis

---

**Q42.** A technician is about to service a 415V three-phase busway feeding two GB200 NVL72 racks (120 kW+ each). The technician has already opened the disconnect, applied a personal lock and tag, and put on arc-rated PPE per the equipment's arc-flash label. What is the required NEXT step before physical contact with any conductor?

A) Notify the data center facilities team that the lock is applied and proceed with the work order
B) Ask a second technician to co-sign the tag, then begin work immediately since the disconnect is open
C) Remove PPE once the lock is applied, since an open disconnect with a lock guarantees a de-energized circuit
D) Use a rated voltage tester to verify zero energy state, testing the tester on a known live source before and after the check

---

**Q43.** An installer is routing out-of-band management copper cabling through the space above suspended ceiling tiles in the hot aisle, which is also used as the return-air plenum for the CRAH units. Per NEC Article 800, which cable rating is required for this pathway?

A) CMR (riser-rated)
B) CMP (plenum-rated)
C) CM (general-purpose)
D) CMX (limited-use, residential-grade)

---

**Q44.** A technician needs to perform a voltage-verification check on an energized 415V busway supplying multiple NVL72 racks in a 120 kW+ pod. Per NFPA 70E, what determines the specific PPE arc-flash category required for this task?

A) The technician's years of experience with similar busway systems
B) The arc-flash risk assessment and incident-energy label affixed to the equipment
C) A fixed table based solely on the nominal system voltage (415V)
D) The rack vendor's quick-start installation guide

---

**Q45.** During installation of 800G OSFP interconnect cables per NVIDIA DU-10438 rack cabling guidelines, what is the minimum bend radius requirement to remain within signal-integrity spec and warranty compliance?

A) Not less than 10 times the cable's outer diameter
B) No bend radius restriction applies as long as the connector housing is undamaged
C) A fixed 1-inch (2.5 cm) radius regardless of cable diameter
D) Not less than 2 times the cable's outer diameter

---

**Q46.** A technician is about to remove a GPU tray from a GB200 NVL72 compute chassis for replacement. Which grounding configuration correctly protects the technician while also protecting the ESD-sensitive tray from a hazardous discharge path?

A) Rubber-soled shoes on an insulated floor mat, with no wrist strap required
B) An ESD wrist strap connected to a common-point ground through an integrated 1 MΩ current-limiting resistor, combined with an ESD mat at the work surface
C) Touching the bare metal rack frame once before handling the tray, then working without further grounding
D) A wrist strap connected directly to chassis ground with no resistor, for the lowest possible resistance path

---

