# EVHACK-2.0-Powertrain-design-of-a-Front-Wheel-Drive-Car-Finalist-Project

# EVHACK-2.0-Powertrain-design-of-a-Front-Wheel-Drive-Car-Finalist-Project

## Objective
This project was our team's entry in **EVHACK 2.0** (Bosch Global Software Technologies), a national EV-technology hackathon where we reached the **final round**. We designed the complete powertrain for an electric car: the traction motor, the inverter and the motor control strategy. The design was modelled and simulated in MATLAB/Simulink and presented to the judges under time constraints.

**Team 21:** Vishnu R, Arya Sunil, Amarjith S, Sabari Priya A

### Goals

- Design the powertrain for an electric car to the desired specifications.
- Design a motor and an inverter that satisfy the requirements.
- Check the efficiency of the designed motor.
- Compare the actual vehicle velocity with the reference velocity.

### Skills Learned

- EV powertrain sizing from vehicle parameters and a drive cycle.
- Permanent magnet synchronous motor (PMSM) design: main dimensions, stator lamination geometry and rotor sizing.
- Field Oriented Control (FOC) using the Clarke and Park transforms.
- Three-phase voltage source inverter design and switching strategy.
- Modelling and simulation in MATLAB/Simulink.
- Teamwork and pitching a technical design under time pressure.

### Tools Used

- **MATLAB/Simulink** for vehicle, motor, FOC and inverter modelling.

## Design Summary

### 1. Vehicle Requirements and Powertrain Sizing
The powertrain was sized from the vehicle parameters and a drive cycle, using a Simulink model to find the peak torque and power at the wheels.

| **Parameter** | **Target** |
|---------------|-----------|
| Total mass | 1400 kg |
| Top speed | 130 km/h |
| Acceleration time | 15 s (2.407 m/s²) |
| Gradability | 10% |
| Frontal area | 2.2 m² |

**Result:** peak wheel torque of 481 Nm and peak wheel power of 46.2 kW.

### 2. Motor Specification
With a gear ratio of 3.5, the motor was sized and then overdesigned for margin:

| **Parameter** | **Value** |
|---------------|-----------|
| Motor power (after overdesign) | 50.8 kW |
| Motor torque (after overdesign) | 151.17 Nm |
| Rated speed | 3532 RPM |
| Battery voltage | 400 V |
| Motor line-to-line voltage | 275 V (star connection) |
| Desired efficiency | 95% |
| Poles / slots | 6 / 36 |
| Air gap | 0.7 mm |
| Magnet type | NdFeB |

### 3. Motor Design
The main dimensions were derived from the output equation, using a magnetic loading of 0.55 T and an electric loading of 35 kA/m:

- Stator core internal diameter: 139 mm
- Stator core length: 218 mm
- Stator outer diameter: 196.54 mm
- Shaft diameter: 34.14 mm

The stator lamination geometry, slot area and rotor magnet dimensions were then worked out. The resulting motor has a power density of 0.8129 kW/kg and a torque density of 2.41 Nm/kg, with a rotor weight of 25.27 kg.

### 4. Field Oriented Control (FOC)
FOC was used to decouple torque and flux. The Clarke transform converts the three-phase abc quantities into the stationary αβ frame, and the Park transform converts them into the rotating dq frame.

### 5. Inverter Design
A three-phase voltage source inverter supplies the motor with a variable frequency of 0 to 900 Hz, at 250 V peak phase-neutral. MOSFETs were chosen over IGBTs because of the lower blocking voltage, which allows a high switching frequency of 50 kHz. The switching strategy aims for high DC bus utilization, low power losses and low harmonic distortion.

*Ref 1: Simulink Model (FOC and Inverter)*
![Simulink Model](link-to-image)

*Ref 2: Inverter Output*
![Inverter Output](link-to-image)

## Outcome

Reached the **final round of EVHACK 2.0** (Bosch Global Software Technologies), designing and pitching a complete EV powertrain solution.

*Ref 3: Final Round Certificate*
![EVHACK 2.0 Final Round Certificate](images/evhack-certificate.png)
