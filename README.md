# PLC Water Tank Control using CODESYS

## 📌 Project Overview

This project demonstrates an **Automatic Water Tank Control System using PLC programming in CODESYS**.

The system monitors the water level of a tank using two Boolean sensors, `TankLow` and `TankHigh`, and automatically controls a water pump based on the detected water-level condition.

The control logic is implemented using **IEC 61131-3 Structured Text (ST)** and tested using the **CODESYS Control Win V3 simulation environment**.

### Technologies and Concepts Used

- PLC Programming
- CODESYS
- IEC 61131-3
- Structured Text (ST)
- Boolean Logic
- IF-ELSIF-ELSE Conditional Logic
- Sensor-Based Automation
- Automatic Pump Control
- PLC Simulation
- Debugging and Testing

---

## 🛠️ Software and Tools Used

- **CODESYS V3.5 SP22 Patch 3**
- **CODESYS Control Win V3**
- **Structured Text (ST)**
- **PLC Simulation**

---

## ⚙️ System Variables

| Variable | Type | Description |
|---|---|---|
| `TankLow` | BOOL | Indicates that the tank water level is low |
| `TankHigh` | BOOL | Indicates that the tank has reached the high-water level |
| `Pump` | BOOL | Represents the ON/OFF state of the water pump |

---

## 🔄 Working Principle

The PLC continuously monitors the `TankLow` and `TankHigh` sensors and controls the pump according to the water-level conditions.

The control logic follows a priority-based approach:

- When `TankHigh` is **TRUE**, the pump is switched **OFF** because the tank has reached the high-water level.
- When `TankHigh` is **FALSE** and `TankLow` is **TRUE**, the pump is switched **ON** to fill the tank.
- When both sensors are **FALSE**, the pump maintains its previous state.
- When both sensors are **TRUE**, the `TankHigh` condition gets priority, so the pump remains **OFF**.

The logic was developed and tested in CODESYS using PLC simulation.

---
# Visualisation image

<img src="" width="700"/>


# 🧪 Simulation and Test Cases

The PLC control system was tested using different combinations of the `TankLow` and `TankHigh` sensor inputs. These test cases were used to verify whether the pump responds correctly under different tank-level conditions.

## Test Case 1: Both Sensors OFF

### Input Condition

- `TankLow = FALSE`
- `TankHigh = FALSE`

### Expected Behavior

The tank is not indicating a low-level condition and has also not reached the high-level condition. Therefore, the pump maintains its previous state.

During the initial simulation, the pump was **OFF**.

### Simulation Result

<img src="https://github.com/SujalPatil1616/PLC-Water-Tank-Control-CODESYS/blob/main/01_Simulation_Both_Sensors_OFF.png" alt="Test Case 1 - Both Sensors OFF" width="700"/>

### Result

- TankLow: **FALSE**
- TankHigh: **FALSE**
- Pump: **FALSE (OFF)**
- **Status: PASS ✅**

---

## Test Case 2: Tank Low – Pump ON

### Input Condition

- `TankLow = TRUE`
- `TankHigh = FALSE`

### Expected Behavior

The `TankLow` sensor indicates that the water level is low. Since the high-level sensor is not active, the PLC turns the pump **ON** to fill the tank.

### Simulation Result

<img src="https://github.com/SujalPatil1616/PLC-Water-Tank-Control-CODESYS/blob/main/02_Simulation_TankLow_TRUE_Pump_ON.png" alt="Test Case 2 - Tank Low Pump ON" width="700"/>

### Result

- TankLow: **TRUE**
- TankHigh: **FALSE**
- Pump: **TRUE (ON)**
- **Status: PASS ✅**

---

## Test Case 3: Tank High – Pump OFF

### Input Condition

- `TankLow = FALSE`
- `TankHigh = TRUE`

### Expected Behavior

The `TankHigh` sensor indicates that the tank has reached its high-water level. The PLC therefore switches the pump **OFF** to prevent further filling.

### Simulation Result

<img src="https://github.com/SujalPatil1616/PLC-Water-Tank-Control-CODESYS/blob/main/03_Simulation_TankHigh_TRUE_Pump_OFF.png" alt="Test Case 3 - Tank High Pump OFF" width="700"/>

### Result

- TankLow: **FALSE**
- TankHigh: **TRUE**
- Pump: **FALSE (OFF)**
- **Status: PASS ✅**

---

## Test Case 4: Both Sensors ON – High-Level Priority

### Input Condition

- `TankLow = TRUE`
- `TankHigh = TRUE`

### Expected Behavior

Both sensors are active at the same time. Since the `TankHigh` condition has higher priority in the control logic, the pump remains **OFF**.

This ensures that the pump does not continue filling the tank when the high-water-level condition is detected.

### Simulation Result

<img src="https://github.com/SujalPatil1616/PLC-Water-Tank-Control-CODESYS/blob/main/04_Simulation_Both_Sensors_True_Pump_OFF.png" alt="Test Case 4 - Both Sensors TRUE" width="700"/>

### Result

- TankLow: **TRUE**
- TankHigh: **TRUE**
- Pump: **FALSE (OFF)**
- **Status: PASS ✅**

---

## 📊 Test Case Summary

| Test Case | TankLow | TankHigh | Pump | Result |
|---|---|---|---|---|
| Test Case 1 | FALSE | FALSE | OFF | ✅ PASS |
| Test Case 2 | TRUE | FALSE | ON | ✅ PASS |
| Test Case 3 | FALSE | TRUE | OFF | ✅ PASS |
| Test Case 4 | TRUE | TRUE | OFF | ✅ PASS |

---

## 🎯 Project Objectives

- To understand the fundamentals of PLC programming.
- To implement an automatic water tank control system.
- To develop control logic using CODESYS.
- To work with IEC 61131-3 Structured Text.
- To monitor water-level conditions using Boolean sensors.
- To automatically control a water pump.
- To implement priority-based control.
- To simulate and test the PLC program.
- To verify the system under different operating conditions.

---

## 📚 Key Learning Outcomes

Through this project, practical knowledge was gained in:

- PLC programming
- CODESYS environment
- IEC 61131-3 Structured Text
- Boolean logic
- Conditional statements
- Sensor-based automation
- Automatic pump control
- PLC simulation
- Debugging
- Testing and validation
- Industrial automation concepts

---

## 🚀 Future Improvements

The project can be further developed by integrating:

- Physical water-level sensors
- PLC digital input/output modules
- Relay or contactor for pump control
- Real water pump
- HMI for monitoring
- Manual/Automatic operating modes
- Overflow alarm
- Dry-run protection
- Emergency stop
- Timer-based pump protection
- IoT-based remote monitoring
- Water consumption monitoring

---

## 📝 Conclusion

The **PLC Water Tank Control using CODESYS** project successfully demonstrates an automatic water-level monitoring and pump-control system using PLC programming.

The system uses `TankLow` and `TankHigh` as Boolean inputs to determine the appropriate pump operation. When the water level is low, the pump turns ON, while the high-level condition switches the pump OFF. When both sensors are active, the high-level condition receives priority.

The system was tested through **four different simulation test cases**, covering all possible combinations of the two Boolean sensors. All four test cases produced the expected results.

The project provided practical experience in **PLC programming, CODESYS, IEC 61131-3 Structured Text, Boolean logic, conditional control, PLC simulation, debugging, and industrial automation**.

Overall, the simulation successfully validated the automatic water tank control logic and provides a foundation for implementing the same concept using a physical PLC, sensors, and pump.
