# General information

# Schematic
## Schematic design rules
- Grid: 50 mil, 25 mil

# Components library rules
## Symbol configuration
- Pin length:       150  mil
- Name text size:   50   mil
- Number text size: 50   mil
- Position ofset:   5,10 mil
- IC "cap" heigh:   100  mil
- Pin with same name: covered
## Symbol parameters list
1.  Reference
2.  Value
3.  Footprint
4.  Datasheet
5.  Manufacturer
6.  Part Number
7.  Description(Standart place)
## Parameters placement
![placement example](images/sym_param_pls_ex.png)

## Footprint configuration
- Grid: 0.025mm
- Origin to middle
- Always shoud be pointer to first pin?
- Create field with ${REFERENCE} text in the middle using Fab layer
- Value field should be on Fab layer. 


# Board trace
## Stack up

| Name       | Material | Thickness | Epsilon R |
| ---------- |:---------| :---------| :-------- |
| F.Cu       | Copper   | 0.035 mm  | -         |
| PrePreg 1  | FR4(2116)| 0.11 mm   | 4.29      |
| In1.GND.Cu | Copper   | 0.035 mm  | -         |
| Core       | FR4      | 1.2 mm    | 4.5       |
| In2.PWR.Cu | Copper   | 0.035 mm  | -         |
| PrePreg 2  | FR4(2116)| 0.11 mm   | 4.29      |
| B.Cu       | Copper   | 0.035 mm  | -         |

## Plane Properties

| Property            | Value                  |
|:------------------- |:---------------------- |
| Corner smoothing    | Fillet                 |
| Fillet radius       | 0.3                    |
| Clearance           | 0(same with net class) |
| Minimum width       | 0.3                    |
| Pad connections     | Reliefs for PHT        |
| Thermal relief gap  | 0.2                    |
| Thermal spoke width | 0.2                    |
|                     |                        |
| Remove islands      | Always                 |

## Parent Net Classes parameters:

| Parent classes | Via size | Via hole | Track width | Clearance | Description |
|----------------|----------|----------|-------------|-----------|-------------|
| Signal_Dig     |   0.6 mm |   0.3 mm |     0.15 mm |   0.2 mm  | Digital low speed signals |
| Signal_Tenso   |   0.6 mm |   0.3 mm |     0.2 mm  |   1.0 mm  |
| Power_0P2A     |   0.6 mm |   0.3 mm |     0.2 mm  |   0.4 mm  |
| Power_0P5A     |   0.6 mm |   0.3 mm |     0.4 mm  |   0.4 mm  |
| Power_1P5A     |   0.6 mm |   0.3 mm |     0.8 mm  |   0.4 mm  |
| Signal_50Ohm   |   ------ |   ------ |     0.22 mm |   0.2 mm  |


### Power domains
- TENSO_PWR
- BAT_PWR
- BUZ_PWR
- MAIN_PWR

### Interface
- I2C
- SPI

### Buzzer
- None

### Flash Memory
- MEM_PWR
- MEM_CTL

### Motion sensor
- MEMS_PWR
- MEMS_INT

### RGB LED
- LED_CTL
- LED_PWR

### Program/Debug SWD Connector
- SWD_SIG

### BLE MCU
- MCU_XL
- MCU_XC
- MCU_PWR
- MCU_ANT_50OHM
- MCU_DCDC


### Fuel Gauge with Protection
- FUELGA_MOS_DRV
- FUELGA_NTC
- FUELGA_SR
- FUELGA_BAT
- FUELGA_PWR
- FUELGA_SIG

### Battery Charger DC-DC

- CHG_BAT_PWR
- CHG_BAT_SR
- CHG_BAT_CTL
- CHG_BAT_SIG

### Tensosensor Step-Up DC-DC
- TENSO_DCDC_PWR
- TENSO_DCDC_VFB
- TENSO_DCDC_CTL

### Tensosensor LDO
- TENSO_LDO_PWR
- TENSO_LDO_CTL

### Buzzer Step-Down DC-DC
- BUZ_DCDC_PWR
- BUZ_DCDC_CTL

### Main Step-Down DC-DC
- MAIN_DCDC_PWR
- MAIN_DCDC_CTL

### Tenso Sensor Differential Amplifier
- TENSO_AMP_LPSIG
- TENSO_AMP_SIG
- TENSO_AMP_OUT

### Tenso Sensor Voltage Reference
- TENSO_REF_SIG
- TENSO_REF_OUT


## Shorts 
AMP - amplifier
LIN - linear voltage converter 
DCDC - DC-DC voltage converter.
CS, SR - current sense resistor

SIG - low frequency signal 
OUT - output low frequency signal(ex. from tensosensor amplifier ) 
PWR - power signal(in power regulators)
SUP  - power supply signal(generally output from power regulators )
