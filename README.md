
### Test_1_Results and Description of the work

### Tools Used
+ Matlab

### Results
<img width="730" height="730" alt="Screenshot 2026-01-07 205945" src="https://github.com/user-attachments/assets/5a50da53-16b3-4df5-8e48-8a214f940345" />
<img width="730" height="730" alt="Screenshot 2026-01-07 210005" src="https://github.com/user-attachments/assets/e150a654-c02d-472b-9a04-52bab8dde841" />
<img width="730" height="730" alt="Screenshot 2026-01-07 210030" src="https://github.com/user-attachments/assets/e0594065-fa8e-48e2-9683-c0580736b035" />
<img width="730" height="730" alt="Screenshot 2026-01-07 210101" src="https://github.com/user-attachments/assets/66219459-cd71-4003-ad95-43da15cf23da" />

### Description of the work
+ Introduced full 3D Ray Tracing Physics
Unlike the previous model (which relied only on view-factor + cosine law), this version generates actual rays from IR heaters with directional emission cones, creating a physically intuitive and visually accurate radiation model.
+ Added Multi-Bounce Wall Reflections
Rays now reflect from chamber walls (up to 3 bounces), capturing secondary radiation paths, improving realism of heat transport inside the chamber.
+ Modeled Heaters as True 3D Cylinders With Emission
Instead of treating heaters as line sources, this code constructs 3D cylindric heater geometry and emits rays along their length, increasing geometric accuracy.
+ Enhanced Visual Interpretation. The new ray-plotting system clearly shows:
  1. direct rays
  2. reflected rays
  3. ray intensities based on angle

This makes the energy flow inside the chamber far more interpretable than the previous purely mathematical flux computation.
