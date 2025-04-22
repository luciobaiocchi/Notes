# Recap of Electrical Components and Circuits

## Electric Charge
- **Atom**: Composed of electrons (negative charge), protons (positive charge), and neutrons (neutral charge).
- **Electron Charge (Q)**: Measured in Coulombs (C). 1 C = charge of 6.25 * 10^18 electrons.
- **Materials**:
  - **Conductors**: Many free electrons (e.g., copper, silver).
  - **Semiconductors**: Fewer free electrons (e.g., silicon).
  - **Insulators**: Very few free electrons.

## Electric Field
- **Net Charge**: Excess electrons (negative charge) or protons (positive charge).
- **Electric Force**: Opposite charges attract, like charges repel.
- **Ions**: Atoms with a net positive (positive ions) or negative (negative ions) charge.

## Voltage (Potential Difference)
- **Definition**: Potential energy per unit charge. \( V = \frac{W}{Q} \).
- **Unit**: Volt (V). 1 V = 1 Joule/Coulomb.
- **Voltage Sources**:
  - **Battery**: Converts chemical energy into electrical energy.
  - **Power Supply**: Converts AC voltage to DC.
  - **Solar Cells**: Convert light into electrical energy.
  - **Generators**: Convert mechanical energy into electrical energy.

## Electric Current
- **Definition**: Ordered flow of electric charge. \( I = \frac{Q}{t} \).
- **Unit**: Ampère (A). 1 A = 1 Coulomb/second.
- **Types of Current**:
  - **Direct Current (DC)**: Constant direction (e.g., batteries).
  - **Alternating Current (AC)**: Periodically changing direction (e.g., mains electricity).

## Electric Power
- **Definition**: Energy consumed per unit time. \( P = \frac{W}{t} \).
- **Unit**: Watt (W). 1 W = 1 Joule/second.
- **Energy Consumption**: \( W = P \cdot t \) (e.g., kWh).

## Resistance
- **Definition**: Opposition to the flow of current. \( R = \frac{V}{I} \).
- **Unit**: Ohm (Ω). 1 Ω = 1 Volt/Ampère.
- **Ohm’s Law**: \( V = I \cdot R \).
- **Power Dissipation**: \( P = V \cdot I = I^2 \cdot R = \frac{V^2}{R} \).

## Electronic Components
- **Passive**: Resistors, capacitors, inductors, diodes.
- **Active**: Transistors, integrated circuits.
- **Resistors**: Voltage drop when current flows. Color code for value identification.
- **Capacitors**: Store electric charge. Capacitance measured in Farads (F).
- **Inductors**: Generate magnetic fields with varying current.
- **Diodes**: Allow current to flow in only one direction.
- **LEDs**: Light-emitting diodes.
- **Transistors**: Amplify signals or act as switches.

## Kirchhoff’s Laws
- **First Law (Node Rule)**: The sum of currents entering a node equals the sum of currents leaving.
- **Second Law (Loop Rule)**: The algebraic sum of voltages in a closed loop is zero.

## Resistors and Capacitors in Series and Parallel
- **Resistors**:
  - **Series**: \( R_{eq} = R_1 + R_2 \).
  - **Parallel**: \( R_{eq} = \frac{R_1 \cdot R_2}{R_1 + R_2} \).
- **Capacitors**:
  - **Series**: \( C_{eq} = \frac{C_1 \cdot C_2}{C_1 + C_2} \).
  - **Parallel**: \( C_{eq} = C_1 + C_2 \).

## Measurement Instruments
- **Ammeter**: Measures current. Connected in series. Low internal resistance.
- **Voltmeter**: Measures voltage. Connected in parallel. High internal resistance.
- **Multimeter**: Measures voltage, current, and resistance.

---

# Introduction to Embedded Systems

## 1. Basic Concepts

### Definition
Embedded systems are computing systems designed to perform a specific function within electronic devices. They interact with the physical world through sensors and actuators and consist of both hardware and software.

