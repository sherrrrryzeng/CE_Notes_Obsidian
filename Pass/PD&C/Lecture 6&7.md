---
date: 2025-09-18
Prof: Dr.ir. Farzad Mousazadeh
aliases:
  - BFD, PFD, P&ID
  - "Chapter 4: Instrument"
---
# Block Flow Diagram (BFD)
![[8f820cb49614bd7c3a9622f18eeae5d1304b66329b302b9e1b33055199a8cd49.png]]
- Block: Unit operation/equipment
- Straight line with arrow: Shows Material Flow
- Flow direction, preferred from left to right hand
- Lines can be vertical or horizontal
- Normally heavy streams at the bottom and light stream at top
- Necessary information of the blocks should be provided
- Material balance will be provided
- Heat and energy balance is not needed


# Process Flow Diagram (PFD)
graphical representation of chemical process, water treatment process, nuclear process, etc. which displays the relationship between ==main== process equipment. 
---Reactors, Distillation columns, Separators, Pumps, Compressors, Heat exchangers
![[42a4d3d6cdf3b1c48b99121fd92e0c97837e475184c2162e445a9670541b3a57.png]]

### What is included
- Major equipment items
- Connection between the items
- Bypasses and circulation lines
- Operational data like temperature, pressure, mass flow rate, density, composition, etc
- Process Stream
- Mass balance
- Heat Balance

### What is NOT included
- Pipeline including pipe classes and pipe numbers
- Instrumentation details (temperature and pressure measurements, etc..)
- Minor bypass lines
- Control equipment like control valve, controllers, sensors, etc..
- Shut-off valves, isolation valves, maintenance valves, etc..
- Maintenance vents and drains
- Relief and safety valves
- Flanges


# Piping and Instrumentation Diagram (P&ID)
shows all details of the process as well as control/safety system

### Used in
- Instrumentation and control design
- HAZOP(Hazard and Operability) study
- Management of changes
- Evaluate construction process
- Developing facility operation guidelines (start-up&shut-down procedures)
- Create philosophies for control and safety system
-*used by operators and engineers*

### What should be included
- Mechanical equipment with tag name and number (same as in PFD)
- All valves
- Piping, size and identification
- Vents, drains, special fittings, ...
- Start-up and flush line
- Flow directions
- Interconnection references
- Control and safety input/outputs
- Components and subsystems delivered by others
- Equipment rating and capacity

### What should NOT be included
- Instrument root valves (has its own system)
- Control relays
- Manual switches
- Primary instrument tubing and valves
- Pressure, temperature and flow data
- Elbow, tees and similar standard fitting
- Heat and material balance


# Instrument

## Control System Design
**Components**:
- sensors
- actuators
- controllers

**Sensors and Actuators**:
- Instrumentation is the limiting factor to the controlled process:
	- not every variable can be measured
	- not every variable can be manipulated
- Sensors and actuators are not ideal, they have **limit accuracy**
- Instrumentation is very **expensive**(over 15% of total CAPEX)
- Computation power is not important anymore nowadays

**Sensors**:
- Sends electrical signal with the process variable
- Range(zero/span)
- Repeatability
- Dynamics

### Flow Sensors
- Orifice plates (*influence the flow, need more than one*)
	![[c490c674f98e4134c376ea5930d1c73d743d7f8e2d9c3a0e19353018cfba4d90.png]]
	-$F_{vol.}=C\sqrt{\frac{\triangle P}{\rho}}$
	-$F_{mass}=C\sqrt{\triangle P\rho}$
	
- Magnetic flow meters / Rotameters / Pitot tubes(mainly for gas systems)
	-Accuracy:1-4%
	-Rangeability: 4:1, 10:1
	-Noisy signals(filtering is needed)
	-Fast respond
	

### Temperature Sensors
- Thermocouples
	-Iron-Constantan 0-750°C
	-Chromel-Nickle 0-1250°C
	-Accuracy: 2°C, 0.75%
	
- Resistance Thermometers
	-Platinum: -250~1000°C
	-Nickle: -250~425°C
	-Copper: -200~250°C
	-Accuracy: 0.1% of the Span
	-Time Constant: about 30s

### Pressure Sensors
- Principle: Measuring the deformation of an elastic transducer
![[5c59e10fd321cdc7e4c2bca227d350e39676e62390ec6e741a5f1e1366584f5b.png]]

### Level Sensors
- Differences in static pressure
- Unlimited range
- Good accuracy, fast dynamics


### Quality Measurements
**Gas Liquid Chromatography**: 
- Separate a mixture in its components
- Residence time depends on the temperature and nature of component
- Different range and accuracy
- Slow dynamics(5-30 minutes)

**Electrode Quality Measurement**: 
- Principle: Measuring the potential difference between a measuring and a standard electrode (Nernst Equation)
- pH, Ammonia, Chloride, Fluoride, etc.. can be measured using this method
- The range and accuracy is application dependent
- The dynamics are first order with a time constant of 5-20s


**Quality Measuring Instruments**: 
- Clear difference between the quality measuring instruments with others (pressure, temperature, level and flow)
1. These devices are **more expensive**.
2. The installation/maintenance costs are also more expensive.
3. The reliability is lower because of their complexity. For instance, Gas Chromatograph has a temperature-controlled oven (including sensor, controller and heating element)


### Actuators (Control valves)
a device which produces force if electrical input is supplied to it. 
![[409a6d9415946311cf227ead84ea4294964e93436ecd7d11b86cd54038176dfb.png]]
Valve size:$$F=C_Vf(x)\sqrt{\frac{\triangle P_v}{\rho}}$$
![[0387bdef8c76ff1eef4f120b45ce63f85908be54dfee6ef6b6acc8647bf81fa6.png]]

- Valve characteristics: 
	-the relationship between stem position and flow: linear / equal percentage
	-different start-up/shut-up methods *(e.g. time period)*


## Controllers
1. Single loop digital controllers - take care of one control loop, support for complex loops
2. Programmable Logic Controller(==PLC==) - an area of control *(e.g. in washing machine or AC)*
3. Distributed Control System(==DCS==) - combination of all controllers