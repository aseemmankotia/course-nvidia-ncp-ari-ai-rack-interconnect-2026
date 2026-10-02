# Chapter 4 Cheat Sheet: Preparing the Rack for High-Density Install

## GB200 NVL72 Rack Basics
| Attribute | Value |
|---|---|
| Compute | 72 Blackwell GPUs + 36 Grace CPUs per rack |
| Cooling | Liquid-cooled via CDU (Coolant Distribution Unit) |
| Weight (loaded) | Up to ~1,360 kg (3,000 lb) |
| Footprint | 600mm (W) x 1200mm (D) — wider/deeper than standard 600x1000/1070mm racks |
| Reason for wider rack | CDU manifolds, high-current busbars, dense NVLink harness routing |

**Exam gotcha:** Standard enterprise rack depth is NOT sufficient for GB200 NVL72 — always confirm structural floor loading BEFORE install; standard tile ratings are often exceeded.

## Containment Clearance Specs
| Clearance Point | Minimum Recommended |
|---|---|
| Front-post-to-front-door | 1000mm (39.4 in) — tray slide-out, CDU hose service |
| Rear-post-to-rear-door | ≥1000mm — hose routing, rear-door heat exchanger service |
| Cold aisle / inter-row spacing | 1200mm (48 in) minimum |
| Hot aisle spacing | ~900mm minimum (narrower than cold aisle) |
| NEC 110.26 electrical workspace (0-150V) | 36 in (914mm) minimum — code baseline, separate from vendor spec |

## Cable Management Accessories
| Accessory | Purpose |
|---|---|
| Vertical cable manager/duct | Bulk vertical routing, side-of-rack |
| Horizontal cable manager | Lateral routing at equipment U-position; install every 4-6U |
| Bend-radius guide/finger duct | Enforces minimum bend radius, prevents attenuation/damage |

**Fiber bend radius (TIA-568):** 10x OD unloaded / 15x OD under tension.

## EMI Mitigation (Power vs. Data Pathways)
| Rule | Spec |
|---|---|
| Min. parallel separation (power vs. copper data) | 150mm (6 in) per TIA-569-C |
| Crossing method when unavoidable | 90° perpendicular crossing |
| Fiber vs. copper | Fiber is EMI-immune — separation rule targets copper data only |
| Standard layout | Power in bottom trays/busbars; data/fiber in top trays or opposite-side vertical managers |

## Quick Exam Rules
- Verify floor/structural load rating BEFORE any high-density rack install.
- 600x1200mm footprint = flag for extra-wide/deep rack requirement.
- Front AND rear clearance both matter for liquid-cooled service access — don't assume front-only.
- Cold aisle > hot aisle spacing in high-density containment designs.
- EMI separation applies to copper data lines, not fiber.
- Horizontal managers every 4-6U prevent airflow/service blockage.
