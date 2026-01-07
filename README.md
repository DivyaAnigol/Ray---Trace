# Ray---Trace
This work marks the transition of my ray-tracing study from ANSYS to MATLAB, using a fully custom heater-configuration model built from scratch. By recreating the geometry and control logic in MATLAB, the project now offers faster iteration, deeper customization, and a more flexible platform for analysing IR heater behaviour.

## Technical Content
**AIM:** To simulate IR radiation transport in an SLS chamber using geometric and Monte-Carlo ray tracing, capturing direct and reflected energy paths. The model converts ray-hit distributions into heat-flux and temperature fields to evaluate thermal uniformity and optimize heater performance.


**TOOL USED:** MATLAB


**CODE & LOGIC:**

**1. Material Properties (PA12 & Stainless Steel):** 
```
%% Material Properties
PA12 = struct('reflectivity', 0.05, 'emissivity', 0.46);
SS   = struct('reflectivity', 0.85, 'emissivity', 0.15);
```
**Physics relevance:**

Controls optical behavior upon ray interaction:
1. PA12 powder is mostly absorbing → converts radiation into heat
2. Stainless steel is highly reflective → drives multi-bounce behavior.
   
These parameters dictate how energy is redistributed in the chamber.


**2. Heater Geometry (Line/Cylinder Definition):**
```
heater_lines = [
    x1 y1 z1  x2 y2 z2;
    ...
];
```
**Physical Relevance:**

Represents IR heaters as finite-length line emitters, approximating real quartz tube IR lamps.

These heater geometries govern: emission origin, radiation direction, spatial heating uniformity.

Defines where and how radiation enters the system.


**3. Directional Emission Using Emission Cone:**
```
theta = deg2rad(emission_angle) * rand();
phi   = 2*pi*rand();
dir = [sin(theta)*cos(phi), sin(theta)*sin(phi), -cos(theta)];
```
**Physical Relevance:**

Models realistic infrared emission, where heaters radiate strongest perpendicular to their surface.

The emission cone captures: angular distribution of IR intensity, beam spreading, directional heating effects, 

This is crucial for accurate radiation mapping.


**4. Ray–Wall Reflection Physics:**
```
curr_dir = curr_dir - 2 * dot(curr_dir, wall.normal) * wall.normal;
```
**Physical Relevance:**

Implements specular reflection, the correct optical law for polished stainless steel.

Controls: secondary/tertiary radiation, indirect heating, spatial smoothing of energy

Reflections are a dominant factor in chamber thermal uniformity.


**5. Bed Intersection Calculation:**
```
t_bed = -curr_origin(3) / curr_dir(3);
hit_bed = curr_origin + t_bed * curr_dir;
```
**Physical Relevance:**

Determines where radiation actually lands on the powder bed surface.

This gives: energy deposition location, heat flux patterns, temperature rise predictions

