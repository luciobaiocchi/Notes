# IOT

## 3.1 Embedded Systems based on SoC and RTOS - Summary

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

---

#### Layers/Levels

- **Highest-Level View**:
  - **High-level Languages / Applications**
  - **Operating System**
  - **Hardware**

---

#### Language/Application Level Zoom

- **Applications**
- **High-level Languages**
- **Compilers / Interpreters**
- **Virtual Machines**
- **Operating System**
- **Hardware**

---

#### Hardware Level Zoom

- **High-level Languages / Applications**
- **Operating Systems**
- **Assembler**
- **Machine Language (or Code)**
- **Computer Architecture**
  - **ALU (Arithmetic Logic Unit)**
  - **Memory**
  - **Boolean Arithmetic / Algebra**
  - **Combinatory & Sequential Logic Circuits**
  - **Boolean Logic**

---

#### Virtualisation Level Zoom

- **High-level Languages / Applications**
- **Operating System**
- **System Compiler**
- **System Virtual Machine**
- **Hardware**

---

#### Overall Software and Hardware Hierarchy

- **Software Hierarchy**:
  - **Applications**
  - **High-level Languages**
  - **Compilers / Interpreters**
  - **Virtual Machines**
  - **Operating System**
  - **System Compiler**
  - **System Virtual Machine**
- **Hardware Hierarchy**:
  - **Assembler**
  - **Machine Language**
  - **Computer Architecture**
  - **ALU and Memory**
  - **Boolean Arithmetic and Sequential Logic Circuits**
  - **Boolean Logic**

---

#### Levels and Interfaces

- **Main Interfaces**:
  - **Instruction Set Architecture (ISA)**:
    - **System ISA**: Interface for OS-level instructions.
    - **User ISA**: Interface for user-level instructions.
  - **Application Binary Interface (ABI)**: Combines user ISA and system call interface.
  - **System Call Interface**: Provides fundamental OS services to programs.
  - **Application Programming Interface (API)**: For high-level languages (e.g., C, Java).

---

##### Machine Interface: ISA

- **Application Software**
- **Operating System**
  - **System ISA**
  - **User ISA**
- **Execution Hardware**
  - **Physical Machine**
  - **System Interconnect (BUS)**
  - **Memory Translation**
  - **Controllers**
  - **I/O Device and Networking**
  - **Main Memory**

---

#### Machine Interface: ABI

- **Application Software**
  - **System Call Interface**
- **Operating System**
  - **Drivers**
  - **Memory Manager**
  - **Scheduler**
- **Execution Hardware**
  - **Abstract / Virtual Machine**
  - **System Interconnect (BUS)**
  - **Memory Translation**
  - **Controllers**
  - **I/O Device and Networking**
  - **Main Memory**

---

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

---

#### SoC Architecture

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

---

#### Real-Time Systems

- **Hard Real-Time**: Deadlines must be met (e.g., safety-critical systems).
- **Soft Real-Time**: Deadlines are preferred but not critical.
- **Scheduling Algorithms**:
  - **Rate Monotonic (RM)**: Fixed priorities based on task periods.
  - **Earliest Deadline First (EDF)**: Dynamic priorities based on deadlines.

---

#### Benefits of RTOS

- **Improved Responsiveness**: Minimizes overhead and maximizes CPU utilization.
- **Resource Management**: Efficient sharing of resources among tasks.
- **Simplified Development**: Abstraction layer for hardware access.
- **Portability**: Applications can run on different hardware platforms.

---

#### When to Use RTOS

- **Useful for**:
  - Complex embedded systems with multiple tasks.
  - Systems requiring real-time responsiveness.
- **Not useful for**:
  - Simple super-loop applications.
  - Single-task applications with small memory footprints.

---

#### Examples of RTOS Architectures

- **FreeRTOS**: Open-source RTOS with a modular architecture.
- **QNX Neutrino**: Commercial RTOS with a microkernel architecture.
- **RT Linux**: Real-time extension of the Linux kernel.

---

#### Scheduling in RTOS

- **Temporal Parameters**:
  - **Release time**: When a task is ready to execute.
  - **Execution time**: Time required to complete the task.
  - **Deadline**: Maximum allowed time for task completion.
- **Scheduling Strategies**:
  - **Priority-based**: Tasks are executed based on priority.
  - **Round-robin**: Tasks are executed in a cyclic order.
  - **Preemptive**: Higher priority tasks can interrupt lower priority ones.

---

#### Conclusion

- **SoC** and **RTOS** are essential for modern embedded systems, enabling complex, real-time applications with efficient resource management.
- **RTOS** provides deterministic behavior, making it suitable for real-time tasks, while **SoC** integrates all necessary components on a single chip, reducing system complexity.

---

#### References

- **FreeRTOS**: [https://www.freertos.org/](https://www.freertos.org/)
- **Comparison of RTOS**: [Wikipedia](https://en.wikipedia.org/wiki/Comparison_of_real-time_operating_systems)

## 3.2 From Embedded Systems to Internet of Things (IoT) - Summary

This module explores the transition from **Embedded Systems** to the **Internet of Things (IoT)**, focusing on the evolution of IoT, its impact on industries, and the integration of IoT with web technologies.

---

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

### References

- Kevin Ashton. *The Internet of Things Thing*. RFID Journal, 2009.
- Luigi Atzori, Antonio Iera, Giacomo Morabito. *The Internet of Things: A survey*. Computer Networks, 2010.
- Samuel Greengard. *The Internet of Things*. MIT Press.
- IoT Fundamentals: Networking Technologies, Protocols, and Use Cases for the Internet of Things. Hanes et al., Cisco Press, 2017.
  
## 3.3 Technologies and Protocols for Wireless Communication - Summary

#### Introduction
This module provides an overview of **wireless communication technologies and protocols** used in **embedded systems** and **IoT (Internet of Things)**. It covers the evolution of wireless communication, key protocols, and their applications in IoT.

---

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

---

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

#### Conclusion
- **Wireless communication** is essential for IoT, enabling devices to connect and exchange data.
- **Key technologies** include Wi-Fi, Bluetooth, ZigBee, and cellular networks (5G).
- **IoT-specific protocols** like 6LoWPAN, Thread, and Matter ensure efficient, secure communication in constrained environments.
- **Application-level protocols** like CoAP and MQTT facilitate data exchange in IoT systems.

---

#### References
- **IoT Fundamentals**: Networking Technologies, Protocols, and Use Cases for the Internet of Things. Hanes et al., Cisco Press, 2017.
- **Building Internet of Things with Arduino**, Charalampos Doukas.