### Key Characteristics
- **Specific Purpose**: Designed for a single application.
- **Efficiency & Limited Resources**: Optimized for low power consumption and minimal space.
- **Criticality**: Used in applications where reliability is crucial (healthcare, automotive, industry).
- **Responsiveness & Real-Time**: Must quickly react to environmental inputs.

### Common Applications
- Consumer electronics (smartphones, smartwatches, cameras)
- Home automation (thermostats, lighting systems)
- Automotive (navigation, safety systems)
- Healthcare (biomedical monitoring, wearables)
- Industry (process control, automation)

---

### Comparison of GPP, ASIP, FPGA, and ASIC

### General Purpose Processor (GPP)
- **Description**: A processor designed for a wide range of applications and general computing tasks.
- **Examples**: Intel, AMD, ARM Cortex-A CPUs.
- **Pros**:
  - Flexible and can run different software.
  - Easy to program and update.
- **Cons**:
  - Less efficient for specific tasks than specialized hardware.

### Application-Specific Instruction-set Processor (ASIP)
- **Description**: A processor tailored for a specific application domain.
- **Examples**: DSP (Digital Signal Processor) for audio/video processing.
- **Pros**:
  - Higher efficiency for targeted tasks.
  - Balance between flexibility and performance.
- **Cons**:
  - Less flexible than GPPs for general applications.

### Programmable Hardware (FPGA)
- **Description**: Reconfigurable hardware programmable for specific logic functions.
- **Examples**: Xilinx, Intel (Altera) FPGA.
- **Pros**:
  - High flexibility and upgradability.
  - Suitable for high-speed and custom applications.
- **Cons**:
  - Higher power consumption than ASICs.
  - Expensive for mass production.

### Application-Specific Integrated Circuit (ASIC)
- **Description**: A circuit optimized for a single application.
- **Examples**: Smartphone chips, Bitcoin mining chips.
- **Pros**:
  - Maximum efficiency for a dedicated function.
  - Low cost in large volumes.
- **Cons**:
  - No flexibility after manufacturing.
  - High initial development cost.

![difference cpu](difference_cpu.png)


## Embedded Systems: Interaction with the Environment via Sensors and Actuators

| **Aspect**        | **Sensors**                         | **Actuators**                          |
|------------------|---------------------------------|---------------------------------|
| **Function**     | Measure environmental phenomena | Produce physical effects       |
| **Output Type**  | Analog or digital               | Mechanical, thermal, optical   |
| **Examples**     | Temperature sensors, accelerometers | Motors, LEDs, heaters         |

---

## Communication Protocols

- **UART/USART**: Simple serial communication.
- **I2C**: Two-wire, multi-device communication.
- **SPI**: A faster, synchronous protocol requiring more wires, ideal for high-speed communication with peripherals.
- **JTAG**: A testing and debugging protocol used for hardware fault detection and software debugging in embedded systems.
- **CAN-BUS**: A robust, message-based protocol designed for automotive and industrial applications, capable of handling electromagnetic interference and supporting multiple nodes.


---

## Signals

Signals represent physical quantities and can be classified as:
- **Analog signals**
- **Discrete signals**
  - **Logical signals** (two values only)
  - **Coded signals** (more than two values)

# 2. Microcontrollers and Architecture

## Main Elements of a Microcontroller
- **CPU**
- **Memory (Flash, SRAM, EEPROM)**
- **GPIO (General Purpose Input/Output)**
- **Analog-to-Digital Converter (ADC)**
- **Timers**
- **Serial Communication Bus**

### Example: Arduino Uno
- MCU: **ATMega328P** (8-bit, 16 MHz, 32 KB Flash, 2 KB SRAM, 1 KB EEPROM)
  - Based on the von Neumann architecture:
    ![Von Neumann Machine](Vonn%20Neumann%20machine.png)
- **14** digital pins, **6** PWM pins, **6** analog inputs
- **Power Supply:** 5V, recommended input voltage 7-12V

