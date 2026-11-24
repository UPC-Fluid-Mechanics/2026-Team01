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
## 7. Design of the axial fan
### 7.1 Specification and dimensionless parameters
#### 7.1.1 Reference fan and operating point
#### 7.1.2 Dimensionless parameters (D1)
### 7.2 Geometry description of all the parts of the axial fan
### 7.3 Materials and characteristics. Justification
### 7.4 Mean line analysis (D2)
#### 7.4.1 Velocity triangles
#### 7.4.2 Cascade geometry and diffusion factor
#### 7.4.3 Preliminary blade angles
#### 7.4.4 Sensitivity and limitations
### 7.5 Conclusions and next steps

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

<img width="517" height="255" alt="Screenshot 2026-11-24 231256" src="https://github.com/user-attachments/assets/9e46e2d2-ae13-40c1-ba58-3044317076a9" />

<img width="571" height="458" alt="Screenshot 2026-11-24 231434" src="https://github.com/user-attachments/assets/5ac8492c-7c1f-42aa-8a94-26781bfb776b" />


### 6.2. Proposed instrumentation for measuring and data acquisition
- Flow rate measurement
Airflow will be determined using a rounded-entry nozzle system installed in an inlet chamber. A multi-nozzle arrangement is proposed so that different active throat areas can be selected over the operating range.
This approach is consistent with the Category A inlet-chamber method introduced in E3. The nozzle profile, throat dimensions, installation and discharge-coefficient calculation must follow the applicable requirements of ISO 5801 Annex A. A generic bellmouth opening cannot be treated as a standardised measuring nozzle without this verification.
The final calculation will use the complete expression applicable to the selected geometry, including the relevant coefficients, corrections and validity limits. Nozzle number and dimensions will be established during detailed bench design.
To measure the airflow, the air passes through a nozzle, it accelerates and its static pressure decreases. The resulting pressure difference is related to the mass flow rate through the nozzle. Measuring this pressure difference, together with nozzle geometry and air density, allows the airflow to be calculated. ISO 5801 provides the applicable methods in Annex A.

- Pressure Measurement
Two independent differential-pressure channels are required:
-- Differential pressure across the nozzle system, used to calculate airflow.
-- Chamber pressure relative to ambient, used to determine fan pressure according to the selected configuration.
The WIKA CPC2000 is proposed as a candidate instrument for steady-state differential-pressure measurement, operating in measurement mode. It contains an internal pressure sensor, display and USB/RS-232 communication. Pressure is transmitted from the bench through pneumatic tubing; no additional pressure transmitter is required in series with the instrument. It will only be needed to connect to a computer so we can share the readings of the instrument.
For the fan-pressure channel, the 0–1 mbar configuration, equivalent to 0–100 Pa, is a candidate. Its specified accuracy is 0.3% of span, equivalent to 0.3 Pa. WIKA defines this specification with a coverage factor of k=2, subject to the conditions stated in its documentation. This is an instrument specification, not the uncertainty of the complete pressure-measurement chain.
One CPC2000 provides one differential-pressure measurement, not two independent simultaneous channels. So we would need two CPC2000 to capture the two independent differential-pressure channels.

For atmospheric pressure, ambient barometric pressure (pa) is measured using a Vaisala PTB110 electronic barometer, which employs a silicon capacitive absolute pressure sensor (BAROCAP). This instrument covers an absolute pressure range of 500 to 1100 hPa (50,000 to 110,000 Pa), fully encompassing expected laboratory atmospheric variations. According to the manufacturer's datasheet, it provides a total accuracy of ±0.3 hPa (±30 Pa) at 20 °C and ±0.6 hPa (±60 Pa) across the 0 to 40 °C temperature range, incorporating internal temperature compensation between -40 °C and +60 °C. For seamless data acquisition, the barometer provides a linear 0 to 5 V DC analog output signal wired directly into an analog input channel of the NI cDAQ system, enabling continuous automated logging of barometric pressure alongside temperature and humidity.
Air Temperature Measurement
Air temperature will be measured using a Type T thermocouple with an exposed welded junction. A specific candidate is the Pico Technology SE046, which has PTFE insulation and a 1 m cable. Its exposed junction is suitable for gas-temperature measurements. Has a ±0.2% accuracy of reading and ±0.5 °C.
In the proposed NI-based architecture, the thermocouple will be connected to an NI-9211 thermocouple input module, with suitable Type T connections and correct polarity. The NI-9211 provides cold-junction compensation and thermocouple measurement functions.

