## Chapter 9 Cheat Sheet: Continuity and Link Testing

### Test Sequence (order matters — exam trap)
| Stage | What's Tested | Purpose |
|---|---|---|
| Pre-test | Raw cable/reel before install | Catch manufacturing defects |
| Post-install | Fully terminated end-to-end link | Catch connector/routing loss |

Never skip pre-test; never reverse the order.

### Continuity Test Faults (Copper)
| Result | Meaning | Action |
|---|---|---|
| Open | Broken conductor / bad termination | Replace or re-terminate |
| Short | Two conductors unintentionally joined | Replace or re-terminate |
| Miswire | Pins mapped incorrectly | Re-terminate to correct pinout |
| Pass | Continuous, correctly mapped pins | Proceed to log/next test |

### Optical Power Meter (OPM) — Fiber Loss Budget
| Element | Typical Value |
|---|---|
| Connector pair loss (TIA-568.3-D) | ≤0.75 dB |
| OM3/OM4 attenuation @850nm | ≤3.5 dB/km |
| Singlemode (OS2) @1310/1550nm | ≤0.4 dB/km |

Budget = (connector count × 0.75 dB) + (fiber length km × attenuation/km). Measured loss > budget = FAIL → clean/re-terminate → re-test before hardware swap.

### Link Status States (Exam Trap)
| State | Meaning |
|---|---|
| LinkUp/Active | Physical + logical link established |
| LinkDown | No physical connection negotiated |
| Polling | Actively negotiating, not resolved |
| Disabled | Administratively shut down |

Do not confuse Disabled (config) with LinkDown (no negotiation).

### Differentiating NVIDIA vs Non-NVIDIA Cabling
| Tool | Command | Reveals |
|---|---|---|
| mlxlink | `mlxlink -d mlx5_0 -m` | Vendor Name/PN from cable EEPROM, cable health |
| ethtool | `ethtool -m <iface>` | Module EEPROM: vendor, part number, serial, DOM |
| ibstat | `ibstat` | Port link state (IB) |

The **Vendor Name/Part Number EEPROM field** is the authoritative check — not link speed or port location, which any cable meeting spec can achieve.

### Documentation Log — Required Fields
- Cable ID / endpoint locations
- Measured value (actual dB loss or continuity result — not just pass/fail)
- Test equipment used (and calibration ref if applicable)
- Technician name
- Timestamp

Common mistake: logging only pass/fail with no measured value — fails audit traceability.

### Quick Decision Rules
- Measured loss > budget → clean/inspect → re-test → THEN escalate/replace.
- Continuity open/short → replace cable, no re-test workaround.
- Unknown cable vendor suspected → check EEPROM via mlxlink/ethtool -m, don't assume from physical appearance.