### CPU Architectures
- **Von Neumann:** Single memory for both data and instructions
- **Harvard:** Separate memories for data and instructions (used in microcontrollers)

---

# 2.1 Embedded Systems and Object-Oriented Modelling

## Summary
This module focuses on the modelling of embedded software using paradigms such as Object-Oriented (OO) modelling. It explores the design and development of embedded software through top-down and bottom-up approaches, emphasizing the importance of modelling in understanding system complexities, reusability, portability, and extensibility.

## Key Concepts

### Modelling and Programming
- **Programming Paradigms**: OO is both a programming and modelling paradigm.
- **Model**: A representation of relevant aspects of a system, abstracting from irrelevant details.
- **Strong Relationships**: Between modelling and programming, as highlighted by the Scandinavian school.

### Importance of Modelling
- **Advantages**:
  - Better understanding of system complexities.
  - Reusability, portability, and extensibility.
  - Rigorous approaches to verify system correctness.

### Fundamental Dimensions of Modelling
- **Structure**: Parts composing a system.
- **Behaviour**: Computational behaviour of each part.
- **Interaction**: How parts interact.

### Paradigms and Languages
- **Modelling Paradigms**: Set of concepts and principles defining models (e.g., OO).
- **Modelling Languages**: Provide a rigorous way to represent models (e.g., UML).

### Object-Oriented Paradigm
- **Main Paradigm**: Effective abstraction for capturing and representing essential aspects of a problem.
- **Properties**:
  - Modularity, encapsulation, reuse, and extensibility.
- **Limitations**: Does not directly capture concurrency, asynchronous interactions, and distribution.

### Modelling Embedded Software
- **Two Main Parts**:
  - **Controller**: Encapsulates control/application logic.
  - **Controlled Elements**: Resources and devices managed by the controller.

### Button-LED Example
- **Model**: A button controlling an LED.
- **Interfaces**:
  - `Button`: `isPressed(): boolean`
  - `Led`: `switchOn()`, `switchOff()`
- **Control Loop**: Super-loop architecture for controlling the LED based on button state.

### From Models to Code: Arduino in Wiring/C++
- **Light Interface**: Abstract class in C++.
- **Led Device**: Concrete implementation of the Light interface.
- **Button Interface**: Basic button interface.
- **ButtonImpl**: Concrete implementation of the Button interface.
- **Setup and Loop**: Object creation and control loop in Arduino.

### Extension: LED with Light Intensity
- **LightExt Interface**: Extends the Light interface with `setIntensity(int)`.
- **LedExt Class**: Implements the LightExt interface, allowing control of LED intensity.

### Smart Light Controller
- **Evolution**: From a simple button-LED system to a smart light system.
- **Components**:
  - `MovementDetector`: Detects presence.
  - `LightDetector`: Measures light intensity.
  - `SmartLightController`: Controls the light based on presence and light intensity.

### Control Loop and Finite State Machines
- **Execution Model**: Based on a control loop (super-loop).
- **Finite State Machines (FSM)**: Used to describe state-based behaviours.

### Controller as an Active Entity
Controller as an Agent as first-class design abstraction.
- reactive + pro-active behaviour
- encapsulating a control flow
- task-oriented design
- **Conceptual Nature**: The controller is an active entity with its own control flow.
- **Agent Concept**: Used to model controllers as first-class active entities.

### Agents in Literature
- **Adopted in**: Artificial Intelligence, modelling and simulation, software engineering.
- **Agent-Oriented Software Engineering**: Agents encapsulate reactive and proactive behaviours.

### From Individual Agents to Multi-Agent Systems
- **Complex Systems**: Distributed systems with interacting/cooperating sub-systems.
- **Multi-Agent Systems**: Used to model systems like smart homes and smart cities.

# 2.2 Finite State Machines (FSM) in Embedded Systems

## Definition
Finite State Machines (FSM) are computational models that represent a system through a finite number of states, transitions, and actions.