Relative humidity measurement
Relative humidity will be measured using a Vaisala HMP60 probe. The proposed configuration uses a 0–5 V analogue output connected to an NI-9205 voltage-input module.
For this output configuration, the probe requires an 8–28 V DC supply; a regulated 12 V supply is therefore suitable, provided that the wiring and electrical references are correctly implemented.
The manufacturer specifies a typical humidity accuracy of ±3 percentage points of relative humidity over 0–90% RH at 0–40 °C.

Rotational speed (n) and electrical power (Pel)
If the Noctua motor and electronics are used, rotational speed will be obtained from the tachometer output. The tachometer output and PWM control input are separate signals.
Noctua specifies an open-collector tachometer output with two pulses per revolution. A pull-up resistor to a voltage compatible with the acquisition input is therefore required. The tachometer wire must not be described as an independently generated 5 V square-wave output.
For two pulses per revolution:

where 𝑛 is in rpm and 𝑓 is in Hz.

The signal will be routed through an NI-9401 digital module to a counter in the cDAQ chassis. A fixed accuracy of ±2 rpm is not claimed at this stage. The achievable uncertainty depends on the counting method, timebase, observation interval and signal quality.
A Keysight E36312A bench power supply is proposed to power the fan. The nominal supply setting does not replace a measurement of the actual voltage at the fan terminals.
Current may be determined using a precision shunt resistor and a differential voltage measurement:

For the proposed 0.1 Ω shunt, a current of 0.10 A produces a voltage drop of 10 mV. The acquisition range and wiring must therefore be suitable for low-level voltage measurements.
The shunt tolerance alone does not determine current-measurement uncertainty. The voltage-input offset, gain error, noise, resistor temperature dependence and connections must also be considered.
The NI-9205 has a maximum selectable input range of ±10 V. Therefore, the nominal 12 V fan supply must not be measured directly on this range. A characterised voltage divider, a suitable higher-range input or a separate voltage-measuring instrument is required. Fan terminal voltage will be measured through a characterised voltage divider connected to an NI-9205 input. Current will be determined from the differential voltage across the shunt resistor. Divider ratio, resistor specifications, grounding and measurement uncertainty will be established during detailed design.

### 6.3. ISO 5801:2019 application to the axial fan

<img width="677" height="450" alt="image" src="https://github.com/user-attachments/assets/c88665eb-651f-4430-bcef-309e3c462940" />

# 7. Design of the axial fan

## 7.1 Specification and dimensionless parameters

### 7.1.1 Reference fan and operating point

The selected fan is a 120 mm axial fan for electronic cooling, with a nine-blade rotor and PWM speed control.

| Parameter | Value | Basis |
|---|---:|---|
| Maximum rotational speed | 2,000 rpm | Manufacturer |
| Maximum free-air flow | 102.1 m³/h | Manufacturer |
| Maximum static pressure | 2.34 mmH₂O | Manufacturer |
| Rated voltage | 12 V | Manufacturer |
| Typical / maximum electrical input | 1.20 / 1.68 W | Manufacturer |
| Maximum acoustic noise | 22.6 dB(A) | Manufacturer |
| Selected volume flow, $Q$ | 45.6 m³/h | Published P/Q curve |
| Selected static pressure rise, $\Delta p_s$ | 1.52 mmH₂O = 14.906 Pa | Published P/Q curve |
| Air density, $\rho$ | 1.20 kg/m³ | Assumed |
| Dynamic viscosity, $\mu$ | 1.81 × 10⁻⁵ Pa·s | Assumed |

The operating point is selected from matched pressure and flow data at approximately 2,000 rpm. It is not claimed to be the best-efficiency point. Maximum flow and maximum static pressure occur at different operating conditions.

| Flow (m³/h) | Static pressure (mmH₂O) |
|---:|---:|
| 0 | 2.34 |
| 18.7 | 1.92 |
| **45.6** | **1.52** |
| 76.5 | 0.87 |
| 102.1 | 0 |

For the initial lossless Euler calculation, the measured-type static pressure specification is used as a proxy for ideal total pressure rise, $\Delta p_{0,E}\approx\Delta p_s$. This is a modelling assumption, not a physical equivalence. The static fluid-output power is $Q\Delta p_s=0.1888$ W. Actual shaft efficiency cannot be determined from the rated electrical input alone.

### 7.1.2 Dimensionless parameters (D1)

The definitions follow the course notebooks, using the assumed rotor diameter in Section 2 and angular velocity $\Omega=2\pi N/60=209.440$ rad/s.

