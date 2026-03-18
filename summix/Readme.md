# Summix

A simple, low-cost Eurorack 3-channel summing mixer with 4 inputs and 2 separately buffered outputs for each channel.

![Summix module](doc/summix.gif)

The mixer is fully **DC-coupled**, **Unit-Gain**, **Non-Inverting**. Nothing fancy. Just adding signals.

## Repository content

- doc/BOM.csv: Bill of materials

- summix-pcb/
    - summix-pcb.kicad_sch / summix-pcb.kicad_pcb: main circuit board
    - gerbers/: generated gerbers/drills for the main board

- summix-panel/
    - summix-panel.kicad_pcb: front panel PCB (text/art + mounting)
    - gerbers/: generated gerbers/drills for the panel

# How it works

## Block diagram

```mermaid
%%{init: {"themeVariables": {"fontSize": "12px"}, "flowchart": {"nodeSpacing": 25, "rankSpacing": 25}}}%%
flowchart LR

    IN1["Input 1"] --> SUM["Inverting summing amp"]
    IN2["Input 2"] --> SUM
    IN3["Input 3"] --> SUM
    IN3["Input 4"] --> SUM

    SUM --> INV["Inverter"]
    INV --> BUF1["Output buffer 1"] --> OUT1["Output 1"]
    INV --> BUF2["Output buffer 2"] --> OUT2["Output 2"]
```

## Schematic

The schematic of a single channel (there are 3 of them):

![Schematic](doc/schematic.png)

## License

Licensed under **CC BY-SA 4.0**.
