## Chapter 1: AI Rack Power Fundamentals — Flashcards

| # | Front (Question) | Back (Answer) |
|---|-----------------|---------------|
| 1 | GB200 NVL72 rack power draw class? | ~120kW per rack. Exam tip: roughly 10x+ a traditional air-cooled rack (~10-15kW), driving DC busbar and liquid-cooling adoption. |
| 2 | 80% continuous-load derating rule | Continuous loads (>3 hrs) must not exceed 80% of rated breaker/circuit capacity. Example: 30A breaker → 24A max continuous load. |
| 3 | N+1 vs 2N vs 2N+1 — difference? | N+1 = one spare unit on a shared path. 2N = two fully independent full-capacity paths. 2N+1 = two independent paths, each with a spare unit. Exam tip: 2N survives a full path failure; N+1 does not. |
| 4 | Why does phase imbalance on an rPDU create risk even with rack headroom available? | One overloaded phase can trip its breaker independently while other phases still have spare capacity, causing an avoidable partial outage. |
| 5 | 3-phase 208V rPDU, 60A/phase — approximate kVA rating? | ~21.6 kVA (P = √3 x 208V x 60A). Exam tip: know the √3 formula for 3-phase capacity math. |
| 6 | Single-phase 208V 30A rPDU branch — rated and derated capacity? | Rated: 6.24kW (208V x 30A). Derated continuous (80% rule): 4.99kW. Always derate before capacity planning. |
| 7 | AC rack power architecture vs DC rack power architecture — key tradeoff? | AC distributes 208/400V to per-server PSUs (AC-DC conversion at each server). DC (e.g., -48VDC busbar) distributes DC directly, eliminating redundant conversion stages and improving efficiency in ultra-high-density AI racks. |
| 8 | What does 2N guarantee that N+1 does not? | 2N guarantees survival of a complete independent power path failure (e.g., an entire utility feed or PDU string); N+1 only tolerates a single component failure within one shared path. |
| 9 | Grounding verification step before energizing a high-density AI rack? | Verify a continuous, low-resistance bonding path between the rack frame and the facility grounding grid before applying power. A skipped grounding check is a classic exam 'what did the technician forget' scenario. |
| 10 | Rack draws 120kW; PDUs derate to 17.28kW usable each. PDUs needed per independent feed for 2N? | 120 ÷ 17.28 ≈ 6.94 → round UP to 7 PDUs per feed (x2 feeds = 14 total). Exam tip: always round capacity calculations up, never down. |
| 11 | Traditional air-cooled rack power draw vs GB200 NVL72 rack power draw? | Traditional: ~10-15kW/rack. GB200 NVL72: ~120kW class. This order-of-magnitude jump drives the shift to DC busbar power and liquid cooling. |
| 12 | Why does the exam emphasize 'intelligent' rPDUs specifically for phase balancing? | Intelligent (metered/switched) rPDUs provide per-phase current monitoring, letting operators detect and correct imbalance remotely before a breaker trips. 'Intelligent' = monitoring/remote capability, not just a passive PDU. |
