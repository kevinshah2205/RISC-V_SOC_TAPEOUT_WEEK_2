# VSDBabySoC: A Comprehensive Guide to RISC-V Based SoC Design
[![RISC-V](https://img.shields.io/badge/RISC--V-Project-orange?style=for-the-badge&logo=riscv)](https://riscv.org/)
[![Week 2](https://img.shields.io/badge/Week%202-Part%201-green?style=for-the-badge)]()

## 📑 Table of Contents
1. [Introduction](#introduction)
2. [What is a System-on-Chip (SoC)?](#what-is-a-system-on-chip-soc)
3. [SoC Architecture and Structure](#soc-architecture-and-structure)
4. [How Does an SoC Work?](#how-does-an-soc-work)
5. [Types of SoCs](#types-of-socs)
6. [Introduction to VSDBabySoC](#introduction-to-vsdbabysoc)
7. [VSDBabySoC Architecture](#vsdbabysoc-architecture)
8. [Component Details](#component-details)
9. [How VSDBabySoC Works](#how-vsdbabysoc-works)
10. [Applications and Use Cases](#applications-and-use-cases)
11. [Conclusion](#conclusion)

---

## 🎯 Introduction

The VSDBabySoC project represents a journey into the fascinating world of integrated circuit design, specifically focusing on System-on-Chip (SoC) architecture. This educational platform combines open-source IP cores to create a functional, compact SoC based on the RISC-V instruction set architecture. By integrating a RISC-V processor (RVMYTH), a Phase-Locked Loop (PLL), and a Digital-to-Analog Converter (DAC) on a single chip using Sky130 technology, this project provides hands-on experience in digital design, analog interfacing, and system integration.

This documentation serves as both a learning resource and a technical reference for understanding how modern SoCs are designed, implemented, and verified.

---

## 🔍 What is a System-on-Chip (SoC)?

A **System-on-Chip (SoC)** is an integrated circuit that consolidates all essential components of an electronic system onto a single chip. Rather than using separate chips for different functions, an SoC combines the processor, memory, input/output interfaces, and specialized hardware accelerators into one compact package.

### Why SoCs Matter

Think of an SoC as a complete computer system miniaturized onto a single silicon die. This integration offers several revolutionary advantages:

- **Space Efficiency**: Combining multiple components reduces the physical footprint dramatically
- **Power Optimization**: Shorter interconnects mean lower power consumption and heat generation
- **Performance Enhancement**: Reduced signal propagation delays enable faster communication between components
- **Cost Reduction**: Single-chip manufacturing is more economical than multi-chip solutions
- **Reliability**: Fewer interconnections translate to fewer potential points of failure

---

## 🏗️ SoC Architecture and Structure

<img width="984" height="984" alt="image" src="https://github.com/user-attachments/assets/0b7b0ac6-5993-45b7-979b-38fca00c02cf" />

Modern SoCs are marvels of engineering that integrate diverse subsystems into a cohesive whole. A typical SoC architecture includes:

### Core Components

1. **Central Processing Unit (CPU)**
   - The computational heart of the SoC
   - Executes instructions and manages system operations
   - Can be single-core or multi-core depending on application requirements

2. **Memory Subsystem**
   - **RAM**: Volatile memory for active data storage
   - **ROM/Flash**: Non-volatile storage for firmware and persistent data
   - **Cache**: High-speed memory for frequently accessed data

3. **Input/Output Interfaces**
   - USB, UART, SPI, I2C controllers
   - GPIO (General Purpose Input/Output) pins
   - Enable communication with external peripherals

4. **Specialized Processing Units**
   - **GPU**: Graphics rendering and parallel computation
   - **DSP**: Digital signal processing for audio/video
   - **NPU**: Neural processing for AI/ML workloads

5. **Clock and Power Management**
   - Clock generation and distribution networks
   - Power gating and voltage/frequency scaling
   - Thermal management systems

6. **Interconnect Fabric**
   - Bus systems (AHB, AXI, Wishbone)
   - Network-on-Chip (NoC) for complex designs
   - Ensures efficient data flow between components

### SoC Design Flow

![SoC Design Flow](https://github.com/user-attachments/assets/54b5e8f9-f03d-4b53-a535-859360589119)

The design process follows a structured methodology:
1. **Specification**: Define requirements and constraints
2. **Architecture Design**: Plan system organization and interfaces
3. **RTL Design**: Create register-transfer level descriptions
4. **Verification**: Simulate and validate functionality
5. **Synthesis**: Convert RTL to gate-level netlist
6. **Physical Design**: Place and route components on silicon
7. **Manufacturing**: Fabricate the actual chip

---

## ⚙️ How Does an SoC Work?

An SoC operates through the coordinated interaction of its various subsystems, orchestrated by clock signals and communication protocols.

### Operational Flow

1. **Power-On and Initialization**
   - Boot ROM loads initial firmware
   - Clock and power management systems stabilize
   - Processor begins executing boot code

2. **Clock Distribution**
   - A master clock source (often a PLL) generates the primary clock
   - Clock distribution networks deliver synchronized signals to all components
   - Different clock domains may operate at different frequencies

3. **Data Processing Pipeline**
   - CPU fetches instructions from memory
   - Data moves through processing units via interconnect fabric
   - Results are written back to memory or output interfaces

4. **Peripheral Communication**
   - I/O controllers handle external device communication
   - Interrupt systems notify CPU of events requiring attention
   - DMA controllers enable data transfers without CPU intervention

---

## 🎨 Types of SoCs

SoCs can be categorized based on their intended applications and design philosophy:

### 1. Microcontroller-Based SoCs
- Optimized for embedded control applications
- Low power consumption and cost-effective
- Examples: ARM Cortex-M series, Atmel AVR
- **Use Cases**: IoT sensors, home appliances, automotive control systems

### 2. Microprocessor-Based SoCs
- Feature powerful CPUs capable of running operating systems
- Support complex multitasking and high-performance computing
- Examples: Apple A-series, Qualcomm Snapdragon
- **Use Cases**: Smartphones, tablets, laptops

### 3. Application-Specific SoCs (ASSoC)
- Custom-designed for specific high-performance tasks
- Optimized for particular workloads
- Examples: AI accelerators, network processors, media codecs
- **Use Cases**: Data centers, telecommunications, professional graphics

---

## 🌟 Introduction to VSDBabySoC

![VSDBabySoC Architecture](https://github.com/user-attachments/assets/38253bb7-b658-496d-a043-15402219e089)

**VSDBabySoC** is an educational SoC platform designed to demonstrate fundamental concepts in digital IC design and mixed-signal integration. Built on the open-source RISC-V architecture, it serves as a practical learning tool for understanding how modern chips are designed, verified, and fabricated.

### Project Objectives

1. **Educational Platform**: Provide hands-on experience with SoC design concepts
2. **IP Integration**: Demonstrate the integration of multiple IP cores
3. **Mixed-Signal Design**: Bridge digital and analog domains through DAC interface
4. **Open-Source Advocacy**: Utilize completely open-source tools and IP cores
5. **PDK Exploration**: Leverage SkyWater Sky130 PDK for real fabrication potential

### Key Features

- **RISC-V Based**: Uses the RVMYTH processor core implementing RV32I base instruction set
- **Complete System**: Includes processor, clock generation, and analog output capability
- **Sky130 Technology**: Designed for the open-source 130nm process
- **Fully Documented**: Comprehensive documentation for learning and experimentation
- **Simulation Ready**: Includes testbenches for pre- and post-synthesis verification

---

## 🔧 VSDBabySoC Architecture

The VSDBabySoC integrates three primary IP blocks into a cohesive system:

```
┌─────────────────────────────────────────────────────────┐
│                    VSDBabySoC                           │
│                                                         │
│  ┌──────────┐      ┌──────────┐      ┌──────────┐       │
│  │          │ CLK  │          │      │          │       │
│  │   PLL    │─────▶│  RVMYTH  │      │   DAC    │       │
│  │          │      │  (RISC-V)│──────│          │───▶Out│ 
│  └──────────┘      │          │ 10bit│          │       │
│                    └──────────┘      └──────────┘       │
│                         │                               │
│                     Register r17                        │
└─────────────────────────────────────────────────────────┘
```

### System Signals

**Inputs:**
- `reset`: System reset signal
- `VCO_IN`: PLL voltage-controlled oscillator input
- `ENb_CP`: PLL charge pump enable (active low)
- `ENb_VCO`: PLL VCO enable (active low)
- `REF`: PLL reference clock signal
- `VREFH`: DAC reference voltage (high)

**Outputs:**
- `OUT`: Analog output from DAC
- `CLK`: System clock from PLL (internal)

**Internal Signals:**
- `RV_TO_DAC[9:0]`: 10-bit digital bus from processor to DAC

---

## 🧩 Component Details

### 1. RVMYTH (RISC-V Processor Core)

The heart of VSDBabySoC is the RVMYTH processor, a compact RISC-V implementation.

**Specifications:**
- **ISA**: RV32I (32-bit base integer instruction set)
- **Pipeline**: Multi-stage pipeline architecture
- **Registers**: 32 general-purpose registers (x0-x31)
- **Output**: 10-bit data from register r17 (x17)

**Functionality:**
- Executes RISC-V assembly instructions
- Performs arithmetic and logical operations
- Manages data flow within the SoC
- Updates output register cyclically for DAC conversion

**Interface:**
```verilog
module rvmyth(
    input CLK,
    input reset,
    output [9:0] OUT
);
```

The processor continuously executes a program that updates register r17 with values intended for analog conversion, effectively generating a digital waveform pattern.

### 2. AVSDPLL (Phase-Locked Loop)

![PLL Block Diagram](https://github.com/user-attachments/assets/217d602f-003d-4606-9bca-855a4832764c)

The PLL generates a stable, synchronized clock signal for the entire system.

**Components:**
- **Phase Detector**: Compares reference and feedback signals
- **Charge Pump**: Converts phase difference to voltage
- **Loop Filter**: Smooths the control voltage
- **Voltage-Controlled Oscillator (VCO)**: Generates output clock
- **Frequency Divider**: Provides feedback for frequency multiplication

**Why PLLs are Essential:**

1. **Clock Multiplication**: Generate high-frequency clocks from low-frequency references
2. **Jitter Reduction**: Clean up noisy clock signals
3. **Phase Alignment**: Ensure precise timing relationships
4. **Frequency Synthesis**: Create multiple clock domains with precise ratios

**Interface:**
```verilog
module avsdpll(
    input VCO_IN,
    input ENb_CP,
    input ENb_VCO,
    input REF,
    output CLK
);
```

**Crystal Oscillator Considerations:**

Off-chip crystals have inherent limitations:
- **Frequency Error**: Measured in parts per million (ppm)
- **Temperature Drift**: Frequency varies with ambient temperature
- **Aging**: Long-term frequency drift over years
- **Load Capacitance**: External capacitors affect frequency

PLLs overcome these limitations by locking to the crystal's frequency and providing a clean, stable clock signal with reduced jitter and the ability to multiply to higher frequencies.

### 3. AVSDDAC (Digital-to-Analog Converter)

The DAC bridges the digital and analog worlds, converting processor output to analog signals.

**Architecture Types:**


1. **Weighted Resistor DAC**
   
   ![Weighted Resistor DAC](https://github.com/user-attachments/assets/344e4ffd-7509-41e7-ac42-21a553b3db11)
   
   - Uses binary-weighted resistors
   - Simple but requires precise resistor matching
   - Resistor values: R, 2R, 4R, 8R, etc.

2. **R-2R Ladder DAC**
   
   ![R-2R Ladder DAC](https://github.com/user-attachments/assets/5c15f424-1a94-4424-b019-a76c0ca0db43)
   
   - Uses only two resistor values (R and 2R)
   - Better matching and scalability
   - Preferred for integrated circuits

**VSDBabySoC DAC Specifications:**
- **Resolution**: 10 bits (1024 discrete levels)
- **Input**: Digital word from processor
- **Output**: Proportional analog voltage
- **Reference**: VREFH sets the full-scale output

**Interface:**
```verilog
module avsddac(
    input [9:0] D,
    input VREFH,
    output OUT
);
```

**Conversion Formula:**
```
V_OUT = (D / 1023) × VREFH
```

Where D is the 10-bit digital input value (0-1023).

---

## 🔄 How VSDBabySoC Works

### System Operation Sequence

1. **Power-On and Reset**
   - System receives power and reset signal is asserted
   - All registers and state machines initialize to known states
   - PLL begins locking process to reference clock

2. **Clock Generation and Stabilization**
   - PLL locks to the reference frequency (REF)
   - VCO generates a stable clock signal at the desired frequency
   - Clock distribution network delivers CLK to RVMYTH
   - System waits for PLL lock before starting processor

3. **Processor Execution**
   - RVMYTH begins fetching and executing instructions
   - Program loop updates register r17 with sequential values
   - Values represent a digital waveform pattern (e.g., ramp, sine approximation)
   - 10-bit output updates synchronously with system clock

4. **Digital-to-Analog Conversion**
   - DAC continuously samples the 10-bit digital input
   - Resistor network converts digital code to proportional voltage
   - Analog output (OUT) reflects the digital waveform pattern
   - Output can drive external analog devices

### Data Flow Example

```
Clock Cycle 1: r17 = 0x000 → DAC OUT = 0.00V
Clock Cycle 2: r17 = 0x100 → DAC OUT = 0.80V
Clock Cycle 3: r17 = 0x200 → DAC OUT = 1.60V
...
Clock Cycle N: r17 = 0x3FF → DAC OUT = 3.30V (VREFH)
```

This creates a continuous analog waveform that could represent:
- Audio signals for sound generation
- Control voltages for analog circuits
- Video signals for display devices
- Sensor calibration signals

---

## 🌐 Applications and Use Cases

### Educational Applications

1. **Digital Design Fundamentals**
   - Understand processor architecture
   - Learn Verilog/SystemVerilog HDL
   - Practice RTL design and verification
   - Explore synthesis and timing analysis

2. **Mixed-Signal Integration**
   - Bridge digital and analog domains
   - Understand ADC/DAC principles
   - Learn about signal integrity and noise

3. **SoC Design Methodology**
   - IP core integration techniques
   - Clock domain crossing
   - System-level verification
   - Design-for-testability concepts

### Practical Extensions

1. **Audio Generation**
   - Implement waveform generators (sine, square, triangle)
   - Create simple music synthesizers
   - Generate DTMF tones

2. **Signal Processing**
   - Digital filters (FIR, IIR)
   - FFT/IFFT implementations
   - Modulation schemes

3. **Communication Interfaces**
   - UART for serial communication
   - SPI/I2C for peripheral control
   - Simple wireless protocols

4. **Sensor Interfacing**
   - Temperature sensors
   - Accelerometers
   - Light sensors

### Industry Relevance

Understanding VSDBabySoC prepares students for:
- ASIC/FPGA design roles
- Embedded systems engineering
- Digital verification positions
- Physical design and implementation
- Mixed-signal IC design

---

## 🎓 Conclusion

The VSDBabySoC project demonstrates that complex systems can be broken down into understandable, manageable components. By integrating a RISC-V processor, PLL, and DAC into a single chip, this project encapsulates the essence of modern SoC design:

### Key Takeaways

1. **Integration is Power**: Combining multiple functions on one chip offers unprecedented efficiency and performance
2. **Standardization Matters**: Open standards like RISC-V democratize chip design
3. **Mixed-Signal Design**: Real-world applications require bridging digital and analog domains
4. **Verification is Critical**: Thorough simulation ensures design correctness before fabrication
5. **Open Source Enables Innovation**: Community-driven tools and IP accelerate learning and development

### The Learning Journey

VSDBabySoC serves as a stepping stone into the world of semiconductor design. From understanding basic digital logic to grasping complex system integration, this project provides hands-on experience with concepts that power everything from smartphones to supercomputers.

As Moore's Law continues to drive integration density, and as new paradigms like chiplets and heterogeneous integration emerge, the fundamentals learned through projects like VSDBabySoC remain relevant. The ability to think at multiple levels of abstraction—from transistors to systems—is what distinguishes great chip designers.

### Future Directions

Potential enhancements to explore:
- Additional peripheral interfaces (UART, SPI, I2C)
- More complex processor features (interrupts, exceptions)
- Memory hierarchy (cache, SRAM)
- Advanced DAC techniques (sigma-delta modulation)
- Complete physical design through Sky130 PDK
- Actual fabrication through open shuttle programs

---

## 📚 References and Resources

- **RISC-V ISA Specification**: [riscv.org](https://riscv.org)
- **SkyWater Sky130 PDK**: [skywater-pdk.readthedocs.io](https://skywater-pdk.readthedocs.io)
- **VSDBabySoC Repository**: [github.com/manili/VSDBabySoC](https://github.com/manili/VSDBabySoC)
- **RVMYTH Core**: [github.com/kunalg123/rvmyth](https://github.com/kunalg123/rvmyth)
- **AVSDPLL**: [github.com/lakshmi-sathi/avsdpll_1v8](https://github.com/lakshmi-sathi/avsdpll_1v8)
- **AVSDDAC**: [github.com/vsdip/rvmyth_avsddac_interface](https://github.com/vsdip/rvmyth_avsddac_interface)

---

**Author**: Kevin Shah
**Last Updated**: October 2025  
**License**: Open Source (Specify License)

*This project is part of the VSD (VLSI System Design) educational initiative.*
