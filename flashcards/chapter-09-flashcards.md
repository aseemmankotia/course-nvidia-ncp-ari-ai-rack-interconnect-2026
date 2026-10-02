## Chapter 9: Continuity and Link Testing — Flashcards

| # | Front (Question) | Back (Answer) |
|---|-----------------|---------------|
| 1 | Command to check InfiniBand port physical/logical link state on a Mellanox/NVIDIA HCA? | ibstat. Exam tip: reports states like LinkUp/Active vs LinkDown/Polling — differs from ethtool which is Ethernet-only. |
| 2 | Command to read module EEPROM (vendor, PN, serial) on a Linux Ethernet NIC? | ethtool -m <interface>. Exam tip: used to confirm cable/transceiver vendor identity for NVIDIA vs non-NVIDIA differentiation. |
| 3 | Which tool shows cable vendor info, temperature, and link diagnostics on Mellanox/NVIDIA adapters? | mlxlink -d <device> -m. Exam tip: the Vendor Name/Part Number field is the authoritative source for NVIDIA-certified cable verification. |
| 4 | Continuity test result: 'open' on a conductor — what does it mean? | No electrical path exists on that pin/conductor — indicates a broken wire or bad termination. Cable must be replaced. |
| 5 | Continuity test result: 'short' between two conductors — what does it mean? | Two conductors are unintentionally connected. Fault requires re-termination or replacement; the cable cannot pass signal correctly. |
| 6 | TIA-568.3-D max insertion loss per mated fiber connector pair? | ≤0.75 dB per connector pair. Exam tip: use this to calculate the expected total link loss budget before testing. |
| 7 | Typical OM3/OM4 multimode fiber attenuation at 850nm? | ≤3.5 dB/km. Exam tip: use with connector loss and splice loss to compute the total acceptable loss budget for an OPM test. |
| 8 | Typical singlemode (OS2) fiber attenuation at 1310/1550nm? | ≤0.4 dB/km. Exam tip: singlemode has much lower attenuation than multimode — relevant when calculating long-haul link budgets. |
| 9 | Pre-test vs post-install test — what's the difference in purpose? | Pre-test: verify raw cable/reel integrity before install (catch manufacturing defects). Post-install: verify the fully terminated end-to-end link (catch connector/routing issues). Both are required, in that order. |
| 10 | Optical power meter test fails above calculated loss budget — correct first troubleshooting step? | Inspect and clean connectors, re-terminate if dirty/damaged, then re-test. Do NOT immediately swap hardware or mark as pass. |
| 11 | What fields MUST appear in a test verification log for audit traceability? | Cable ID, endpoint locations, measured value (not just pass/fail), test equipment used, technician name, timestamp. |
| 12 | Link states: Link Down vs Disabled vs Polling — key distinction? | Link Down = no physical connection established. Disabled = administratively shut down by config. Polling = actively negotiating, not yet resolved. Exam trap: these are distinct states, not interchangeable. |
