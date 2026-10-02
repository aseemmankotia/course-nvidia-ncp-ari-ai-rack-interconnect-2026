## Chapter 10: Final Inspection, Documentation, and BER Troubleshooting — Flashcards

| # | Front (Question) | Back (Answer) |
|---|-----------------|---------------|
| 1 | What does a 'link-down' (LOS) condition indicate vs a 'high-BER' condition? | Link-down = total loss of signal, interface fails to negotiate. High-BER = link stays up/negotiated but data has excessive errors. Exam tip: don't confuse a degraded link with a dead link. |
| 2 | Symptom pattern: errors clear after cleaning connectors but return within hours. | Indicates contamination/dirty end-face (dust, oil) being reintroduced, not a permanent fiber defect. Re-clean and inspect with a fiber scope. |
| 3 | Symptom pattern: OTDR shows a loss event at a specific distance correlating with a tight cable loop. | Indicates over-bending (macrobend) at that physical location — go correct the bend, cleaning will NOT fix this. |
| 4 | Three items on the final deployment quality inspection checklist | 1) Bend radius compliance 2) Cable/port labeling 3) Airflow clearance around active equipment. All three are heavily tested. |
| 5 | What must as-built photo documentation include? | Legible cable labels at BOTH ends of each run + overall rack/patch panel context photo, matching the as-built diagram. |
| 6 | Escalation procedure order for persistent BER faults | 1) Clean connectors 2) Verify bend radius 3) Re-terminate/replace patch cords 4) If still failing, escalate to Tier 2/engineering WITH test results and OTDR trace attached — don't repeat the same fix blindly. |
| 7 | Dirty connector vs over-bend: which is typically reversible? | Dirty connector contamination is reversible by cleaning. Over-bending can cause permanent microfracture/attenuation damage to the fiber core — not always reversible. |
| 8 | What test tool identifies the physical location of a bend or break along a fiber run? | OTDR (Optical Time-Domain Reflectometer) — shows loss/reflectance events plotted against distance. |
| 9 | BER acceptance criterion vs link-up status — which governs sign-off? | BER against the documented acceptance threshold governs pass/fail sign-off, NOT whether the link is simply up and passing some traffic. |
| 10 | Why is minimum bend radius tested so heavily on this exam? | Because violating it causes macrobend attenuation and potential permanent core damage — a leading real-world cause of intermittent, hard-to-diagnose signal-integrity faults. |
| 11 | What should you do BEFORE re-terminating a connector to fix suspected contamination? | Inspect the end-face with a fiber inspection scope and clean with a one-click cleaner or wipe/solvent first — re-termination should not be the first response to a cleaning-fixable issue. |
| 12 | What information must accompany an escalation ticket for a persistent signal-integrity fault? | OTDR trace, BER test results/thresholds, and the list of remediation steps already performed (cleaning, bend check, re-termination) — undocumented escalations are a checklist failure. |
