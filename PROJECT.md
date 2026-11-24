# INDEX:

## 1. Team Organization
### 1.1. Role Assignments
### 1.2. Group Regulations
## 2. Axial Fan Introduction: Noctua NF-A12x25 PWM
## 3. Technical Specifications
### 3.1. Dimensions
### 3.2. Performance
### 3.3. Estimated Power Consumption
## 4. Applications and Examples from the web
### 4.1. Main Applications 
### 4.2. Examples from the web
## 5. CFD planning
## 6. Experimentation
### 6.1. Relevant variables of the axial fan
### 6.2. Proposed instrumentation for measuring and data acquisition
### 6.3. ISO 5801:2019 application to the axial fan
---

## 1. Team Organization
To ensure efficient and effective work, the project has been structured into three distinct categories to be covered by group members, in accordance with the project guidelines. Certain rules and regulations have also been established to help maintain an equitable and professional work pace.

### 1.1. Role Assignments
- **Martí Buil (Team Leader & Design Expert):** Responsible for group coordination, delivery deadlines, and project quality. As a Design Expert, Martí will also be responsible for CAD modeling and the physical design of the axial fan.
- **Pol Sabaté (Test & Experimentation Expert):** Responsible for the experimental phase of the project, in charge of measuring the axial fan's actual performance and collecting data to help validate CFD simulations and theoretical calculations.
- **Pau Pujol (CFD Expert):** Responsible for Computational Fluid Dynamics (CFD) analysis. Pau’s role involves airflow simulation, pressure distribution analysis, and aerodynamic efficiency evaluations of the axial fan.

### 1.2. Group Regulations
To maintain a productive work environment and effective collaboration, the following set of regulations and guidelines has been established; all group members must adhere to them throughout the project.

1. **Communication & Meetings:** The team must maintain active communication channels at all times, ensuring the ability to exchange information continuously and assist other group members with any questions.
2. **File Management & Version Control:** All newly created files must be shared and validated by all three group members. Established folder structures must be respected, and appropriate file naming conventions used to ensure clarity.
3. **Internal Deadlines:** To ensure the quality of deliverables, work must be completed 24 hours prior to the official deadline. This ensures not only timely submission but also allows for additional time to discuss the technical aspects of the work performed.
4. **Decision Making & Conflict Resolution:** Decisions regarding technical and design concepts must be subject to group review. In the event of a disagreement on a specific issue, proposals will be put to a group vote. If no resolution is reached, the Group Leader will make the final decision to ensure progress continues.
5. **Workload Equity:** All group members must contribute equitably and offer assistance if a designated expert lacks sufficient time. The goal is not merely to complete individual tasks, but to finish the project and deliver work that meets expectations.

## 2. Axial Fan Introduction: Noctua NF-A12x25 PWM
The axial fan selected for this project is the Noctua NF-A12x25 PWM, a cooling component primarily used for CPUs and other computer hardware. Noctua is one of the most renowned brands in the sector, and this model represents one of the company's most efficient and modern offerings. Constructed using innovative materials such as Sterrox (a liquid-crystal polymer), this model delivers high performance, overcoming some of the limitations associated with earlier axial fans in the industry. The Noctua NF-A12x25 PWM stands out for its excellent high static pressure capabilities and exceptional airflow, while simultaneously significantly reducing noise output, making it an ideal product for industrial and high-performance applications.

## 3. Technical Specifications

### 3.1. Dimensions
- **Width x Height x Depth:** 120 x 120 x 25 mm
- **Diameter:** 114 mm
- **Hub Diameter:** 50 mm  
- **Mounting hole spacing:** 105 x 105 mm

### 3.2. Performance
- **Maximum rotational speed:** 2000 rpm
- **Maximum airflow:** 102,1 m3/h
- **Maximum static pressure:** 2,34 mm H2O
- **Maximum noise level:** 22,6 dB(A)
- **Bearing type:** SSO2 (Self-stabilizing oil-pressure bearing)
- **Impeller material:** Sterrox LCP (Liquid-Crystal Polymer)

### 3.3. Estimated Power Consumption
- **Typical Voltage:** 12 V
- **Estimated Power Consumption:** 1,2 W (up to a maximum of 1,68 W at full load)
- **Connector:** 4-pin PWM

## 4. Applications and Examples from the web

### 4.1. Main Applications 
Thanks to its optimized P/Q (pressure/airflow) curve in the mid-range, this axial fan is ideally suited for the applications described below: 

- **Liquid cooling radiators (AIO systems or custom loops):** given its high operating static pressure, the Noctua axial fan can effectively force air through dense radiator fins without sacrificing airflow. 
- **Air-cooled CPU heatsinks:** this model is ideal for "push" or "push-pull" configurations, offering lower noise levels compared to other models on the market. 
- **Chassis ventilation (case cooling):** this fan delivers excellent performance as an intake fan, as its airflow is capable of overcoming the high airflow resistance created by dust filters or mesh front panels.

### 4.2. Examples from the web
Below, three exampels of real-world applications documented online are presented to show how efficient this axial fan is:

