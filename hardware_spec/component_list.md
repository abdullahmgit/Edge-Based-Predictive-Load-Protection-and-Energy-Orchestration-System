# Hardware Component Selection (Conceptual)

This document describes the hardware classes required to realize the proposed
edge-based CPS energy management system. No specific vendor or MCU is fixed at
this stage; selections are made at the architectural level.

NOTE:
This is an abstract bill of materials intended for feasibility analysis and
future prototyping.
Control & Compute Layer:
| Component Class              | Role                         | Rationale                                           |
| ---------------------------- | ---------------------------- | --------------------------------------------------- |
| Edge Controller (MCU / SBC)  | CPS execution & safety logic | Deterministic control, real-time capability         |
| Auxiliary Compute (optional) | AI advisory inference        | Can be integrated or external depending on platform |

Sensing Layer
| Sensor Type           | Measured Quantity     | Notes                       |
| --------------------- | --------------------- | --------------------------- |
| Voltage Sensor        | Line voltage          | Isolated, scaled            |
| Current Sensor        | Load / source current | Hall-effect preferred       |
| Frequency Detector    | Grid frequency        | Zero-cross or PLL-based     |
| Battery SOC Interface | State of Charge       | Via BMS or estimation logic |

Actuation & Switching
| Component                        | Purpose                    |
| -------------------------------- | -------------------------- |
| Load Control Relays / Contactors | Load shedding              |
| Source Selection Switches        | Grid / Battery / Renewable |

Safety & Isolation
| Component              | Purpose            |
| ---------------------- | ------------------ |
| Electrical Isolation   | Protect controller |
| Overcurrent Protection | Prevent damage     |
| Surge Protection       | Transient handling |

Power Supply
| Component       | Purpose              |
| --------------- | -------------------- |
| AC–DC Converter | Controller & sensors |
| DC Regulation   | Stable logic rails   |
