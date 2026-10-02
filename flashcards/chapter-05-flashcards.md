## Chapter 5: Cable and Transceiver Selection — Flashcards

| # | Front (Question) | Back (Answer) |
|---|-----------------|---------------|
| 1 | Passive DAC max reliable reach at NDR (400Gb/s) signaling? | ~2 meters. Beyond this, signal integrity degrades. Exam tip: DAC = cheapest, shortest reach, no active components. |
| 2 | Active Copper Cable (ACC) max reach at NDR speeds? | ~5 meters. ACC adds active equalization/re-timing chips at each end to extend copper reach beyond passive DAC limits. |
| 3 | AOC (Active Optical Cable) typical max reach with MMF? | Up to ~30 meters. Used when reach exceeds copper (DAC/ACC) limits but full SMF distance isn't needed. |
| 4 | NVIDIA NDR InfiniBand port speed and lane structure? | 400Gb/s per port, 8 lanes x 50Gb/s PAM4. Exam tip: can be split into 2x NDR200 (200Gb/s) via Y-cable. |
| 5 | NVIDIA XDR InfiniBand port speed? | 800Gb/s per port — next generation after NDR, requires OSFP form factor for thermal/power headroom. |
| 6 | Common SMF optic reach tiers tested on the exam? | DR ~500m, FR ~2km, LR ~10km, ER ~40km. Longer reach = more expensive laser optics. |
| 7 | OSFP vs QSFP-DD — which supports higher power/thermal envelope? | OSFP. Larger mechanical size allows higher power dissipation, needed for 800G (XDR) optics. QSFP-DD favors density and lower power at 400G. |
| 8 | DAC vs ACC vs AOC — when to choose each? | DAC: shortest reach (~2m), cheapest, passive. ACC: medium reach (~5m), active copper, no optics cost. AOC: longest reach (~30m), uses optics over MMF, highest cost of the three. |
| 9 | MMF vs SMF — key selection difference? | MMF: VCSEL optics, short reach (tens of meters to ~100m), lower cost. SMF: laser-diode optics, long reach (500m–40km), higher cost. Exam tip: match fiber type to transceiver — mismatched MMF/SMF optics will not link. |
| 10 | Are OSFP and QSFP-DD modules physically interchangeable? | No — OSFP is mechanically larger. Some OSFP cages accept QSFP-DD modules via adapter, but the reverse does not work. Exam trap: assuming they're drop-in compatible. |
| 11 | NDR port splitter (Y-cable) breakout pattern? | 1x NDR (400Gb/s, 8 lanes) splits into 2x NDR200 (200Gb/s, 4 lanes each). Used to connect two hosts to one switch port. |
| 12 | Risk of using third-party (non-NVIDIA LinkX) cables/transceivers in NVIDIA gear? | Firmware may log cable as unqualified/unrecognized via EEPROM ID check; NVIDIA support and full cable diagnostics may not be honored even if the link comes up. Exam tip: 'NVIDIA-branded' vs 'generic' cable identification is heavily tested. |
