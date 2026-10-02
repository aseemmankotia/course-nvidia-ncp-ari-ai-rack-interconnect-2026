## Chapter 2: Cooling and GB200 NVL72 Rack Anatomy — Flashcards

| # | Front (Question) | Back (Answer) |
|---|-----------------|---------------|
| 1 | What does a CDU (Coolant Distribution Unit) do in a liquid-cooled AI rack? | Isolates and exchanges heat between the facility water loop (FWS) and the rack's internal technology cooling loop (TCS), managing flow rate, pressure, and coolant quality. Exam tip: CDU = interface point, not the cold plate itself. |
| 2 | GB200 NVL72 approximate total rack power draw? | ~120kW per rack. Exam tip: this is why air-only cooling cannot support it — liquid cooling via CDU is mandatory. |
| 3 | How many GPUs and Grace CPUs are in one GB200 NVL72 rack? | 72 Blackwell GPUs, 36 Grace CPUs. Exam tip: 18 compute trays × (4 GPUs + 2 Grace CPUs) per 'Bianca' board. |
| 4 | How many NVLink Switch trays are in a GB200 NVL72 rack? | 9 NVLink Switch trays. Exam tip: don't confuse with 18 compute trays — a frequent exam trap. |
| 5 | NVLink 5th generation per-GPU bandwidth in GB200 NVL72? | 1.8 TB/s bidirectional per GPU. Exam tip: this is roughly double NVLink 4 (Hopper) bandwidth of 900GB/s. |
| 6 | Hot-aisle containment vs cold-aisle containment: which is preferred for high-density racks like GB200 NVL72? | Hot-aisle containment — ducts hot exhaust directly back to CRAH, keeps rest of room cold-aisle temperature. Exam tip: cold-aisle containment leaves hot exhaust free in room, worse for mixed high/low density environments. |
| 7 | NVLink vs InfiniBand vs Ethernet — role in a GB200 NVL72 cluster? | NVLink = intra-rack GPU-to-GPU (highest bandwidth). InfiniBand (e.g., Quantum-2 NDR, 400Gb/s/port) or Ethernet (e.g., Spectrum-X) = scale-out between racks/nodes. Exam tip: NVLink never leaves the rack domain in NVL72. |
| 8 | What are the four main structural layers of a GB200 NVL72 rack? | Compute trays (GPU+CPU boards), NVSwitch trays (NVLink fabric), power shelves (DC power delivery), and cooling manifolds (liquid distribution to cold plates). Exam tip: know each layer's function, not just its name. |
| 9 | What cools the compute trays inside a GB200 NVL72 rack? | Direct-to-chip liquid cooling via cold plates connected to the rack's cooling manifolds, fed by the CDU-managed technology cooling loop. Exam tip: liquid handles GPU/CPU heat; some peripheral components may still need facility air handling. |
| 10 | InfiniBand NDR link speed commonly referenced for GPU cluster scale-out? | 400Gb/s per port (Quantum-2 NDR generation). Exam tip: used for inter-rack/inter-node scale-out, not intra-rack GPU fabric. |
| 11 | Why can't legacy CRAH-only cooling support a GB200 NVL72 rack? | CRAH/air cooling is typically limited to ~20kW per rack footprint, far below the GB200 NVL72's ~120kW draw. Exam tip: this gap is the core justification for CDU + liquid cooling adoption. |
| 12 | What is the aggregate NVLink domain bandwidth across all 72 GPUs in one NVL72 rack? | 130 TB/s aggregate bandwidth across the NVLink domain. Exam tip: this figure represents the full non-blocking fabric, not per-GPU bandwidth (1.8TB/s). |
