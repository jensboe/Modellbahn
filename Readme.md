# System architecture
The `adapter board A` is connected to a nucleo 64 board.
The `adapter board A` provides a 
```mermaid
block-beta

columns 1
block:selfmade
    block:base
        columns 1
        nucleo
        adapter["adapter board A"]
    end
    space
    expansion_1["expansion board A 1"]
    space
    expansion_n["expansion board A n"]
    space
    expansion_b["expansion board B"]
    adapter     <--> expansion_1
    expansion_1   ----> expansion_n
    expansion_n  ----> expansion_b
    style expansion_b stroke:#333,stroke-dasharray: 5 5;
end
space
block:extern
    power_supply
    track_1
    switch_1_a
    switch_1_b
    track_x
    switch_y_a
    switch_y_b
end
power_supply --> adapter
expansion_1 --> track_1
expansion_1 --> switch_1_a
expansion_1 --> switch_1_b

expansion_n --> track_x
expansion_n --> switch_y_a
expansion_n --> switch_y_b
```
## Connection between expansion boards
Required Wires:
1. Drive Ground
2. Drive voltage
3. Switch voltage
4. Vcc (3V3 or 5V?)
5. D_Ground
6. MOSI
7. MISO
8. CLK