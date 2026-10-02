# Practice Test 1: NCP-ARI: AI Rack & Interconnect Exam Prep

- **Questions:** 46
- **Time limit:** 90 minutes
- **Passing score:** 70%%

> Answers are in `answer-key-1.md`. Track results in `score-tracker.md`.

---

**Q1.** A technician is preparing a new GB200 NVL72 rack for installation. The rack's compute trays connect to a busbar that distributes 48V to each tray, and this busbar is fed by rectifier/power shelves that convert incoming facility power. How should this rack be classified for power planning purposes?

A) A traditional AC rack, because facility power always arrives as AC regardless of in-rack distribution
B) A hybrid rack that requires no power shelves since GPUs consume AC directly
C) A DC rack, because power is converted to DC and distributed to compute trays via a busbar rather than individual AC PDU outlets
D) An AC rack, because rPDUs are still required for every server in the rack

---

**Q2.** An AC-powered AI rack uses three-phase intelligent rPDUs. Monitoring shows Phase L1 is drawing significantly more current than L2 and L3, though total rack power is within capacity. What is the correct corrective action?

A) Increase the breaker rating on Phase L1 to accommodate the higher draw
B) Redistribute power cord connections across the three phases on the rPDUs to balance current draw
C) Remove servers from the rack until total power drops below the rated capacity
D) Replace the three-phase rPDU with a single-phase PDU to simplify monitoring

---

**Q3.** A mission-critical GB200 NVL72 rack must remain operational if an entire power distribution path — including its upstream UPS and PDU — fails completely. Which power redundancy configuration meets this requirement?

A) N+1 redundancy using a single shared PDU with a backup power module
B) 2N redundancy, with two independent PDU paths each fed by separate UPS sources and each sized for the full rack load
C) 1N configuration with one PDU sized for full load and no backup path
D) N+1 redundancy where a shared neutral connects both PDU paths for load balancing

---

**Q4.** In a liquid-cooled AI rack, which component isolates the facility water loop from the rack's technology cooling loop while monitoring coolant flow rate, pressure, and temperature?

A) The intelligent rack PDU (rPDU)
B) The NVLink switch tray
C) The coolant distribution unit (CDU)
D) The blind panel airflow baffle

---

**Q5.** Before energizing a newly installed AI rack, a technician must verify the rack is properly grounded per site electrical standards. Which method correctly verifies this?

A) Measuring the resistance between the rack chassis and the building's grounding electrode system with a ground resistance meter, confirming it meets facility specification
B) Confirming the ESD wrist strap mat is clipped to the rack frame
C) Visually confirming the green/yellow ground wire is present in the power cable
D) Confirming the rack's power cord is plugged into a labeled 'grounded' wall outlet

---

**Q6.** Within a GB200 NVL72 rack and its scale-out fabric, which statement correctly matches the interconnect layer to its primary role?

A) Ethernet connects all 72 GPUs within the rack for GPU-to-GPU communication; NVLink handles scale-out between racks
B) NVLink connects all 72 GPUs within the rack for GPU-to-GPU communication; InfiniBand handles scale-out between racks; Ethernet handles management/storage traffic
C) InfiniBand connects all 72 GPUs within the rack for GPU-to-GPU communication; NVLink handles scale-out between racks
D) NVLink, InfiniBand, and Ethernet are interchangeable and any one of them can be used for any of the three roles

---

**Q7.** A data-center technician is installing two intelligent rack PDUs (rPDUs) in an AC-powered AI rack fed by three-phase power (L1, L2, L3). Ten servers each draw roughly equal current and must be distributed across the phases. Which action BEST ensures safe, balanced operation of the rack?

A) Connect all ten servers to L1 on both rPDUs for simplicity and monitor total amps at the panel
B) Distribute the server power connections evenly across L1, L2, and L3 on each rPDU and verify per-phase current draw with the rPDU's built-in metering
C) Connect one rPDU entirely to L1-L2 and the other entirely to L2-L3 so each PDU has a dedicated pair of phases
D) Disable phase monitoring on the rPDU since GB-class AI servers regulate their own current draw internally

---

**Q8.** A rack is being provisioned for direct-to-chip liquid cooling in an NVIDIA GB200 NVL72 deployment. Which component is responsible for isolating the facility water loop from the rack's internal coolant loop while regulating coolant flow, pressure, and temperature to the cold plates?