## Key Concepts
- **States:** Distinct configurations representing the system status.
  affects how system reacts to input.
- **Transitions:** Changes from one state to another, triggered by specific events or conditions.
- **Events:** Inputs or occurrences that cause state transitions.
- **Actions:** Operations executed during state transitions or within a state.

## Types of FSM
- **Moore Machine:** Outputs depend only on the current state.
- **Mealy Machine:** Outputs depend on both the current state and inputs.

## ASYNCHRONOUS AND SYNCHRONOUS FSM
Two possibilities
- Asynchronous FSM, also called Event-triggered FSM
  - in this case, the valuation occurs anytime there is an input
event
  - in this case, the environment where the system works
establish when the reactions are evaluated and triggered
- Synchronous FSM, also called Time-triggered FSM
  in this case, valuations occur periodically, at a regular interval
of of time called period
-  the period determines the working frequency/rate of the
machine
## Application in Embedded Systems
FSMs are commonly used for:
- **Control logic:** Managing device behavior based on input signals.
- **Communication protocols:** Handling data transmission states.
- **Error detection and recovery:** Managing system faults effectively.

## Tools for FSM Modeling
Popular tools include Statecharts, UML diagrams, and software frameworks that support FSM integration into embedded systems.

## 3. Microcontroller Programming

### Code Structure in Wiring (Arduino)
```cpp
void setup() {
  pinMode(13, OUTPUT); 
}

void loop() {
  digitalWrite(13, HIGH);
  delay(1000);
  digitalWrite(13, LOW);
  delay(1000);
}
```

### Key Concepts
- **Super-loop:** infinite loop without an operating system.
- **GPIO interfacing:** handling digital/analog inputs and outputs.
- **Interrupts:** asynchronous event handling.
- **Serial communication:** sending and receiving data (UART, I2C, SPI).

## 4. Sensors and Actuators

### Sensors
Devices that detect physical quantities and convert them into electrical signals.
- **Analog:** produce continuous signals (thermistors, LDR, microphones)
- **Digital:** produce discrete signals (proximity sensors, encoders)

### Actuators
Devices that convert electrical signals into physical actions.
- **Motors (DC, stepper, servo)**
- **LEDs, displays, buzzers**
- **Relays, solenoid valves**

### ADC Conversion
Analog inputs are converted into numerical values (0-1023 on Arduino with a 10-bit ADC).
```cpp
int val = analogRead(A0);
```

## 5. Measurement and Error Considerations
- **Accuracy:** difference between measured and actual values.
- **Precision:** repeatability of measurements.
- **Systematic and random errors:** sources of measurement inaccuracies.


# 3.1 Embedded Systems based on SoC and RTOS - Summary

#### Introduction

This module covers embedded systems based on **System-on-a-Chip (SoC)** and **Real-Time Operating Systems (RTOS)**. It explores the transition from microcontrollers to SoCs, the architecture of SoCs, and the role of RTOS in embedded systems.

---

#### Operating Systems: Some Recall

#### Modern Computing Systems: A Bird’s Eye View

- **Computing System**: Composed of **software** and **hardware**.
  - **Highest Levels**: High-level programming languages, applications, and complex software systems.
  - **Lowest Levels**: Electronic circuits, logical ports, and binary logic.
- **Design and Construction Complexity**: Managed through **hierarchical levels (layers)**.
  - **Decomposition in Modules**: Each module encapsulates functionalities and defines an abstraction level.
  - **Hierarchical Organisation**: Each module corresponds to a layer, providing an interface to exploit functionalities while hiding implementation details.

#### Levels and Interfaces

- **Main Interfaces**:
  - **Instruction Set Architecture (ISA)**:
    - **System ISA**: Interface for OS-level instructions.
    - **User ISA**: Interface for user-level instructions.
  - **Application Binary Interface (ABI)**: Combines user ISA and system call interface.
  - **System Call Interface**: Provides fundamental OS services to programs.
  - **Application Programming Interface (API)**: For high-level languages (e.g., C, Java).

