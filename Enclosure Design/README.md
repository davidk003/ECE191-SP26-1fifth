# Enclosure Design

This folder contains the STL files for a custom-designed enclosure used to protect onboard computing and electronic components of an off-road autonomous vehicle platform.

The enclosure is designed to operate in challenging outdoor environments, where dust, moisture, vibration, and thermal buildup can affect system reliability. Key components such as the NVIDIA Jetson AGX, power distribution board, and supporting electronics are housed within this enclosure to ensure stable operation.

A system-level protection strategy was adopted, enclosing multiple components within a single unified structure. The design incorporates overlapping interfaces and a C-channel interlocking mechanism to reduce water ingress and improve sealing. Drainage channels are also included to allow any water entering the enclosure to exit efficiently.

To address thermal constraints, the enclosure integrates ventilation features and supports active cooling via a fan, ensuring adequate airflow for heat-generating components. The structure is also designed to withstand vibrations encountered during off-road driving.

The enclosure is 3D printed using ASA filament, chosen for its UV resistance, thermal stability, and mechanical strength compared to materials such as PLA and PETG. This makes it suitable for long-term outdoor deployment.

## Files

- `Back.stl` – rear enclosure panel  
- `Side Wall.stl` – side structural walls  
- `Front and Middle.stl` – front and central structural section  
- `Front Lid.stl` – front lid/cover  
- `Top Lid Part 1.stl` – top enclosure (part 1)  
- `Top Lid Part 2.stl` – top enclosure (part 2)  

## 3D Printing Guidelines

- Material: ASA (recommended)  
- Layer height: 0.2 mm  
- Supports: Required for overhangs  
- Orientation: Print major flat surfaces on the build plate

## Assembly Process

The enclosure is assembled from back to front. First, the rear section is mounted onto the vehicle chassis using a C-channel structure, providing stable alignment and secure attachment to the base plate. The remaining components are then installed sequentially toward the front. The front lid is attached next to close the front opening, ensuring proper alignment of the enclosure. Finally, the top lid, which is pre-assembled as a single piece, is slid into place along the guiding rails to complete the enclosure. This assembly process ensures a straightforward installation while maintaining structural stability.
<img width="1536" height="1152" alt="image" src="https://github.com/user-attachments/assets/39427b81-6b9b-4cdf-ad4e-8a91d0d9ecb4" />


## Future Work

- Top Lid Assembly
  - Combine the two top lid parts using threaded inserts for secure fastening.
  - <img width="1152" height="1536" alt="image" src="https://github.com/user-attachments/assets/07da91bb-b15b-43dd-9498-d9d328ba7c75" />


- Weather Robustness Testing
  - Conduct testing under outdoor conditions to evaluate water and dust resistance, and validate the effectiveness of sealing features such as overlapping interfaces and drainage channels.