| Parameter | Definition | Result |
|---|---|---:|
| Flow coefficient | $\phi=Q/(\Omega D^3)$ | 0.04082 |
| Head coefficient (proxy) | $\psi=\Delta p_s/(\rho\Omega^2D^2)$ | 0.02179 |
| Fluid power coefficient (proxy) | $\hat P_h=\phi\psi$ | 0.00089 |
| Diameter Reynolds number | $Re_D=\rho c_x D/\mu$ | 11,613 |
| Specific speed (proxy) | $\Omega_s=\Omega\sqrt Q/(\Delta p_s/\rho)^{3/4}$ | 3.562 |
| Specific diameter (proxy) | $D_s=D(\Delta p_s/\rho)^{1/4}/\sqrt Q$ | 1.902 |

The Cordier diagram in D1 locates the provisional point at $(D_s,\Omega_s)=(1.902,3.562)$, for comparison with axial-machine design ranges. The location is tentative because of the pressure assumption and does not establish optimum efficiency.

## 7.2 Geometry description of all the parts of the axial fan

| Component / parameter | Geometry or dimension | Basis |
|---|---|---|
| Frame | Square, 120 × 120 × 25 mm (without pads) | Manufacturer |
| Frame with pads | 120 × 120 × 27 mm | Manufacturer |
| Mounting hole spacing | 105 × 105 mm | Manufacturer |
| Rotor tip diameter | 114 mm | Release 0 assumption; verify |
| Hub diameter | 50 mm | Release 0 assumption; verify |
| Blades | Nine curved, swept blades | Manufacturer description cited in D2 |
| Nominal radial tip clearance | 0.5 mm | Manufacturer |
| Inner frame bore | 115 mm if assumed rotor diameter and nominal clearance are combined | Derived, not measured |
| Blade radial span | 32 mm | Derived from assumed diameters |
| Hub / motor assembly | Central cylindrical assembly containing motor and bearing | Qualitative; axial dimensions pending |
| Motor supports | Struts connecting central motor housing to outer frame | Qualitative; count and dimensions pending |
| Anti-vibration pads | Located at frame corners | Manufacturer |

The rotor has twisted and swept blades; the chord varies along the span. The apparent frontal width is not necessarily the true section chord. Actual radial chord, thickness, twist, sweep and hub depth require measurements or a suitable geometric reference. The manufacturer CAD download can support dimensional inspection, subject to its stated limitations.

The assumed annular flow geometry gives:

$$r_h=25\,\mathrm{mm},\qquad r_t=57\,\mathrm{mm},\qquad r_m=\sqrt{\frac{r_h^2+r_t^2}{2}}=44.011\,\mathrm{mm}$$

$$A=\pi(r_t^2-r_h^2)=0.008244\,\mathrm{m^2},\qquad s_m=\frac{2\pi r_m}{Z}=30.726\,\mathrm{mm}$$

The hub-to-tip ratio is 0.439. The preliminary mean-section chord and blade angles are evaluated in Section 4; these are design estimates, not measured dimensions of the commercial fan. Detailed spanwise geometry will be determined during Release 2.

## 7.3 Materials and characteristics. Justification

The following material descriptions are based on the manufacturer's specifications. The justification is an engineering interpretation of their function; numerical mechanical properties are not assumed without grade-specific data.

| Component | Material / technology | Engineering justification |
|---|---|---|
| Impeller (blades and polymer hub) | Sterrox® LCP GF30 | Dimensional stability, low creep and thermal expansion help preserve the small tip gap; strength and damping are useful under centrifugal loading and vibration. |
| Frame and integrated supports | PBT ABS GF30 (manufacturer designation) | Glass-fibre reinforcement supports stiffness and dimensional stability of the stationary structure. |
| Corner pads | Silicone rubber | Compliance helps reduce vibration transmission to the mounting structure. |
| Motor hub reinforcement and shaft | Metal; exact alloy not specified | Supports alignment and dimensional precision. |
| Bearing | SSO2 bearing system | Supports rotation and stable rotor positioning; detailed material composition not specified. |
| Motor and electronics | Exact material grades not specified | Provide electromagnetic drive and PWM speed regulation; no quantitative material model is assigned. |

The small tip clearance is particularly relevant to material selection because deformation of the impeller can reduce the available clearance, while a larger clearance increases leakage. No structural or material-property validation is claimed at this stage.

## 7.4 Mean line analysis (D2)

### 7.4.1 Velocity triangles

Assuming incompressible flow, uniform axial velocity and no inlet swirl, the mean-section relations are:

$$c_x=Q/A,\qquad U=\Omega r_m,\qquad c_{\theta1}=0,\qquad c_{\theta2}\approx\frac{\Delta p_s}{\rho U}$$

$$\beta_1=\tan^{-1}(U/c_x),\qquad \beta_2=\tan^{-1}[(U-c_{\theta2})/c_x]$$

The relative angles are positive magnitudes measured from the axial direction; they are flow angles, not blade metal angles.

