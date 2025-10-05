### Bosch Motronic MP7.2 ECU Pinout for TU5JP Engine

The Bosch Motronic MP7.2 (also known as SID 201 in PSA nomenclature) is an 88-pin ECU commonly used in Peugeot 206 (Phase 1, 1998–2001) and similar models with the TU5JP engine. It's a multi-connector ECU with a main 88-pin harness (typically gray or black plastic housing). The pinout below is grouped by function for clarity, based on standard PSA wiring diagrams. Pin numbers are from the ECU side (female connectors); wire colors are typical for Peugeot but can vary by model year or market—always cross-reference with your vehicle's harness using a multimeter or service manual (e.g., Peugeot 206 wiring diagram, section E4).

**Important Safety Notes**:
- Disconnect the battery before probing/wiring to avoid shorts or ECU damage.
- This is for reference only; incorrect wiring can cause engine failure, fires, or ECU bricking. Use official diagrams (e.g., from ElsaWin or Haynes manual) for your exact VIN.
- Grounds are critical—ensure low resistance (<0.5Ω) to chassis/engine block.
- For aftermarket swaps (e.g., Megasquirt), map these to equivalent inputs/outputs.

#### 1. Power Supply and Grounds
| Pin # | Function | Wire Color (Typical) | Description |
|-------|----------|----------------------|-------------|
| 1     | +12V Battery (Permanent) | Red | Constant power for memory/keep-alive (via fuse 15A in engine bay). |
| 2     | Ground (Chassis) | Black | Main ECU ground to chassis. |
| 3     | Ground (Engine) | Black | Power ground to engine block/cylinder head. |
| 4     | +12V Ignition Switched | Pink/Red | Switched power from ignition (via fuse 20A). |
| 88    | Ground (Sensor) | Black | Dedicated sensor ground (low-noise for CKP/TMP). |

#### 2. Crankshaft and Camshaft Sensors (Relevant to Trigger Offset)
| Pin # | Function | Wire Color (Typical) | Description |
|-------|----------|----------------------|-------------|
| 47    | CKP Signal (VR+) | White/Black | Crankshaft position sensor signal input (AC from VR sensor). |
| 99    | CKP Ground (VR-) | Black | Crank sensor ground (shared with other sensors). |
| 48    | CMP Signal (Hall/Hall Effect, if equipped) | Violet | Camshaft position sensor (not always used on TU5JP; some models have it for sequential). |
| 100   | CMP Ground | Black | Cam sensor ground. |

#### 3. Throttle and Temperature Sensors
| Pin # | Function | Wire Color (Typical) | Description |
|-------|----------|----------------------|-------------|
| 20    | TPS Signal | Blue | Throttle position sensor (0–5V analog). |
| 21    | TPS +5V Supply | Gray | 5V reference for TPS. |
| 22    | TPS Ground | Black | TPS signal ground. |
| 51    | ECT Signal | Green | Engine coolant temperature sensor (NTC thermistor). |
| 52    | IAT Signal | Yellow | Intake air temperature sensor (NTC). |
| 53    | ECT/IAT +5V | Gray | 5V pull-up for temp sensors. |

#### 4. Injectors and Fuel System
| Pin # | Function | Wire Color (Typical) | Description |
|-------|----------|----------------------|-------------|
| 12    | Injector 1 | Green/White | Cylinder 1 injector control (ground-driven). |
| 13    | Injector 2 | Green/Black | Cylinder 2. |
| 14    | Injector 3 | Green/Red | Cylinder 3. |
| 15    | Injector 4 | Green/Yellow | Cylinder 4. |
| 16    | Fuel Pump Relay | Brown | Output to fuel pump relay (via fuse 20A). |

#### 5. Ignition and Coils (Wasted-Spark)
| Pin # | Function | Wire Color (Typical) | Description |
|-------|----------|----------------------|-------------|
| 23    | Ignition Coil 1-4 | Orange | Coil pack primary (wasted-spark pairs 1-4 and 2-3). |
| 24    | Ignition Coil 2-3 | Orange/Black | Second coil circuit. |
| 25    | ECU Diagnostic K-Line | White/Red | OBD-II communication (ISO 9141). |

#### 6. Other Actuators and Outputs
| Pin # | Function | Wire Color (Typical) | Description |
|-------|----------|----------------------|-------------|
| 26    | Idle Air Control (IAC) Stepper A | Blue | IAC valve control (4-wire stepper). |
| 27    | IAC Stepper B | Blue/White | Phase B. |
| 28    | IAC Stepper C | Blue/Black | Phase C. |
| 29    | IAC Stepper D | Blue/Red | Phase D. |
| 30    | EVAP Purge Valve | Purple | Canister purge solenoid. |
| 31    | VVT Solenoid (if equipped) | Gray/Black | Variable valve timing (TU5JP typically none). |
| 32    | Tach Output | Yellow | RPM signal to dash/instruments. |

#### 7. Vehicle Speed and Switches
| Pin # | Function | Wire Color (Typical) | Description |
|-------|----------|----------------------|-------------|
| 33    | VSS Signal | Green/Black | Vehicle speed sensor (from gearbox). |
| 34    | Clutch Switch | Pink | Clutch pedal input (for neutral safety). |
| 35    | Brake Switch | White | Brake light switch (for cruise/ABS). |
| 36    | AC Request | Brown/White | A/C compressor clutch request. |

#### 8. Additional Inputs/Outputs
| Pin # | Function | Wire Color (Typical) | Description |
|-------|----------|----------------------|-------------|
| 40    | Knock Sensor 1 | Gray | Pre-det knock sensor (piezo). |
| 41    | Knock Sensor 2 | Gray/White | Bank 2 (inline-4 uses one typically). |
| 42    | O2 Sensor Heater | Black/Red | Lambda heater relay. |
| 43    | O2 Sensor Signal | White | Upstream O2 (narrowband). |
| 44    | O2 Sensor Ground | Black | O2 signal ground. |
| 80–87 | Reserved/Expansion | Varies | Unused or for options (e.g., immobilizer). |

#### Connector Layout Overview
- **Main Connector**: 88 pins in a single large block (4 rows of 22 pins each). Pins are numbered left-to-right, top-to-bottom (Row 1: 1–22, Row 2: 23–44, etc.).
- **Secondary Connectors**: Some models have a small 4-pin for diagnostics or power.

For a visual diagram, search for "Bosch MP7.2 pinout Peugeot 206" or consult PSA technical data (e.g., via Peugeot Planet or AutoData). If you're interfacing with aftermarket (e.g., for CKP trigger), focus on Pins 47/99 first. If this doesn't match your harness, provide your model year or a photo for more specifics!