## Chapter 4: Preparing the Rack for High-Density Install — Flashcards

| # | Front (Question) | Back (Answer) |
|---|-----------------|---------------|
| 1 | Max weight of a fully configured GB200 NVL72 rack? | Up to ~1,360 kg (3,000 lb). Exam tip: always verify raised-floor/structural load rating before install — most standard tiles are rated well below this. |
| 2 | GB200 NVL72 rack footprint (W x D)? | 600mm x 1200mm — deeper than standard 600x1000/1070mm enterprise racks to fit CDU manifolds and busbars. Exam tip: standard rack depth is usually insufficient. |
| 3 | GB200 NVL72 compute composition? | 72 Blackwell GPUs + 36 Grace CPUs per rack, liquid-cooled via a Coolant Distribution Unit (CDU). Exam tip: one rack = one NVLink domain. |
| 4 | Minimum front-post-to-front-door clearance recommended for high-density liquid-cooled AI racks? | 1000mm (39.4 in) — needed for tray slide-out and CDU hose service access. Exam tip: legacy 600-700mm clearance is insufficient. |
| 5 | Minimum recommended cold-aisle/inter-row spacing for high-density AI rack rows? | 1200mm (48 in) minimum for service access and containment doors. Exam gotcha: don't confuse with hot aisle, which is typically narrower (~900mm). |
| 6 | Minimum parallel separation between power cabling and copper data cabling per TIA-569-C? | 150mm (6 in); cross at 90° when unavoidable. Exam tip: fiber optic cabling is EMI-immune, so this rule specifically targets copper. |
| 7 | TIA-568 fiber cable minimum bend radius rule? | 10x cable OD when unloaded/no tension, 15x OD when under load. Exam tip: violating this causes attenuation/signal loss, not necessarily immediate breakage. |
| 8 | NEC 110.26 minimum working clearance in front of electrical equipment (0-150V, condition 2)? | 3 feet (36 in / 914mm). Exam tip: this is a life-safety code minimum, separate from vendor-specified service clearance recommendations. |
| 9 | Standard pattern for separating power and data cable pathways in a rack row? | Route power in bottom trays/busbars, data/fiber in top trays or dedicated vertical managers on the opposite side. Exam tip: physical separation is the primary EMI mitigation technique. |
| 10 | Why do GB200 NVL72 racks need a wider/deeper footprint than legacy 42U enterprise racks? | Liquid-cooling CDU manifolds, high-current busbars, and dense NVLink cable harnesses all require extra depth/width beyond standard 600x1000mm racks. |
| 11 | Best-practice interval for installing horizontal cable managers in dense AI racks? | Every 4-6U between equipment groups. Exam tip: too few managers causes cable congestion that blocks airflow and rear-door heat exchanger access. |
| 12 | Recommended rear-post-to-rear-door clearance for high-density AI racks with liquid cooling hoses? | ≥1000mm — needed for CDU hose routing, rear-door heat exchanger service, and hot-aisle containment airflow. Exam tip: often overlooked in favor of front clearance. |
