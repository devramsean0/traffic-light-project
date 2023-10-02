---
title: 'Designing the sequencer hardware'
description: 'The joys and challenges of designing the Hardware behind my Sequencer'
date: '02-10-2023'
---
# The basic design
- Should be based around the Pico W
- Should have built in methods for displaying basic information
- Use an external 240VAC -> 5VDC board (for safety and ease)
- Have 3 Control channels
- Expose UART pins for the wait sign

# General wiring Diagram
My general idea for how the sequencer works is like:
```
            Power in
               |
            Control Board
        /     ^             \
    Power Board            Relay
```
# The challenges
## 240v
Working out how to handle this was a challenge.
This included things like:
- Designing the PCB to handle it
- Safeguards for if something goes wrong.

I solved these issues by:
- using 3mm traces for anything that should take 240V
- having a ground plane on the PCB so the circuit will ground via the cable instead of the rest of the circuitry
- Putting a fuse inline before the 3 light channel outputs

## Size
The art of compacting a 4 layer PCB's is intense. I eventually ended up with a long but thin PCB
