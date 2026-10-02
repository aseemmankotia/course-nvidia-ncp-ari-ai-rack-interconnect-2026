## Chapter 3 Cheat Sheet: Site Assessment Before Deployment
**Exam Domain:** Pre-Deployment Planning and Site Assessment (11%)

### Floor Load Capacity
| Item | Value |
|---|---|
| Standard raised floor rating | 150-250 lbs/sq ft (732-1,220 kg/m²) |
| GB200 NVL72 rack weight | ~1,362 kg (3,000 lbs) |
| Rack footprint (typical) | ~0.72 m² (7.75 sq ft) |
| Rule | Concentrated load (lbs/sq ft) = rack weight ÷ footprint. If it exceeds floor rating → escalate to structural engineer |
| Static vs. dynamic load | Rolling path during delivery may require higher momentary rating than resting position |

### Clearance Verification
| Clearance Type | Minimum |
|---|---|
| NEC front working clearance (0-150V to ground, Condition 1) | 36 in (914 mm) |
| Typical rear service/airflow clearance | 30 in (762 mm) |
| Hot/cold aisle width (industry common practice) | ~42 in (1.07 m) minimum for tile access |

**Exam trap:** Don't confuse the 36-in NEC front clearance (code requirement) with the 30-in rear clearance (vendor/airflow spec) — they answer different questions.

### Environmental Readiness
| Parameter | ASHRAE Class A1 |
|---|---|
| Recommended temp range | 18-27°C (64-80°F) |
| Allowable temp range (wider) | up to ~32°C |
| Liquid cooling | Facility CDU supply temp/flow must match rack spec before power-on |

**Exam trap:** Questions often give a temperature within the *allowable* range but outside the *recommended* range — read carefully which envelope is being asked about.

### Process Order (Survey → Assessment → Install)
1. **Site Survey** — physical measurements: clearances, pathways, power drops, floor condition
2. **Documentation Review** — validate physical network design docs against survey findings
3. **Site Assessment** — synthesize survey + docs + readiness data into go/no-go decision
4. **Inventory Check** — verify all shipped components against manifest
5. **Install**

### Pre-Install Documentation Package Checklist
- [ ] Physical network design drawings (as-built validated)
- [ ] Floor load / structural assessment
- [ ] Environmental readiness report (power, cooling, thermal zone)
- [ ] Cable pathway and clearance survey
- [ ] Inventory manifest reconciliation

**Common Mistake:** Choosing to "proceed with install" because equipment physically fits, without validating floor load or clearance codes — the exam consistently rewards escalation/verification answers over convenience answers.