A) The rack-mounted rPDU
B) The NVLink Switch tray
C) The hot-aisle containment door
D) The Coolant Distribution Unit (CDU)

---

**Q9.** An architect needs the 72 GPUs within a single GB200 NVL72 rack to communicate as one unified, all-to-all memory domain with the lowest possible latency and highest bandwidth, while a separate fabric will handle scale-out communication between multiple NVL72 racks in the cluster. Which interconnect should be used for the intra-rack, all-to-all GPU domain?

A) NVLink (via NVSwitch), because it provides the highest bandwidth, lowest-latency GPU-to-GPU fabric within the rack's unified memory domain
B) Ethernet, because it is the most widely supported fabric across all rack vendors
C) InfiniBand, because it is NVIDIA's exclusive standard for all GPU-to-GPU traffic at any scale
D) A standard PCIe switch, because it offers greater bandwidth than any NVIDIA proprietary interconnect

---

**Q10.** A data center is preparing to receive a GB200 NVL72 rack, which weighs approximately 1,360 kg (3,000 lbs) fully populated. The facilities team confirms the raised floor tiles are rated for 600 kg/m² static load. Before scheduling delivery, what is the FIRST site-readiness step the deployment team should perform?

A) Verify the structural floor load capacity and reinforcement requirements against the rack's certified weight specification
B) Order additional InfiniBand cables to have spares on-site before the rack arrives
C) Pre-configure the management switch VLANs so the rack is network-ready on arrival
D) Schedule the ESD training session for the installation crew

---

**Q11.** During a pre-deployment site survey for a row of liquid-cooled AI racks, the assessment team measures 900mm of clearance in the cold aisle and 1200mm in the hot aisle. Per standard high-density rack deployment practices for service access and airflow/CDU maintenance, what should the survey document as a finding?

A) The clearances are acceptable as-is since hot aisle spacing exceeds cold aisle spacing
B) The cold aisle clearance is insufficient and should be flagged for correction to meet the minimum service-access requirement
C) Only power cabling clearance matters; airflow clearance is irrelevant for liquid-cooled racks
D) The measurements are irrelevant until after the racks are physically installed

---

**Q12.** An installation technician arrives on-site to begin high-density InfiniBand cabling for a new AI rack row. Which document should be consulted FIRST to determine correct port-to-port connectivity between leaf and spine switches?

A) The facility's fire suppression system diagram
B) The physical network design/cabling schematic prepared during pre-deployment planning
C) The rack manufacturer's shipping manifest
D) The general safety data sheet (SDS) for the cabling materials

---

**Q13.** As part of environmental readiness verification before rack delivery, the site assessment identifies that the facility's rPDU circuits are rated for 3-phase 415V/60A, while the incoming GB200 NVL72 rack's power specification requires 415V/63A per feed with N+N redundancy. What should the assessment report conclude?

A) The circuits pass verification since the voltage rating matches, regardless of amperage
B) The mismatch is acceptable because InfiniBand switches will draw less current than compute nodes
C) Power specifications only need to be verified after the rack is physically installed and powered on
D) The environmental readiness check fails on power capacity, and the electrical infrastructure must be upgraded before delivery

---

**Q14.** What is the primary purpose of the inventory-check procedure performed during pre-deployment site assessment for an AI rack deployment?

A) To confirm that all received components, cables, and accessories match the bill of materials before installation begins
B) To calculate the total power draw of the rack under full GPU load
C) To validate InfiniBand link bit-error-rate performance after cabling is complete
D) To generate the final compliance certificate required for facility handover

---

**Q15.** A technician is preparing an extra-wide GB200 NVL72 rack for installation and needs to confirm the front-post-to-front-door clearance before mounting compute trays. Which clearance value should the technician verify meets NVIDIA's rack preparation requirement for full door swing and hot-swap tray access?

A) Minimum 300 mm (12 in)
B) No clearance is required if the front door is removed permanently
C) Minimum 600 mm (24 in)
D) Minimum 1200 mm (47 in)

---

**Q16.** A site team is routing AC power whips and InfiniBand fiber trunks into a GB200 NVL72 rack row. To mitigate EMI-induced signal degradation on the high-speed fiber links, what cable routing practice should be followed during rack preparation?