#### Key Concepts

- **ISA (Instruction Set Architecture)**: Separates hardware and software levels.
  - **User ISA**: Accessible by user programs.
  - **System ISA**: Accessible only by the OS (privileged instructions).
- **ABI (Application Binary Interface)**: Combines user ISA and system call interface.
- **System Call Interface**: Provides OS services to programs, transferring control to the OS kernel.

---

#### Conclusion

- **Operating Systems** act as intermediaries between **hardware** and **software**, providing abstraction and resource management.
- **Hierarchical layers** simplify the design and construction of computing systems.
- **Interfaces** like **ISA**, **ABI**, and **System Call Interface** enable communication between different levels of the system.

##### 1. **System-on-a-Chip (SoC)**

- **Definition**: An integrated circuit that combines most components of a computer system (CPU, memory, I/O controllers, etc.) on a single chip.
- **Examples**:
  - **Broadcom BCM2837**: Used in Raspberry Pi 3.
  - **ARM Sitara AM335x**: Used in BeagleBone and Arduino Tre.
  - **ESP8266** and **ESP32**: Popular IoT SoCs with Wi-Fi and Bluetooth capabilities.

###### 2. **Real-Time Operating Systems (RTOS)**

- **Definition**: Operating systems designed for embedded systems, providing deterministic and predictable behavior.
- **Features**:
  - Compactness, efficiency, reliability.
  - Support for multi-tasking and real-time scheduling.
- **Examples**:
  - **Open-source**: FreeRTOS, RT Linux.
  - **Commercial**: VxWorks, QNX Neutrino, Micrium uC/OS-III.

#### SoC Architecture

Uses RTOS

- **Components**:
  - Processors/cores (CPU, DSP).
  - Memory modules (ROM, RAM, Flash).
  - Clock, timers, and standard interfaces (USB, Ethernet, I2C, SPI).
  - Radio/network interfaces (Wi-Fi, Bluetooth).
  - DAC and ADC for analog signals.

---

#### RTOS Features

- **Determinism**: Predictable response times for real-time tasks.
- **Task Scheduling**:
  - **Preemptive**: Higher priority tasks can interrupt lower priority ones.
  - **Priority-based**: Tasks are executed based on their priority.
  - **Round-robin**: Tasks are executed in a cyclic order.
- **Task States**: Ready, Running, Waiting, Dormant.
- **Task Communication**: Semaphores, message queues, event flags.

#### When to Use RTOS

- **Useful for**:
  - Complex embedded systems with multiple tasks.
  - Systems requiring real-time responsiveness.
- **Not useful for**:
  - Simple super-loop applications.
  - Single-task applications with small memory footprints.
  - 
#### Scheduling in RTOS

- **Temporal Parameters**:
  - **Release time**: When a task is ready to execute.
  - **Execution time**: Time required to complete the task.
  - **Deadline**: Maximum allowed time for task completion.
- **Scheduling Strategies**:
  - **Priority-based**: Tasks are executed based on priority.
  - **Round-robin**: Tasks are executed in a cyclic order.
  - **Preemptive**: Higher priority tasks can interrupt lower priority ones.

### 1. Internet of Things (IoT)

- **Definition**: IoT refers to the network of physical objects (things) embedded with sensors, software, and connectivity to exchange data over the Internet.
- **Origin**: Introduced by Kevin Ashton in 1999, IoT aims to automate the digitalization of the physical world.
- **Impact**: IoT has transformed industries, enabling real-time data collection, automation, and predictive maintenance.

### 2. **IoT Evolution**

- **Stages**:
  1. **Product Stage**: Basic functionality (e.g., air conditioner).
  2. **Smart Product**: Programmable functionality (e.g., programmable air conditioner).
  3. **Smart Connected Products**: Internet-enabled (e.g., air conditioner controllable via smartphone).
  4. **Product Systems**: Interoperability between devices (e.g., smart thermostat, HVAC, and blinds).
  5. **System of Systems**: Integration across multiple domains (e.g., home, car, hospital).

