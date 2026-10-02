## Chapter 5 Cheat Sheet: Cable and Transceiver Selection

### Copper Cable Reach by Speed (NDR/XDR)
| Cable Type | Signal | Typical Max Reach | Notes |
|---|---|---|---|
| Passive DAC | Passive | ~2m at NDR (400G) | Cheapest, no power draw, shortest reach |
| ACC (Active Copper) | Active equalization | ~5m at NDR (400G) | No optics cost, extends copper reach |
| AOC (Active Optical) | Optics + MMF | ~30m | Used when reach exceeds copper limits |

**Exam rule of thumb:** In-rack (<2m) → DAC. Adjacent rack (~5m) → ACC. Row-to-row (~30m) → AOC. Beyond ~30m or across rows → transceiver + fiber patch (MMF/SMF).

### Transceiver Form Factors
| Form Factor | Max Speed | Lanes | Notes |
|---|---|---|---|
| QSFP56 | ~200Gb/s (NDR200) | 4 | Smaller, used for split NDR links |
| QSFP-DD | 400Gb/s | 8 | Higher density, lower power than OSFP |
| OSFP | 400–800Gb/s (NDR/XDR) | 8 | Largest thermal envelope, required for XDR (800G) |
| SFP-DD | Low speed | 1–2 | Not used for NDR/XDR fabrics |

**Exam trap:** OSFP and QSFP-DD are NOT bidirectionally interchangeable — OSFP cages may accept QSFP-DD via adapter, not the reverse.

### Fiber Type Comparison
| Type | Optics | Reach | Cost |
|---|---|---|---|
| MMF (OM3/OM4) | VCSEL | Tens of meters up to ~100m | Lower |
| SMF | Laser diode | 500m (DR) → 2km (FR) → 10km (LR) → 40km (ER) | Higher |

**Exam trap:** Mismatching MMF-rated transceivers with SMF cabling (or vice versa) prevents link-up — always match transceiver spec to fiber type.

### InfiniBand Speed Reference
| Generation | Speed | Lanes |
|---|---|---|
| NDR | 400Gb/s | 8x50G PAM4 |
| XDR | 800Gb/s | Requires OSFP |

**NDR splitter:** 1 NDR port (400G) → 2x NDR200 (200G) via Y-cable.

### NVIDIA Cable Identification (LinkX)
- NVIDIA cables/transceivers carry an identification EEPROM validated by switch/NIC firmware.
- Common LinkX prefixes: **MCP** = passive copper (DAC), **MCA** = active copper (ACC), **MFA/MFS** = active fiber (AOC).
- Third-party cables may physically fit and even link, but firmware may log them as **unqualified**, and NVIDIA support/diagnostics coverage is not guaranteed.
- Exam focus: correctly identify NVIDIA-branded vs generic cable based on part-number prefix and behavior, not just physical connector type.

### Quick Decision Flow
1. Distance <2m, same rack → **Passive DAC**
2. Distance ~2–5m → **ACC**
3. Distance up to ~30m, MMF available → **AOC**
4. Distance >30m or campus/long-haul → **SMF transceiver + fiber patch**
5. Speed = 800G → **must use OSFP**
6. Speed = 400G, density/power priority → **QSFP-DD**