| Quantity | Inlet | Outlet |
|---|---:|---:|
| Axial velocity (m/s) | 1.537 | 1.537 |
| Tangential absolute velocity (m/s) | 0 | 1.348 |
| Absolute flow angle (°) | 0 | 41.25 |
| Relative flow angle (°) | 80.536 | 78.953 |
| Blade speed (m/s) | 9.218 | 9.218 |

The relative velocity ratio is $w_2/w_1=0.8581$, above the conventional De Haller threshold of 0.72. The local flow and work coefficients are $c_x/U=0.166696$ and $c_{\theta2}/U=0.146196$, respectively. They use different definitions from the global D1 coefficients.

### 7.4.2 Cascade geometry and diffusion factor

For the mean-section cascade, $s=30.726$ mm, $l$ is the chord, and $\sigma=l/s$ is solidity. The D2 model uses the Lieblein diffusion factor and a drag coefficient $C_D=0.02$:

$$DF=1-\frac{\cos\beta_1}{\cos\beta_2}+\frac{s}{2l}\cos\beta_1(\tan\beta_1-\tan\beta_2)$$

$$\tan\beta_m=\frac{\tan\beta_1+\tan\beta_2}{2}$$

$$C_L=2\frac{s}{l}\cos\beta_m(\tan\beta_1-\tan\beta_2)-C_D\tan\beta_m$$

Adopting $DF\leq0.5$ gives a maximum pitch-to-chord ratio of 4.9663 and a minimum chord of 6.1869 mm. At this minimum, the corrected lift coefficient is 1.4307 (1.5419 without drag). Increasing the chord to 8.5847 mm gives the D2 target $C_L=1.0$.

| Chord (mm) | Solidity | DF | Corrected $C_L$ | $Re_c$ |
|---:|---:|---:|---:|---:|
| 6.1869 | 0.2014 | 0.5000 | 1.4307 | 3,833 |
| 8.5847 | 0.2794 | 0.4000 | 1.0000 | 5,319 |
| 9 | 0.2929 | 0.3881 | 0.9487 | 5,576 |
| 12 | 0.3906 | 0.3265 | 0.6837 | 7,435 |
| 15 | 0.4882 | 0.2896 | 0.5248 | 9,293 |
| 20 | 0.6509 | 0.2527 | 0.3658 | 12,391 |
| 25 | 0.8137 | 0.2305 | 0.2704 | 15,489 |
| 30 | 0.9764 | 0.2158 | 0.2068 | 18,587 |

![D2 diffusion factor and lift coefficient versus chord]

The 9 mm chord is a rounded aerodynamic candidate satisfying both D2 criteria. A 20 mm chord is retained as a geometric alternative for investigation, not as a confirmed commercial blade dimension. Full numerical results are available in the [D2 case table].

### 7.4.3 Preliminary blade angles

Using the Carter deviation correlation and zero-incidence assumption implemented in D2, the estimated metal angles and camber are:

| Chord (mm) | Inlet metal angle (°) | Outlet metal angle (°) | Camber angle (°) | Deviation (°) | Stagger (°) |
|---:|---:|---:|---:|---:|---:|
| 8.5847 | 80.536 | 74.586 | 5.950 | 4.366 | 77.561 |
| 9 | 80.536 | 74.946 | 5.590 | 4.007 | 77.741 |
| 20 | 80.536 | 77.486 | 3.050 | 1.466 | 79.011 |

These are preliminary circular-arc-style geometric estimates; the low chord Reynolds numbers and the sensitivity of the deviation correlation limit their reliability. They are not final CAD inputs.

### 7.4.4 Sensitivity and limitations

| Assumed ideal pressure / static pressure | Outlet relative angle (°) | Minimum chord (mm) | Chord for $C_L=1$ (mm) |
|---:|---:|---:|---:|
| 0.8 | 79.310 | 4.587 | 6.754 |
| 1.0 | 78.953 | 6.187 | 8.585 |
| 1.2 | 78.571 | 8.061 | 10.478 |

The sensitivity factors are hypothetical, not measured efficiencies. The calculations satisfy the internal Euler and cascade balance checks in D2, but do not establish the actual fan performance. Radial variation, tip leakage, profile losses, and three-dimensional effects are not resolved by this mean-line model.

## 7.5 Conclusions and next steps

Release 1 establishes the operating point, dimensionless parameters, preliminary component geometry, material rationale and mean-section cascade estimates. Remaining geometry measurements should be recorded when available, particularly rotor and hub diameters, blade dimensions and motor supports. The pressure assumption must be reviewed before finalising the rotor design.

Release 2 will address radial analysis, mean-line corrections, blade and rotor design, and expected overall performance. No definitive radial loading or final CAD geometry is selected in this second release.