### 3. **Industrial IoT (IIoT)**

- **Industry 4.0**: The fourth industrial revolution, characterized by the integration of IoT, big data, and automation in manufacturing.
- **Key Technologies**:
  - **SCADA Systems**: Supervisory Control and Data Acquisition systems for industrial automation.
  - **PLC Programming**: Programmable Logic Controllers (PLCs) are used to control industrial processes.
  - **OPC Standards**: Open Platform Communication for interoperability between industrial devices.

### 4. **IoT Architecture**

- **Core Components**:
  - **Things**: Embedded systems with sensors and actuators.
  - **Connectivity**: Communication protocols like MQTT, CoAP, and WebSockets.
  - **Cloud**: Data storage, processing, and analytics.
  - **Edge Computing**: Local data processing to reduce latency and bandwidth usage.

### 5. **IoT and Cloud Computing**

- **Cloud Services**:
  - **IaaS**: Infrastructure as a Service (e.g., virtual machines, storage).
  - **PaaS**: Platform as a Service (e.g., runtime environments, databases).
  - **SaaS**: Software as a Service (e.g., CRM, email).
- **IoT Applications**: Data collection, real-time analytics, and device management.

### 6. **Web of Things (WoT)**

- **Definition**: Extending IoT to the web by providing RESTful APIs for IoT devices.
- **Benefits**:
  - **Interoperability**: Standardized communication between devices.
  - **Ease of Integration**: Simplifies development and deployment of IoT applications.
  - **Scalability**: Supports large-scale IoT systems.

### 7. **IoT Challenges**

- **Security**: Ensuring data integrity and device authentication.
- **Privacy**: Protecting user data and ensuring compliance with regulations.
- **Interoperability**: Standardizing communication protocols and architectures.

---

### Applications of IoT

### 1. **Smart Cities**

- **Examples**: Traffic management, energy efficiency, and emergency response systems.
- **Technologies**: IoT-enabled sensors, cloud computing, and data analytics.

### 2. **Healthcare**

- **Examples**: Remote patient monitoring, wearable devices, and smart hospitals.
- **Technologies**: IoT sensors, mobile apps, and cloud-based data storage.

### 3. **Transportation and Logistics**

- **Examples**: Fleet management, predictive maintenance, and autonomous vehicles.
- **Technologies**: GPS, IoT sensors, and real-time data analytics.

### 4. **Smart Homes**

- **Examples**: Smart thermostats, lighting, and security systems.
- **Technologies**: IoT devices, mobile apps, and cloud integration.

---

### IoT Technologies and Protocols

### 1. **Communication Protocols**

- **MQTT**: Lightweight messaging protocol for IoT.
- **CoAP**: Constrained Application Protocol for resource-constrained devices.
- **HTTP/WebSockets**: For web-based IoT applications.

### 2. **Edge Computing**

- **Definition**: Processing data locally on edge devices to reduce latency and bandwidth usage.
- **Examples**: IoT gateways, edge servers.

### 3. **OPC Standards**

- **OPC-UA**: Unified Architecture for industrial IoT, enabling secure and interoperable communication.

---

### Conclusion

- **IoT** is transforming industries by enabling real-time data collection, automation, and predictive maintenance.
- **Industrial IoT (IIoT)** is driving the fourth industrial revolution (Industry 4.0) with advanced automation and data analytics.
- **Web of Things (WoT)** extends IoT to the web, enabling interoperability and simplifying IoT application development.
- **Challenges** such as security, privacy, and interoperability must be addressed to fully realize the potential of IoT.

---


## 3.3 Technologies and Protocols for Wireless Communication - Summary

#### Introduction
This module provides an overview of **wireless communication technologies and protocols** used in **embedded systems** and **IoT (Internet of Things)**. It covers the evolution of wireless communication, key protocols, and their applications in IoT.

