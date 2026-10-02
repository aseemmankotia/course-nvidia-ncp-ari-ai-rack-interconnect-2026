## Chapter 11: Safety and Compliance in High-Power Environments — Flashcards

| # | Front (Question) | Back (Answer) |
|---|-----------------|---------------|
| 1 | OSHA LOTO six-step order? | 1) Prepare 2) Notify 3) Shutdown 4) Isolate/Lock-Tag 5) Release stored energy 6) Verify zero energy. Exam tip: verification requires a rated meter test, not a visual check. |
| 2 | NEC cable substitution hierarchy: CMP vs CMR vs CM? | CMP (Plenum) is highest-rated and can substitute for CMR and CM. CMR (Riser) can substitute for CM only. CM cannot substitute upward for either. Exam tip: hierarchy only flows downward (higher can replace lower). |
| 3 | Minimum cable rating required in a floor-to-floor riser shaft? | CMR (Communications Riser). CMP also qualifies (higher rating), but CM does not. Memory trick: 'Riser needs R.' |
| 4 | Approximate power draw of an NVIDIA GB200 NVL72-class rack? | ~120kW per rack. Exam tip: this power density is the reference point for '120kW+ high-power environment' safety questions requiring enhanced arc-flash and LOTO precautions. |
| 5 | NFPA 70E arc-flash PPE categories — general range? | Category 1 (~4 cal/cm²) through Category 4 (~40 cal/cm²). Actual PPE selection is based on calculated incident energy for the specific equipment, not a fixed table lookup alone. |
| 6 | At what discharge voltage can ESD damage sensitive electronic components like GPU dies? | As low as ~100V — far below the ~3,000V threshold at which humans can feel a static shock. Exam tip: 'if you can't feel it, it can still kill the chip.' |
| 7 | Group lockout requirement when multiple technicians work on the same circuit? | Each individual must apply their own personal lock and tag; a circuit cannot be re-energized until every worker has removed their own lock. One person's lock does not cover another worker's safety. |
| 8 | Why does skipping torque specs on DU-10438 busbar connections matter? | Voids NVIDIA warranty coverage AND creates a real hazard — under-torqued connections cause high resistance, heat buildup, and potential arcing/fire in high-power racks. |
| 9 | What is an 'arc-flash boundary'? | The calculated distance from an energized source at which a person could receive a second-degree burn from an arc-flash event. Workers inside this boundary must wear PPE matched to the calculated incident energy. |
| 10 | Correct ESD wrist strap setup when handling GPU modules? | Strap must be worn on bare skin and connected to a common ground point shared with the ESD mat — creating a continuous verified path to ground, not just momentary contact. |
| 11 | Cable rating substitution memory trick? | 'P beats R beats nothing' — CMP > CMR > CM in fire-resistance ranking; higher letter tier can always replace a lower one, never the reverse. |
| 12 | How must zero energy state be verified before starting work (LOTO step 6)? | Using a properly rated meter to test for absence of voltage on the isolated circuit — never by visual inspection or assumption based on breaker position alone. |
