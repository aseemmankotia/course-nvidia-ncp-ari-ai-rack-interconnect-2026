# Chapter 2 Cheat Sheet — Cooling & GB200 NVL72 Rack Anatomy

## GB200 NVL72 Core Specs
| Item | Value |
|---|---|
| GPUs per rack | 72 (Blackwell) |
| Grace CPUs per rack | 36 |
| Compute trays | 18 (2 Grace CPU + 4 GPU 'Bianca' board each) |
| NVLink Switch trays | 9 |
| Total rack power draw | ~120kW |
| NVLink 5 per-GPU bandwidth | 1.8 TB/s bidirectional |
| NVLink domain aggregate bandwidth | 130 TB/s |
| InfiniBand NDR speed | 400 Gb/s per port |

## Rack Anatomy Layers
| Layer | Function |
|---|---|
| Compute trays | Host Grace CPUs + Blackwell GPUs (Bianca boards) |
| NVSwitch trays | Provide NVLink switching fabric across all 72 GPUs |
| Power shelves | Deliver DC power to compute/switch trays |
| Cooling manifolds | Distribute liquid coolant to cold plates on each tray |

## Cooling: CDU Role
- CDU = interface between **facility water loop (FWS)** and rack's **technology cooling loop (TCS)**
- Manages: heat exchange, flow rate, pressure, coolant quality/filtration
- Sits at row-level or rack-level, feeds cooling manifolds
- **Exam trap:** CDU ≠ cold plate. CDU is the exchange/distribution unit; cold plates are on the compute trays themselves.

## Liquid vs Air Cooling
| Aspect | Air Cooling (CRAH) | Liquid Cooling (CDU + cold plates) |
|---|---|---|
| Typical capacity/rack | ~20kW | 100kW+ (matches GB200 NVL72 ~120kW) |
| Use case | Low-density legacy racks | High-density AI racks (GB200 NVL72) |
| Failure mode | Thermal throttling at high density | Requires leak detection, coolant monitoring |

## Containment Strategy
| Type | Seals | Best for |
|---|---|---|
| Cold-aisle containment | Cold aisle only | Mixed-density rooms, simpler retrofit |
| Hot-aisle containment | Hot aisle only, ducts to CRAH return | High-density racks (GB200 NVL72) — preferred |

**Exam trap:** Hot-aisle containment is generally preferred for very high-density racks because it directly returns hot exhaust to cooling units, minimizing room-level temperature rise.

## Interconnect Roles
| Fabric | Scope | Speed |
|---|---|---|
| NVLink | Intra-rack GPU-to-GPU (NVL72 domain) | 1.8TB/s/GPU, 130TB/s aggregate |
| InfiniBand | Inter-rack/node scale-out | 400Gb/s/port (NDR) |
| Ethernet | Scale-out alt / management / storage | Varies (e.g., Spectrum-X) |

**Exam trap:** NVLink never leaves the rack in NVL72 — cross-rack traffic requires InfiniBand or Ethernet.

## Cooling Capacity Verification Rule
Rack cooling capacity (CDU rating) **must** meet or exceed total rack power draw (~120kW), since nearly all electrical power converts to heat. Undersized CDU → thermal throttling or shutdown.