A) Twist the power and fiber cables together in a single bundle for compactness
B) Maintain separate, dedicated pathways for power and data cabling with a minimum lateral separation distance between them
C) Route power cables directly over the fiber trunks using the same overhead tray without separation
D) Route power and fiber cables together but only in the rear of the rack, since front routing requires separation

---

**Q17.** During cable management installation in a high-density rack, fiber trunk cables must transition from a vertical duct to a horizontal duct at a 90-degree turn. Which accessory should be installed at this transition point to prevent the cables from being bent tighter than their minimum specified radius?

A) A horizontal cable manager
B) Additional zip ties spaced every 50 mm
C) A bend-radius manager (waterfall guide)
D) A vertical cable manager

---

**Q18.** Per standard fiber-optic cabling practice applied during GB200 NVL72 rack cable installation, what is the correct minimum bend radius requirement for a fiber trunk cable in the unloaded (no tension) versus loaded (under tension) condition?

A) 1x the cable's outer diameter in both conditions
B) 10x the cable's outer diameter unloaded, 15x the outer diameter loaded
C) No bend radius limit applies to OM4 multimode fiber
D) 5x the cable's outer diameter unloaded only; loaded condition has no additional requirement

---

**Q19.** What is the primary purpose of the front-post-to-rear-post clearance specification measured inside a GB200 NVL72 rack cabinet during rack preparation?

A) It defines the cold-aisle containment distance between adjacent rack rows
B) It sets the raised-floor tile cutout dimensions for the entire data hall
C) It determines how far the front cabinet door can swing open
D) It ensures sufficient internal depth to route power whips, CDU coolant manifolds, and InfiniBand cabling behind the compute trays without interference

---

**Q20.** A high-density AI cluster requires NVIDIA NDR InfiniBand connectivity between two rows of racks located 1.5 km apart on the same data-center campus. Which transceiver and fiber combination BEST meets this requirement?

A) 400G-SR4 transceivers with OM4 multimode fiber
B) 400G-DR4 transceivers with single-mode fiber
C) 400G-FR4 transceivers with single-mode fiber
D) Passive DAC copper cable

---

**Q21.** Which transceiver form factor is used on NVIDIA Quantum-2 NDR InfiniBand switch ports to support the higher thermal and power requirements of 400/800Gb optical modules?

A) SFP+
B) OSFP
C) QSFP28
D) QSFP-DD

---

**Q22.** Per NVIDIA cable installation guidance (DU-10438), what is the approximate minimum bend radius that must be maintained when routing InfiniBand fiber-optic cables through a rack?

A) 30 mm
B) 10 mm
C) 100 mm
D) 60 mm

---

**Q23.** A technician must connect two GB200 NVL72 racks with NDR InfiniBand at a 6-meter distance. Passive DAC copper cables are only rated to about 3 meters at NDR signaling rates. Which cable type should be used to complete this connection while still using copper?

A) A longer passive DAC cable run
B) A standard Ethernet patch cable
C) An MMF SR4 optical transceiver
D) An Active Copper Cable (ACC)

---

**Q24.** What is the primary purpose of implementing the 50/50 left-right cable-routing strategy in a high-density AI rack?

A) It ensures fiber and copper cables are never combined in the same bundle
B) It reduces the total number of cables required for the deployment
C) It balances cable bundle weight and volume on both sides of the rack to improve airflow, cable management, and serviceability
D) It is mandatory only for redundant power distribution wiring

---

**Q25.** During installation of MPO fiber trunks, a technician has both APC (green, angled-contact) and UPC (blue, flat-contact) terminated patch cables available. Which practice is correct?

A) APC and UPC connectors are interchangeable since both use the same MPO housing
B) UPC connectors should be reserved for external plant cabling only and never used indoors
C) Never mate an APC connector to a UPC connector, since the angled and flat contact geometries cause excessive insertion loss and can damage the ferrule
D) APC connectors do not require cleaning before mating because the angled face prevents contamination

---

**Q26.** A technician must connect two InfiniBand NDR switches located 70 meters apart across multiple rows in a data hall. Which cable and transceiver combination should be deployed?

A) Passive DAC copper cable
B) MMF fiber cable with QSFP transceivers (850nm)
C) Active copper cable (ACC)
D) SMF fiber cable with OSFP transceivers (1310nm)

---

**Q27.** Which transceiver form factor is used for InfiniBand NDR (400Gb/s) and XDR (800Gb/s) links in the NVIDIA GB200 NVL72 rack?

