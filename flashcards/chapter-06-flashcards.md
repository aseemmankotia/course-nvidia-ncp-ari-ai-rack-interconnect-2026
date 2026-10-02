## Chapter 6: Fiber Installation and Transceiver Handling — Flashcards

| # | Front (Question) | Back (Answer) |
|---|-----------------|---------------|
| 1 | APC connector polish angle and color code? | 8-degree angle, green connector body. Used for single-mode, low back reflection (~-60 dB). Exam tip: never mate APC to UPC. |
| 2 | UPC connector polish and typical back reflection? | Flat (ultra) polish, blue connector body, back reflection ~-50 to -55 dB. Used for multimode and some single-mode links. |
| 3 | APC vs UPC — can they be mated together? | No. Angle mismatch damages both ferrule endfaces. Always match polish type end-to-end and verify by connector color (green=APC, blue=UPC). |
| 4 | 100GBASE-SR4 reach and fiber type? | Up to ~70-100 m over OM4 multimode fiber using MPO/MTP connector. |
| 5 | 100GBASE-LR4 reach and fiber type? | Up to 10 km over single-mode fiber (SMF), duplex LC connector, WDM on single fiber pair. |
| 6 | 100GBASE-ER4 reach? | Up to 40 km over single-mode fiber. Requires higher TX power; may need an optical amplifier for extended budgets. |
| 7 | MPO Polarity Method A vs Method B | Method A: key-up to key-down connectors, straight fiber mapping. Method B: key-up to key-up on both ends, fiber positions reversed internally. |
| 8 | Correct fiber-optic connector cleaning sequence | 1) Dry-clean with click-type/cassette cleaner. 2) Inspect endface with fiber scope. 3) Wet-clean with isopropyl wipes only if contamination remains. Never mate an unverified connector. |
| 9 | How to verify transceiver seating after insertion? | Confirm audible/tactile latch click, then check link/activity LED or CLI 'show interface transceiver' status — do not rely on latch feel alone. |
| 10 | Transceiver storage best practice when not in use | Install dust cap on optical port immediately; store in ESD-safe bag to prevent both contamination and static damage. |
| 11 | What causes most 'no-link after correct seating' faults? | Contaminated or damaged fiber endfaces — always clean and scope-inspect before further hardware troubleshooting. |
| 12 | SMF transceiver selection rule of thumb by distance | ≤100m/OM4: SR4 (multimode). ≤2-10km: CWDM4/LR4 (SMF). ≤40km: ER4 (SMF). Exam tests picking the LOWEST-cost transceiver that still meets the required distance. |