- **Use with restrictive radiators (for instance, Arctic Liquid Freezer II 240):** Various hardware reviews demonstrate the use of the NF-A12x25 alongside the included NA-AVG1 silicone anti-vibration gasket. This gasket seals the gap between the fan frame and the radiator, channeling all static pressure through the fins without side leakage.
- **Use as a case fan behind filters (for instance, DeepCool CH510 Mesh):** Acoustic tests prove its effectiveness as a primary intake fan. Thanks to its aerodynamic design, it maintains consistent airflow into the system while keeping noise levels very low (around 31 dB(A) at 1100 RPM).
- **Replacement on tower-style heatsinks (for instance, Noctua NH-U12A / DeepCool AK400).** It is frequently documented as a replacement for standard fans, leveraging the minimal 0.5 mm clearance between the blade tips and the frame (made possible by the Sterrox material). This prevents turbulence and improves direct heat dissipation through the processor's aluminum fin stack.

## 5. CFD Planning
Three different types of simulations will be executed to aid and verify our design choices. These will be the following: 

### 5.1. Airfoil simulations:
CAD description:

The CAD will be the selected airfoil with it’s design characteristics. Including profile (NACA 65), chord measurements and design length.

Mesh description:

The mesh will be designed balancing two factors. On one side we aim to obtain the necessary accuracy and definition of results to verify and aid our design. On the other side we want to optimize computational cost so that we are more nimble in our iterative design process. This is why we will discretize different parts of our mesh.

Surrounding our airfoil and following it’s closest flow downstream we will create a region refinement. This zone will use level 4 refinement, and will allow us to understand how the flow behaves after interacting with the fan. 

It will also be necessary to refine the surface of the airfoil and the boundary layer around it. For the surface we will use level 5. For the boundary layer we will use a changing refinement, in SimScale this tool is called “Inflate Boundary Layer”, and will allow us to create refinement that decreases when getting further away from our airfoil. 

Boundary conditions:

The most important boundary condition of these simulations will be the free-stream velocity and it’s direction. The axial velocity in the fan is 1,537m/s. Due to the chosen angle of attack the components of our velocity boundary condition will be the following. 
Vx = 1,516 m/s
Vy = 0.2527 m/s
The velocity boundary condition will be applied in the surrounding walls of our domain. 
Because of the aims of this simulation we are able to apply symmetry boundary conditions in the front and back walls of the domain. This is an efficient way of reducing computational cost.
The airfoil itself will have a wall boundary condition (No-slip). We will use Wall-Functions to resolve the flow close to our surface. 



### 5.2. Cascade Simulations:

CAD description:

This second simulation will use the same CAD model as the first one. Our airfoil of choice with all it’s characteristics. In this case we will introduce the airfoil at the stagger angle (77.896°). 

Mesh description:

The mesh for this simulation will be similar to the mesh described before, but due to the direction of our flow we will modify the geometry of the region refinement. 

Boundary conditions:

Because we aim to understand the effects on the airflow of the cascade of airfoils we will have to set up periodic boundary conditions on the top and bottom of our domain. This way the influence on the state of the flow produced by one fin affects the next, therefore providing us with information on the full rotation of our fan. 

The velocity inlet boundary condition will be set up at a relative angle of (b1 (80,536°) - Stagger (77.896°) = 2.64°. Therefore:
Vx =0.070 m/s
Vy = 1.53536 m/s

Symmetrys will be applied in the front and back sections of our domain. The same way as in the previous types of simulations. 

In this case we will use the pressure outlet boundary condition in the most downstream section of our domain. 

### 5.3. Full model simulations:

CAD description:

The full model simulations will incorporate the CAD of the full fan. This includes casing, center fan structure and the designed 9 airfoils.

Mesh description:

Meshing will be developed with the same objectives in mind, but due to the complexity of this simulations it will also require an iterative process to understand the shortcomings of our initial meshes. 

Boundary conditions:

A velocity inlet will be defined with the mentioned axial velocity. Our idea is to iterate with this velocity to find our ideal performance points. A pressure outlet will also be defined. No-slip conditions will be applied on our airfoils and fan structures, therefore setting them up as walls. The rotating speed of the reference frame will also be applied, therefore simulation the movement in our fan.


Each of these types of simulations will be performed through an iterative process. We will do our first runs using the designed parameters and will subsequently iterate until reaching the desired performance outcomes. We will also perform Grid Convergence Studies to determine if our results are converged. 

## 6. Experimentation
To test the design of the fan and validate the CFD results we must design the experimental procedure to evaluate our axial fan and see if it is in compliance with the UNE-EN ISO 5801:2019. For these release we do not need to construct the whole test-bench, we need to define the following points: 

### 6.1. Relevant variables of the axial fan
The selection of the material and the devices have a direct relation between the following varaibles:
<img width="517" height="255" alt="image" src="https://github.com/user-attachments/assets/4b427761-38ab-442a-b4a4-2295a720d0fd" />
With these reference variables we can select the quantities to be measured with our measurement devices.
<img width="671" height="558" alt="image" src="https://github.com/user-attachments/assets/e607d8df-877a-471a-994d-a708ac96dfe3" />


### 6.2. Proposed instrumentation for measuring and data acquisition

### 6.3. ISO 5801:2019 application to the axial fan

<img width="677" height="450" alt="image" src="https://github.com/user-attachments/assets/c88665eb-651f-4430-bcef-309e3c462940" />