A) OSFP
B) SFP+
C) CFP2
D) QSFP56

---

**Q28.** What is the minimum bend radius NVIDIA specifies for InfiniBand fiber-optic and copper cabling in high-density rack installations to prevent signal degradation and physical damage?

A) 30 mm
B) 10 mm
C) 100 mm
D) 50 mm

---

**Q29.** A technician is about to mate an APC (angled physical contact) fiber connector to a patch panel port during a GB200 NVL72 installation. What is the correct procedure before mating?

A) Skip cleaning since APC connectors are self-cleaning
B) Clean the ferrule with an APC-compatible one-click cleaner, then inspect with a fiber-optic microscope before mating
C) Clean the ferrule using a UPC-rated cleaning cartridge, then mate immediately
D) Apply isopropyl alcohol directly onto the ferrule and mate immediately without inspection

---

**Q30.** Which characteristic reliably differentiates a single-mode fiber (SMF) cable from a multi-mode fiber (MMF) cable in an NVIDIA high-density cabling deployment?

A) SMF cables use a yellow jacket with APC (green) connectors, while MMF cables use aqua/OM4 jackets with UPC/PC (blue) connectors
B) SMF cables cannot use MPO connectors, only LC connectors
C) MMF cables support longer transmission distances than SMF cables
D) SMF cables are always physically thicker in diameter than MMF cables

---

**Q31.** During cabling of a GB200 NVL72 rack, the installation team must route dozens of high-speed copper and fiber cables from the compute trays to the switch trays. Which practice aligns with NVIDIA's recommended 50/50 cable-routing strategy?

A) Route all cables down a single vertical channel to minimize total path length
B) Bundle all cables to the rear-right corner of the rack for easier future access
C) Route cables in whichever direction yields the shortest possible cable length regardless of side
D) Split cable bundles evenly between the left and right sides of the rack to balance weight and preserve airflow clearance

---

**Q32.** A data center technician must connect two GB200 NVL72 racks located 300 meters apart using InfiniBand NDR (400Gb/s) links. Which cabling and transceiver combination BEST meets this distance requirement?

A) Multi-mode fiber (MMF) with SR4 OSFP transceivers
B) Passive Direct Attach Copper (DAC) cables
C) Single-mode fiber (SMF) with DR4/FR4-rated OSFP transceivers
D) Active Copper Cable (ACC) assemblies

---

**Q33.** During cable dressing in a GB200 NVL72 rack, an installer routes a bundle of InfiniBand fiber-optic cables around a vertical support post using hook-and-loop ties. What is the minimum bend radius the installer must maintain to prevent signal degradation and physical cable damage per NVIDIA cabling guidance?

A) 10 mm
B) 75 mm
C) 150 mm
D) 30 mm

---

**Q34.** A technician is planning the overhead cable path for a new row of GB200 NVL72 racks, each requiring hundreds of copper InfiniBand DAC cables plus power whips running horizontally above the row. The bundled weight per linear foot is significantly higher than a typical data hall row. Which approach BEST addresses this load before installation begins?

A) Route all cables through the raised floor plenum to keep weight off the overhead structure
B) Install a continuous run of adhesive-backed wire hooks spaced every 3 feet along the ceiling grid
C) Calculate the total bundled cable weight per section and install a trapeze/ladder rack system rated and spaced to support that calculated load
D) Bundle all cables with hook-and-loop straps and suspend them directly from the rack tops without a dedicated support structure

---

**Q35.** Which overhead cable support structure is specifically designed to distribute the weight of large bundled cable runs across multiple support points in a high-density AI cluster row?

A) Single-point J-hooks
B) Wire basket tray sized for light network cabling
C) Trapeze/ladder cable rack
D) Loose Velcro cable ties spanning between racks

---

**Q36.** During installation, a team is dressing InfiniBand cable runs between a leaf switch and a row of GB200 NVL72 compute racks. What is the PRIMARY reason for leaving a calculated slack (service) loop at each termination point rather than pulling cables taut end-to-end?

A) It reduces the total number of cable ties required for the bundle
B) It allows future moves, adds, and changes (such as re-terminating or relocating a connection) without having to re-run the entire cable
C) It is required to meet the minimum bend radius specification of the cable, regardless of future service needs
D) It lowers the bit error rate (BER) of the optical link by adding extra fiber length

