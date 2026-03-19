# Enclosure Design

This folder contains the STL files for a custom-designed enclosure used to protect onboard computing and electronic components of an off-road autonomous vehicle platform.

The enclosure is designed to operate in challenging outdoor environments, where dust, moisture, vibration, and thermal buildup can affect system reliability. Key components such as the NVIDIA Jetson AGX, power distribution board, and supporting electronics are housed within this enclosure to ensure stable operation.

A system-level protection strategy was adopted, enclosing multiple components within a single unified structure. The design incorporates overlapping interfaces and a C-channel interlocking mechanism to reduce water ingress and improve sealing. Drainage channels are also included to allow any water entering the enclosure to exit efficiently.

To address thermal constraints, the enclosure integrates ventilation features and supports active cooling via a fan, ensuring adequate airflow for heat-generating components. The structure is also designed to withstand vibrations encountered during off-road driving.

The enclosure is 3D printed using ASA filament, chosen for its UV resistance, thermal stability, and mechanical strength compared to materials such as PLA and PETG. This makes it suitable for long-term outdoor deployment.

## Files

- `Back.stl` – rear enclosure panel  
- `Side Wall.stl` – side structural walls  
- `Font and Middle.stl` – front and central structural section  
- `Fron Lid.stl` – front lid/cover  
- `Top Lid Part 1.stl` – top enclosure (part 1)  
- `Top Lid Part 2.stl` – top enclosure (part 2)  

## 3D Printing Guidelines

- Material: ASA (recommended)  
- Layer height: 0.2 mm  
- Supports: Required for overhangs  
- Orientation: Print major flat surfaces on the build plate  
