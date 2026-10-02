## Chapter 11 Cheat Sheet: Safety & Compliance in High-Power Environments

### LOTO — Six-Step Procedure (OSHA 1910.147)
| Step | Action |
|---|---|
| 1 | Prepare — identify all energy sources |
| 2 | Notify affected personnel |
| 3 | Shutdown equipment |
| 4 | Isolate & apply lock/tag |
| 5 | Release stored energy (capacitors, springs, hydraulics) |
| 6 | Verify zero energy with a rated meter |

**Group lockout:** every exposed worker applies their OWN lock/tag — never share.

### Cable Flame Ratings (NEC Art. 800)
| Rating | Location | Substitution Rule |
|---|---|---|
| CMP (Plenum) | Air-handling plenum spaces | Can replace CMR or CM |
| CMR (Riser) | Vertical floor-to-floor shafts | Can replace CM only |
| CM (General) | Standard non-plenum, non-riser | Cannot replace CMR/CMP |

**Memory trick:** Higher tier (P > R > general) can always substitute downward, never upward.

### NVIDIA DU-10438 Compliance
- Mandatory torque values on all power/busbar connections
- Specified grounding/bonding procedures for racks and cooling loops
- Defined cable bend radius and labeling standards
- **Non-compliance = voided warranty + real fire/overheating risk** (loose high-current connections generate resistive heat)

### Arc-Flash Awareness (NFPA 70E)
| PPE Category | Approx. Incident Energy |
|---|---|
| 1 | ~4 cal/cm² |
| 2 | ~8 cal/cm² |
| 3 | ~25 cal/cm² |
| 4 | ~40 cal/cm² |

- **Arc-flash boundary:** minimum safe distance without PPE
- 120kW+ racks (e.g., GB200 NVL72-class, ~120kW/rack) require site-specific incident energy calculations — never assume a fixed category

### ESD Protection
- Sensitive components (GPU dies, ICs) can be damaged by discharges as low as **~100V** — far below human perception (~3,000V)
- Required: grounded wrist strap on bare skin + ESD mat, both tied to a common ground point
- Never use carpeted flooring or plain cardboard for ESD-sensitive parts

### Exam Traps
1. Thinking one technician's lock covers a whole crew (it doesn't — group lockout required)
2. Confusing CMR and CMP use cases (riser ≠ plenum)
3. Assuming breaker-off = safe to touch without meter verification
4. Treating DU-10438 torque specs as optional best-practice rather than mandatory compliance