---

**Q37.** A newly installed InfiniBand fiber link shows a link-up status but is experiencing intermittent packet retransmissions with a bit error rate (BER) above the acceptable threshold, even though the connector appears properly seated. Which troubleshooting step should be performed FIRST?

A) Replace the switch ASIC on the affected port
B) Inspect and clean the fiber connector end-faces using an optical fiber inspection scope and approved cleaning kit
C) Increase the cable's forward error correction (FEC) setting in the switch software
D) Swap the cable for a longer-length variant of the same type

---

**Q38.** During final deployment verification of an InfiniBand fiber run, you need to confirm that the actual optical receive power at the connector falls within the transceiver's specified operating range. Which tool should you use?

A) Optical power meter
B) Digital multimeter
C) Cable continuity tester
D) Thermal imaging camera

---

**Q39.** During a final quality inspection of high-density InfiniBand fiber cabling in a GB200 NVL72 rack, an inspector checks that cables are not bent tightly enough to risk signal loss. What is the generally accepted minimum bend radius rule for fiber cable that has already been installed and is at rest (no tension)?

A) No less than 1x the cable's outer diameter
B) No less than 2x the cable's outer diameter
C) Bend radius restrictions no longer apply once the cable is terminated
D) No less than 10x the cable's outer diameter

---

**Q40.** A rack technician observes that one InfiniBand link shows 'link down' with no light detected at the receiver, while a second cable in the same rack shows 'link up' but reports an elevated bit error rate (BER). What does this difference most likely indicate?

A) Both issues share the same root cause: outdated NIC firmware
B) The link-down cable is a software configuration issue, while the high-BER cable is a hardware failure
C) The link-down cable likely has a physical break, unseated connector, or failed transceiver, while the high-BER cable likely has contamination or a minor signal-integrity issue
D) Both symptoms indicate the switch port is administratively disabled and simply need re-enabling

---

**Q41.** After completing cabling installation on a GB200 NVL72 rack, the deployment team photographs each cable run and produces an as-built diagram. What is the PRIMARY purpose of this documentation step?

A) To provide marketing material for customer case studies
B) To calculate the total power draw for the rack's rPDUs
C) To replace the need for BER and link-state testing
D) To provide an accurate record of the physical installation for future troubleshooting, audits, and maintenance

---

**Q42.** A technician is assigned to service an rPDU feeding a live GB200 NVL72 rack drawing over 120 kW. What is the correct first step before beginning any work on the unit?

A) De-energize the circuit, apply lockout/tagout devices, and verify a zero-energy state with an appropriate tester before starting work
B) Wear insulated gloves and work on the live circuit while a partner monitors
C) Ask a colleague to hold the breaker in the off position while you work
D) Disable the rack's UID indicator light to signal work in progress

---

**Q43.** InfiniBand and network cabling for an AI cluster must be routed through the open plenum space above a suspended ceiling used for HVAC return air. Which cable jacket rating satisfies NEC requirements for this installation?

A) CMR (riser-rated)
B) CM (general purpose)
C) CMX (limited-use residential)
D) CMP (plenum-rated)

---

**Q44.** A technician must perform live diagnostic testing on an energized rPDU bus rated above 120 kW in a high-density AI rack row. Per standard electrical safety practice, which PPE is mandatory before starting the work?

A) Standard cotton lab coat with safety glasses only
B) An ESD wrist strap and antistatic smock
C) Arc-rated flash suit, insulated gloves rated for the circuit's voltage class, and voltage-rated tools
D) Steel-toe boots and a hard hat only

---

**Q45.** According to NVIDIA installation standard DU-10438, which practice during InfiniBand fabric installation can void the hardware warranty?

A) Installing non-NVIDIA-qualified optical transceivers or cables in the InfiniBand fabric
B) Labeling all cable ends with color-coded tags
C) Routing cables through overhead cable trays instead of underfloor
D) Recording serial numbers of all installed components

---

**Q46.** Before handling a GB200 compute tray or NVLink switch module removed from an ESD-protected packaging area, what is the minimum required protection?

A) Wear a grounded ESD wrist strap connected to a common ground point at the ESD-protected work area
B) Wash hands with antistatic soap before handling the module
C) Wear insulated rubber electrical gloves
D) Ground only the rack chassis; personal grounding is unnecessary if the rack is grounded

---

