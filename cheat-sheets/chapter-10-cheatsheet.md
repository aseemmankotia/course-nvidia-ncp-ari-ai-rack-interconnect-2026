## Chapter 10 Cheat Sheet — Final Inspection, Documentation, BER Troubleshooting

### Final Deployment Quality Checklist (3 pillars — heavily tested)
| Check | Failure Example | Fix |
|---|---|---|
| Bend radius | Visible kink, tight loop on cable manager post | Reroute, remove tight loop, verify against spec |
| Labeling | Missing/illegible ID at either cable end | Re-label both ends, match as-built diagram |
| Airflow | Cable bundle blocking equipment exhaust vents | Reroute bundle away from vents |

### Link-Down vs High-BER
| Condition | Link State | Root Cause Class | Typical Fix Path |
|---|---|---|---|
| Link-down (LOS) | No negotiation, no light detected | Total break, unplugged, dead optic, wrong fiber type | Physical continuity check, swap optic/patch |
| High-BER | Link up, traffic passes with errors | Degraded signal (dirty connector, bend, marginal loss budget) | Clean → check bend → re-terminate → escalate |

### Dirty Connector vs Over-Bending
| Fault | Signature | Reversible? | Fix |
|---|---|---|---|
| Dirty connector | Errors clear after cleaning, recur later | Yes | Inspect end-face, clean, re-test |
| Over-bending | OTDR loss event at fixed distance, correlates with physical kink | Not always — may be permanent | Locate bend, correct routing, may require re-cabling |

### BER Interpretation
- BER is expressed as errors per bits transmitted (e.g., 1 x 10^-9, 1 x 10^-12).
- Lower exponent magnitude (more negative) = better quality (fewer errors).
- Sign-off is based on meeting the documented acceptance threshold for the link type — **link-up status alone does NOT equal a pass**.
- A BER that is orders of magnitude above the accepted threshold is a fail even if traffic is flowing.

### Escalation Procedure (persistent signal-integrity fault)
1. Clean all connectors, re-inspect end-face with fiber scope.
2. Verify bend radius along entire run.
3. Re-terminate or swap patch cords.
4. Re-test BER against threshold.
5. If still failing → escalate to Tier 2/engineering with OTDR trace, BER results, and list of steps already performed.

### As-Built Documentation Requirements
- As-built diagram must reflect actual routing/labeling, not original design intent (redline any deviations).
- Photo documentation: legible label at **both ends** of every cable run + overall rack/patch panel context photo.
- Test results (BER, loss budget, OTDR traces) must be attached to the as-built package before final sign-off.

### Common Exam Traps
- Assuming a link that is 'up' automatically passes BER testing — it does not.
- Confusing over-bend damage with contamination symptoms — cleaning will NOT fix a bend-induced loss event.
- Skipping documentation steps when escalating — undocumented escalations fail the process checklist even if the technical fix is correct.
