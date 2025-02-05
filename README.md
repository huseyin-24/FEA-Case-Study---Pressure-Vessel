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
  <img src="https://github.com/user-attachments/assets/9bd2662c-2523-4eab-b6ca-8dc1c62b99ab" width="800" /></p>
<p align="center">Assigned Mesh</p>

### Boundary Conditions - Thermal
<img src="https://github.com/user-attachments/assets/341c2a34-0b8e-4f32-8024-d44fe61a285c" align="right" width="350"/>

- Temperature and convection boundary conditions are  
applied given in the figures.
- Thermal loads are applied at the second step just
after bolts are loaded.
<br clear="left"/>  
<br />
<br />
<br />
<br />
<p align="left"> 
  <img src="https://github.com/user-attachments/assets/b01a08fa-2a7a-45cb-901f-ab8669642cd7" width="400" /></p>
<p align="left">Step Details for Thermal Boundary Conditions</p>
 
### Boundary Conditions - Mechanical
<img src="https://github.com/user-attachments/assets/95323105-0a9d-4329-acac-28ecf5d69b8c" align="right" width="350"/>

- Bolt pre-load is applied in the first step and then locked for second and third steps.
- Inner side of the vessel is pressurized in the third step. 
- Also frictionless supports at the faces from which symmetry regions are defined are valid for all steps.

<br clear="left"/>  

<p align="left"> 
  <img src="https://github.com/user-attachments/assets/555a7bb1-02fa-4af8-8a51-a935d85fcb72" width="400" /></p>
<p align="left">Step Details for Mechanical Boundary Conditions</p>

### Contacts
<img src="https://github.com/user-attachments/assets/6a463f37-47dd-4e81-ae81-b9c66ab73148" align="right" width="320"/>

- Frictional contact is defined on the following regions: 
   - Bolt shanks and holes on the cover 
   - Bolt heads and outer surface of cover
- Since the bolt material is stiffer than body and cover material, bolts are to be determined as target bodies in corresponding contacts.
- Bonded contacts represent the interaction in thereaded regions. 
- Frictional contact is applied to region between cover and body. 
- Friction coefficient of 0.2 is used for all frictional contacts

<br clear="left"/> 

### Solution Methods and Options
<img src="https://github.com/user-attachments/assets/a7efb7c6-e184-4989-8dd7-9881d453eca1" align="right" width="220"/>

- Large deflection is activated. All other details of the solver are held at their default options.  
- Three step analysis is conducted such that;  
  - First step --> Bolt preload  
  - Second step --> Thermal loads  
  - Third step --> Pressure  

<br clear="left"/>  
<br />
<br />
<br />

### Results and Discussion
<img src="" align="right" width="250"/>

- Large deflection is activated. All other details of the solver are held at their default options.  
- Three step analysis is conducted such that;  
  - First step --> Bolt preload  
  - Second step --> Thermal loads  
  - Third step --> Pressure  

<br clear="left"/>

### Analytic Stress Calculation of Bolts
<img src="" align="right" width="250"/>

- Large deflection is activated. All other details of the solver are held at their default options.  
- Three step analysis is conducted such that;  
  - First step --> Bolt preload  
  - Second step --> Thermal loads  
  - Third step --> Pressure  

<br clear="left"/> 




