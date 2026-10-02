## Ch.7 Cheat Sheet — Routing, Bend Radius, Dressing

### 50/50 Left-Right Routing (NVL72-class)
| Rule | Detail |
|---|---|
| Split ratio | ~50% cables left channel, ~50% right channel |
| Why | Prevents single-channel overfill, airflow blockage, thermal hotspots |
| Violation symptom | Forced tight bends at tray exit, congestion, hotspots |

### Bend Radius
| Item | Value/Rule |
|---|---|
| Minimum bend radius | ~30mm (exam benchmark) |
| Applies to | Both fiber AND copper cabling |
| Fiber violation effect | Micro-bend/macro-bend attenuation, signal loss, possible fracture |
| Copper violation effect | Impedance mismatch, signal degradation |
| Exam trap | Assuming only fiber is bend-sensitive — copper is too |

### Bundling Methods
| Method | Use Case | Verdict |
|---|---|---|
| Hook-and-loop (Velcro) | Fiber/copper bundles in high-density trays | ✅ Preferred — even pressure distribution |
| Zip ties | General low-density copper only | ⚠️ Avoid on fiber — point-load crush risk |
| Metal clamps | — | ❌ Too rigid, crushes cores |
| Adhesive clips on jacket | — | ❌ Not standard, adds stress |

### Color-Coding
| Purpose | Enable fast visual ID of cable function (mgmt/data/inter-rack) without tracing |
| Exam note | Not for manufacturer/warranty ID; not a fire-code substitute |

### Cable Slack Allocation
| Rule | Detail |
|---|---|
| Purpose | Allow one service loop for re-termination/maintenance |
| Constraint | Must not create bulk violating bend-radius at tray points |
| Trap | Zero slack = no serviceability; fixed "1m always" is not a real spec |

### TIA-606 Labeling
| Requirement | Detail |
|---|---|
| Minimum content | Unique ID linking origin ↔ destination endpoint |
| Purpose | Enable troubleshooting/MACs without physical tracing |
| Not required | Installer initials, manufacture date, part number alone |

### Common Exam Traps
1. Routing all cables down one channel to "save time" → overfill + bend violations.
2. Using zip ties on fiber bundles → point-load fiber damage.
3. Thinking bend-radius rules apply only to fiber, not copper.
4. Zero slack for a "cleaner look" → fails serviceability requirement.
5. Labeling with only part number/date → fails TIA-606 traceability requirement.