#### Key Concepts

###### 1. **Wireless Communication in IoT**
- **Definition**: Wireless communication enables devices to exchange data without physical connections, crucial for IoT and M2M (Machine-to-Machine) systems.
- **Types**:
  - **Wired**: Ethernet, 802.11.
  - **Wireless**: Wi-Fi, Bluetooth, ZigBee, cellular networks (3G/4G/5G).

###### 2. **Internet Connection in IoT**
- **Indirect Connection**: Devices connect via a gateway (e.g., ZigBee, Bluetooth).
- **Direct Connection**: Devices connect directly to the Internet (e.g., Wi-Fi, 3G/4G/5G).
- **Protocols**: IP, TCP/IP, UDP/IP.

###### 3. **ISO-OSI Architecture**
- **Layers**: Application, Transport, Network, Data Link, Physical.
- **Internet Stack**: Hourglass model with IP at the core.

#### Wireless Technologies and Protocols

###### 1. **Short-Range Communication**
- **Examples**: Bluetooth (IEEE 802.15.1), Visible Light Communication (IEEE 802.15.7).
- **Range**: Up to 10 meters.

###### 2. **Medium-Range Communication**
- **Examples**: Wi-Fi (IEEE 802.11), ZigBee (IEEE 802.15.4).
- **Range**: Up to 100 meters.

###### 3. **Long-Range Communication**
- **Examples**: Cellular networks (2G, 3G, 4G, 5G), LPWA (Low-Power Wide-Area) technologies.
- **Range**: Over 1 mile.

---

#### Key Wireless Protocols

###### 1. **Wi-Fi (IEEE 802.11)**
- **Characteristics**: High data rate (up to 54 Mbps), range up to 150 meters, 5 GHz frequency.
- **Use Case**: Internet connectivity in embedded systems.

###### 2. **Bluetooth (IEEE 802.15.1)**
- **Characteristics**: Short-range, low power consumption, 2.4 GHz frequency.
- **Versions**: Classic Bluetooth, Bluetooth Low Energy (BLE), Bluetooth 5.
- **Topology**: Piconet (master-slave) and Scatternet (multiple piconets).

###### 3. **ZigBee (IEEE 802.15.4)**
- **Characteristics**: Low power, low data rate (up to 250 kbps), range up to 100 meters.
- **Topology**: Star, Mesh, Cluster Tree.
- **Use Case**: Home automation, industrial IoT.

###### 4. **Cellular Networks (2G, 3G, 4G, 5G)**
- **Characteristics**: High data rates (up to 10 Gbps for 5G), long range (km), high power consumption.
- **Use Case**: IoT applications requiring wide-area connectivity.

###### 5. **5G**
- **Characteristics**: High speed (1-10 Gbps), low latency (1-10 ms), designed for IoT.
- **Use Case**: Smart cities, autonomous vehicles, industrial IoT.

---

#### IoT-Specific Protocols

###### 1. **6LoWPAN**
- **Definition**: IPv6 over Low-Power Wireless Personal Area Networks.
- **Use Case**: Enables IP communication in low-power IoT devices.

###### 2. **Thread**
- **Definition**: IPv6-based protocol for low-power IoT devices.
- **Characteristics**: Secure, reliable, self-healing mesh network.
- **Use Case**: Home and building automation.

###### 3. **Matter**
- **Definition**: Open-source connectivity standard for smart home devices.
- **Characteristics**: Interoperable, secure, royalty-free.
- **Use Case**: Smart home ecosystems.

---

#### Application-Level Protocols

###### 1. **CoAP (Constrained Application Protocol)**
- **Transport**: UDP.
- **Use Case**: Lightweight, RESTful communication for IoT devices.

###### 2. **MQTT (Message Queuing Telemetry Transport)**
- **Transport**: TCP.
- **Use Case**: Publish/subscribe messaging for IoT.

---