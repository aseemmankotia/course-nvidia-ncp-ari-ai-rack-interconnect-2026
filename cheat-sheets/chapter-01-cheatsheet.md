# Chapter 1 Cheat Sheet: AI Rack Power Fundamentals

## Redundancy Levels
| Level | Description | Survives |
|---|---|---|
| N | Bare minimum, no spare | Nothing — any failure = outage |
| N+1 | One spare unit on a shared path | Single component failure |
| 2N | Two fully independent, full-capacity paths | Complete failure of one entire path |
| 2N+1 | Two independent paths, each with a spare unit | Full path failure + one extra component failure |

**Exam trap:** N+1 ≠ 2N. N+1 shares a common path; 2N duplicates the path entirely.

## AC vs DC Rack Architecture
| Aspect | AC Architecture | DC Architecture (e.g., -48VDC busbar) |
|---|---|---|
| Distribution | 208/400V AC to rPDUs → per-server PSU converts to DC | DC delivered directly via busbar, no per-server AC-DC stage |
| Conversion losses | Higher (multiple AC-DC-AC stages) | Lower (fewer conversion stages) |
| Typical use | Traditional/legacy racks | High-density AI racks (GB200-class) |

## Power Capacity Math (80% Continuous-Load Rule)
- Usable capacity = Rated capacity x 0.80
- 30A breaker → 24A max continuous
- 3-phase power: P(kVA) = √3 x V(line-line) x I(A)
  - Example: 208V, 60A/phase → ~21.6 kVA rated → 17.28kW usable (derated)
- Single-phase: P(kW) = V x I
  - Example: 208V, 30A → 6.24kW rated → 4.99kW usable (derated)

## GB200 NVL72 Power Awareness
- Rack draw: **~120kW class** (vs ~10-15kW traditional air-cooled rack)
- Drives adoption of DC busbar distribution + liquid cooling
- Always **round UP** when calculating PDU counts per feed: e.g., 120kW ÷ 17.28kW usable/PDU = 6.94 → 7 PDUs per feed

## rPDU Phase Balancing
- Goal: equal current draw across Phase A/B/C
- Risk of imbalance: one phase's breaker trips while others have spare capacity → partial outage despite available rack headroom
- **Intelligent rPDUs** = per-phase metering + remote monitoring to detect/correct imbalance proactively

## Grounding Verification (High-Density Racks)
- Verify continuous, low-resistance bonding path: rack frame → facility grounding grid
- Required for both AC and DC architectures
- Never rely on visual inspection alone — measure continuity/resistance before energizing

## Quick Reference: Common Exam Traps
1. Forgetting to apply 80% derating before sizing PDUs/breakers
2. Confusing N+1 (shared path) with 2N (independent paths)
3. Assuming DC architecture removes the need for grounding — it does not
4. Rounding PDU count DOWN instead of UP in capacity calculations
5. Assuming overall rack capacity is sufficient without checking per-phase balance
