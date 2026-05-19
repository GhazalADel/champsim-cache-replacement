# ChampSim Cache Replacement Policy

**Course**: Principles of Computer Design — Spring 2023  
**University**: Amirkabir University of Technology  

## Overview

Exploring cache behavior using the [ChampSim](https://github.com/ChampSim/ChampSim) cycle-accurate cache simulator. Implemented and benchmarked custom cache replacement policies, comparing them against the built-in LRU policy.

## Phases

**Phase 1 — Setup & Analysis**  
Cloned and compiled ChampSim, ran simulations with default LRU configuration using DPC-3 benchmark traces, and analyzed cache hit/miss rates.

**Phase 2 — Custom Replacement Policy**  
Implemented MRU (Most Recently Used) replacement policy in `replacement/mru/mru.cc`, configured it for L2C, and compared performance against LRU.

**Phase 3 (Bonus) — Advanced Policy**  
Designed an original replacement policy aimed at outperforming LRU based on cache access pattern analysis.

## Modified Files

```
modified/
├── champsim_config.json   # Updated to use custom replacement policy
├── config.sh              # Build configuration script
└── mru/
    └── mru.cc             # MRU replacement policy implementation
```

## Running

```bash
# Clone & build
git clone https://github.com/ChampSim/ChampSim.git
cd ChampSim
./config.sh champsim_config.json
make

# Run simulation
bin/champsim --warmup_instructions 200000000 \
             --simulation_instructions 500000000 \
             ~/traces/600.perlbench_s-210B.champsimtrace.xz
```

Traces: [DPC-3](https://dpc3.compas.cs.stonybrook.edu/champsim-traces/speccpu/) · [CRC-2](http://bit.ly/2t2nkUj)
