# FEA-Case-Study---Pressure-Vessel
According to case definition, thermocoupled structural analysis is supposed to run.
## Case Definition
The pressure vessel geometry, boundary conditions and material properities are given as follows:
<p align="center">
  <img src="https://github.com/user-attachments/assets/22f9c7b3-0fbe-4a72-9325-2690b31e0dce" width="392" />
  <img src="https://github.com/user-attachments/assets/be4897b1-864d-4ec8-8d70-9b595f20ab51" width="402" /></p>
<p align="center">Material Properities and Geometry</p>


<p align="center">
  <img src="https://github.com/user-attachments/assets/a55f1c7a-000a-441a-b073-f7f6fd10943f" width="402" /></p>
<p align="center">Boundary Conditions</p>

## Analysis

### Problem Description
- The pressure vessel given in the image is analyzed under the thermal and mechanical loads.
- Material for the body and cover is AISI 4340 annealed low alloy steel with the given material properties, and bolts are M10x50 class 12.9. Bolts are tightened to yield in the assembly.
- The amount of preload is calculated as 63 kN based on the yield strength of class 12.9 bolts (1100 MPa from internet sources) and the nominal stress area of the bolt (58 mm² from bolt tables).
- A pressure of 50 bars is applied from the inner side of the vessel as a mechanical load.
- A temperature of 200°C is the boundary temperature inside the vessel, and there is convection at the outer surface as thermal loads.
- Material properties given in the problem statement are defined and assigned accordingly.

### Geometric Modifications
- Texts on the body and bolts are cleaned up.
- Threaded faces on bolts are splitted so that the bonded contact is applied only threaded part.
- Vessel is divided into 8 part symetrically because of mesh/node limitation and better accuracy desired.
- Tiny chamfers at the outer surface of contact surface of body and cover are cleaned up.

<p align="center">
  <img src="https://github.com/user-attachments/assets/1c097667-f732-4af8-a710-3fdd9d22e660" width="400" />
  <img src="https://github.com/user-attachments/assets/70b88926-8de1-4ced-bb9f-c7880e9e8dcf" width="225" /></p>
<p align="center">Geometric Modifications</p>

### Mesh
<img src="https://github.com/user-attachments/assets/00e362fa-fb4e-4c5a-8f61-48c557462e0c" align="right" width="200px"/>

- MultiZone mesh method is used for bolts to generate HEX mesh.
- Mesh refinement is applied to surfaces below:
    - Contact surface of cover with body 
    - Contact surface of body with cover
    - Contact surfaces of body (holes) with bolts
- Mesh size is iteratively reduced by Body Sizing so that the element/node  
limit is not exceeded.

<br clear="left"/>

<p align="center">
  <img src="https://github.com/user-attachments/assets/1c097667-f732-4af8-a710-3fdd9d22e660" width="400" />
  <img src="https://github.com/user-attachments/assets/70b88926-8de1-4ced-bb9f-c7880e9e8dcf" width="225" /></p>
<p align="center">Assigned Mesh</p>
