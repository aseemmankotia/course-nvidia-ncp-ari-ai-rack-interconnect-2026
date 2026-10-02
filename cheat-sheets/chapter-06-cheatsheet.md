## Chapter 6 Cheat Sheet — Fiber Installation & Transceiver Handling

### APC vs UPC Polish
| Attribute | APC | UPC |
|---|---|---|
| Angle | 8° angled | Flat |
| Color | Green | Blue |
| Back reflection | ~-60 dB | ~-50 to -55 dB |
| Use case | Single-mode, low-reflection links | Multimode, general SMF |
| Mate together? | **NEVER** — damages ferrules | — |

### SMF Transceiver Reach (100G family)
| Transceiver | Fiber | Max Reach |
|---|---|---|
| SR4 | OM4 MMF | ~70-100 m |
| CWDM4 | SMF | ~2 km |
| LR4 | SMF | 10 km |
| ER4 | SMF | 40 km |

**Rule:** Select the shortest/cheapest transceiver that still meets the required link distance — exam frequently tests over-provisioning (choosing LR4 for a 500m run).

### MPO Polarity Methods
| Method | Connector Keying | Fiber Mapping |
|---|---|---|
| A | Key-up ↔ Key-down | Straight |
| B | Key-up ↔ Key-up | Reversed internally |
| C | Key-up ↔ Key-down | Adjacent pairs crossed |

### Connector Cleaning Procedure
1. Dry-clean with click-type or cassette cleaner.
2. Inspect endface with fiber inspection scope (400x).
3. If contamination remains, wet-clean with isopropyl alcohol wipe/stick.
4. Re-inspect before mating.
**Never** mate an unverified connector — leading cause of high insertion loss/link failure.

### Transceiver Handling
- Two-handed insertion, steady pressure until latch **clicks**.
- Verify seating via LED + CLI link status, not feel alone.
- Install dust caps immediately when disconnected.
- Use ESD wrist strap and ESD-safe bags for storage/transport.
- Never force removal — release latch mechanism first.

### Top Exam Traps
1. Mating APC to UPC (color-code mismatch) — physical ferrule damage.
2. Skipping clean/inspect step before mating — causes intermittent high-error links.
3. Selecting an over-reach transceiver (e.g., LR4 for a <100m run) instead of matching distance to spec.
4. Confusing MPO Method A/B/C wiring during breakout cabling — causes TX/RX polarity failures.
