
### Test_2_Results and Description of the work

### Tools Used
+ Matlab

### Results
+ <img width="730" height="730" alt="Screenshot 2026-01-07 221247" src="https://github.com/user-attachments/assets/c93df116-3e67-4d92-8145-451ab19289fc" />
+ <img width="730" height="730" alt="Screenshot 2026-01-07 221340" src="https://github.com/user-attachments/assets/dd6e4ee6-428f-46c4-bd59-08fe06a07ab6" />

### Description of the work
+ Massively Higher Ray Resolution: Previous version used ~100 rays per heater. This version fires 10,000 rays per heater, giving a much denser, smoother, and more accurate radiation map.
+ True Multi-Bounce Reflection Modeling: Earlier code allowed limited or simplified reflections. This model supports up to 5 wall reflections, capturing realistic indirect heating and chamber optical behavior.
+ High-Fidelity Ray Hit Mapping: Instead of only visualizing rays, this code counts and records every ray impact on the powder bed, producing a quantitative hit-density distribution.
+ Improved Chamber & Heater Geometry: Heaters are fully represented with correct 3D positioning, ceramic coating orientation, and real chamber boundaries-giving a more accurate ray emission baseline.
+ Better Visualization Quality: Rays are plotted with transparent intensity-based coloring, making it clear where direct beams dominate and where reflected rays contribute.

