### **Day 1 -Inception of open-source EDA, OpenLANE and sky130 PDK**

### How to Communicate with Computers

#### Introduction to the QFN-48 Package, Chip, Pads, Core, Die, and IPs

The **QFN-48 package** is a type of chip packaging that holds the chip and connects it to other circuits. Inside this package, you’ll find the **chip**, which contains the main processing unit, as well as **pads** (connections), the **core** (the central processing part), the **die** (the actual silicon piece), and **IPs** (intellectual properties or pre-designed parts of the chip).

#### Arduino Board Overview

The **Arduino board** is a microcontroller board. The highlighted area in the image shows the **chip** (the microprocessor) that connects to various other components of the board. This chip is designed using a process called **RTL to GDSII flow**, which involves going from a high-level design down to the physical chip fabrication.

Arduino has two main parts:
1. The **physical board**, which is programmable and contains the microcontroller.
2. The **IDE (Integrated Development Environment)**, which is software on your computer used to write and upload code to the board.

This process allows you to create projects and control the Arduino with code!

![Screenshot 2024-09-06 225530](https://github.com/user-attachments/assets/edf8edda-d505-4cfc-b11b-ac56d9fe05d4)
### Chip Components:

1. **Pads**: These are the contact points that allow signals to enter and exit the chip, connecting it to the outside world.

2. **Core**: The area where all the **logic gates** (which perform calculations and processing tasks) are located. This is the brain of the chip.

3. **Die**: This is the physical piece of silicon, and it represents the actual size of the chip. It is typically located in the center or corner of the chip package.

### Example: RISC-V SoC

A **RISC-V SoC** (System on Chip) typically includes components like:
- **SRAM** (Static Random Access Memory),
- **SOC** (System on Chip logic),
- **ADC** (Analog-to-Digital Converter),
- **DAC** (Digital-to-Analog Converter),
- **SPI** (Serial Peripheral Interface).

These components are often referred to as **foundry IPs** (Intellectual Properties), which are pre-designed blocks provided by the foundry (the place where chips are manufactured). Foundries use processes like **deposition** and **lithography** to fabricate chips.
![Screenshot 2024-09-06 225907](https://github.com/user-attachments/assets/c58b84ba-2039-4856-8d00-5cb21f3f1d7f)

### Introduction to RISC-V

**RISC-V** (pronounced "risk-five") represents the fifth generation of RISC (Reduced Instruction Set Computer) architecture, developed at the University of California, Berkeley. It is an **open standard instruction set architecture (ISA)**, meaning its design principles are available for anyone to use and modify without licensing fees, unlike most proprietary ISAs.

Many companies are now producing **RISC-V hardware**, and open-source operating systems supporting RISC-V are available. It is also supported by several well-known software development tools, making it widely accessible for both research and industry.

### Key Features of RISC-V:

- **Base Instruction Set**: It uses 32-bit fixed-length instructions, which are naturally aligned in memory for efficient processing.
  
- **Variable Length Extensions**: The instruction set supports extensions, allowing instructions to be composed of 16-bit units, providing flexibility for more complex tasks.

- **Address Space Variants**: 
  - RISC-V defines both **32-bit** and **64-bit** address spaces.
  - A **128-bit address space** specification exists but remains experimental, as real-world use for such large memory systems is still minimal.

### Hardware Design:

In RISC-V chips, the **chip is connected to the package** (the external housing) using **bond wires**, which allow communication between the internal circuits and the outside world. 
RISC-V's open-source nature and flexibility make it an exciting choice for a wide range of applications, from embedded systems to high-performance computing.

![Screenshot 2024-09-07 010438](https://github.com/user-attachments/assets/7de2df70-fd6a-4b59-8287-8763e2eddcb3)
### From Software Applications to Hardware

Here’s a simplified view of how applications run on a system:

1. **Application Software**: This is the program or app that you interact with, like a browser or a game.

2. **System Software**: The app passes through the system software, which translates the entire program into machine-readable binary code. The system software is made up of several layers, including:

   - **Operating System (OS)**: Manages input/output operations, allocates memory, and handles low-level system functions.
   
   - **Compiler**: Converts high-level programming languages like C, C++, or Java into instructions. These instructions are tailored to the specific hardware.

   - **Assembler**: Transforms the instructions from the compiler into binary numbers (machine code). This is the language that hardware understands.

3. **Hardware (Chip)**: The binary code is sent to the hardware, which processes the instructions and performs the required operations, generating the desired output.

### Instruction as the Bridge:
The **instruction set** acts as an interface between the C-language code (or any other programming language) and the hardware. The instructions created by the compiler and assembler allow the hardware to understand what needs to be done.

This is how the software, system software, and hardware work together to run apps on your device.

![Screenshot (1007)](https://github.com/user-attachments/assets/e8fc3772-685e-4cbc-844d-ae14d6444a7b)
### SoC Design and OpenLANE: An Introduction to Open-Source Digital ASIC Design

Designing a **Digital ASIC** (Application-Specific Integrated Circuit) involves various tools and components. Here’s an overview of key elements required from the start:

### Key Components of Digital ASIC Design:

#### 1. **RTL Design** (Register-Transfer Level Design)
RTL is a design abstraction used in digital circuit design, modeling the flow of digital signals between hardware registers and the logical operations performed on them. RTL is essential in designing **synchronous digital circuits** like processors. Several open-source resources are available for RTL designs, such as:
- **LibreCores**: [librecores.org](https://librecores.org)
- **OpenCores**: [opencores.org](https://opencores.org)
- **GitHub**: [github.com](https://github.com)

#### 2. **EDA Tools** (Electronic Design Automation)
EDA tools are software platforms used to design, simulate, and verify integrated circuits (ICs), printed circuit boards (PCBs), and electronic systems. These tools are essential for creating and refining the physical design of an IC.

**Open-source EDA tools** include:
- **Qflow**
- **OpenROAD**
- **OpenLANE**

These tools help automate the chip design flow from RTL to the final physical layout.

#### 3. **PDK Data** (Process Design Kit)
A **PDK** is a collection of files used as an interface between the **foundry** (FAB) and the design process. It contains data necessary for fabricating the chip, including:
- **Design Rules**: Such as DRC (Design Rule Check), LVS (Layout vs. Schematic), and REX (Rule Extraction).
- **Standard Cell Libraries**: Pre-designed logic gates and components.
- **I/O Libraries**: Libraries for input/output operations.

For example, in 2020, Google released the open-source **Skywater PDK** for the **130nm technology node**, offering an accessible way to design chips. While more advanced nodes like **5nm** exist, the **130nm** node is still widely used due to lower costs and sufficient performance for many applications.

### Example of 130nm Processors:
- **Intel Pentium 4 Extreme Edition (P4EE)**: 3.46 GHz (Released in Q4 2004).
- **Sky130_OSU**: A single-cycle **RISC-V RV32i CPU** in the 130nm process, capable of achieving clock speeds over 1 GHz.

In many applications, cutting-edge nodes like 5nm are not required, and older nodes (such as 130nm) still deliver impressive performance while keeping costs lower. OpenLANE and the Skywater 130nm PDK are good examples of how open-source tools are making chip design more accessible.

![Screenshot 2024-09-07 014639](https://github.com/user-attachments/assets/e51cfddc-dba6-4f75-b6d1-d52737e70b25)

### Step 1: **Synthesis**
In the synthesis step, the design described at the RTL (Register Transfer Level) is converted into a gate-level netlist using standard cell libraries (SCL). The resulting circuit is typically described in HDL (Hardware Description Language), and it is functionally equivalent to the original RTL design. The netlist is a list of gates and their connections, which represent the logic of the circuit. "Standard Cells" in this context refer to predefined logic elements with regular layouts, often represented in formats like HDL or SPICE. These cells are used to build more complex circuits.

### Step 2: **Floor/Power Planning**
This step is divided into two main tasks: **Floor Planning** and **Power Planning**.

- **Floor Planning**: The goal of floor planning is to organize the layout of the chip by partitioning the silicon area among different system blocks and placing the I/O pads. In chip-level floor planning, the designer divides the chip die into sections for various subsystems, while micro-level floor planning defines the dimensions of blocks, pin locations, and the arrangement of rows for standard cells.

- **Power Planning**: In this phase, the designer constructs the power network to distribute power efficiently across the entire circuit. Typically, multiple power supplies, such as VDD and GND, are used. The components are connected to the power supply through metal layers that form horizontal and vertical power strips. To minimize resistance, parallel structures are used, and higher metal layers are employed for power distribution because they are thicker and exhibit lower resistance. This helps to mitigate electromigration, a phenomenon where the movement of metal ions due to current can lead to circuit failure. Using upper metal layers reduces the impact of electromigration and ensures a more reliable power distribution network.

![Screenshot 2024-09-07 014723](https://github.com/user-attachments/assets/2a014c44-19b3-4e30-9a2d-e89fc50f19ad)

### Step 3: **Placement**

The placement process involves placing the gate-level netlist onto the predefined rows established during floor planning. Cells are aligned with specific sites, and the objective is to place them as close to each other as possible to minimize interconnect delay. Typically, placement is done in two steps: **Global Placement** and **Detailed Placement**.

1. **Global Placement**:
   - This is the initial stage of placement where cells are placed within the core area of the chip for the first time. The focus here is on optimizing the placement for factors like timing and congestion, while still maintaining a global perspective of the entire netlist.
   - Global Placement provides a rough placement solution, which may not satisfy all constraints at this stage. Its purpose is to get an overall layout that prioritizes reducing congestion and improving timing while preserving the general structure of the circuit.

2. **Detailed Placement**:
   - After global placement, detailed placement is performed to fine-tune the positions of cells. This step determines the exact placement, routing, and metal layers for each connection in the netlist.
   - The objectives of detailed placement include ensuring valid routing, minimizing the overall area, and meeting timing constraints. It also aims to minimize the number of vias (connections between metal layers), reduce power consumption, and ensure that the design remains within physical design rules.

![Screenshot 2024-09-07 014741](https://github.com/user-attachments/assets/055d6d4d-6e76-4ae4-bc8e-fc9b51d9cf0d)

### Step 4: **Clock Tree Synthesis (CTS)**

Before routing the signal connections, the clock signal must be routed to all sequential elements, such as flip-flops, registers, ADCs, DACs, etc. This process is called **Clock Tree Synthesis (CTS)**. In CTS, the goal is to distribute the clock signal evenly across the design while minimizing clock skew, which is the difference in the arrival times of the clock signal at various elements.

The clock network typically resembles a tree structure, where the clock source is the root, and the sequential elements (flip-flops, registers, etc.) are the leaves. This tree-like network ensures that the clock signal reaches all parts of the circuit.

Key considerations in clock tree synthesis:

- **Minimizing Clock Skew**: Clock skew should be minimized to ensure that all clocked elements receive the signal with as little variation as possible. Skew can cause timing violations that degrade the performance or functionality of the design.
  
- **Low-Skew Global Routing Resources**: To reduce skew, many modern devices provide specialized global routing resources optimized for clock signals. These low-skew routing resources ensure that the clock signal maintains its integrity and uniformity as it propagates through the circuit.

- **Clock Tree Structures**: Various types of clock tree structures can be used, depending on the design requirements. Common structures include:
  - **H-tree**: A balanced tree structure used to minimize clock skew by ensuring that the clock signal travels the same distance to all endpoints.
  - **X-tree**: Another structure used to balance the clock distribution, similar to the H-tree.

The clock tree should be synthesized in a way that minimizes skew while ensuring the clock signal reaches all sequential elements effectively.


![Screenshot 2024-09-07 014809](https://github.com/user-attachments/assets/cbbf8596-a15c-48ad-ae19-8efcb724c4ed)

### Step 5: **Routing**

Once the clock tree is routed, the next step is **signal routing**. Routing involves creating the physical connections between signal pins using metal layers. It determines the exact paths for interconnecting standard cells, macros, and I/O pins. This is done after **Clock Tree Synthesis (CTS)** and **optimization**.

In VLSI systems, there are two critical types of nets that require special attention during routing:

- **Clock Nets**: These are crucial for synchronizing the sequential elements of the design.
- **Power/Ground Nets**: These ensure stable power delivery to the entire circuit.

### Routing Process in VLSI:

- In the **sky130 PDK** (Process Design Kit), there are **6 routing layers**. The lowest layer is the **local interconnect layer**, typically made of titanium nitride. The other five layers are **aluminum layers**, used for higher-level routing.

- During routing, metal tracks form a grid structure, and the routing grids can be quite large. To manage this complexity, a **divide-and-conquer** approach is often used. This method splits the routing task into smaller, more manageable sections, making it easier to handle.

### Types of Routing:

1. **Global Routing**:
   - In this step, a rough routing path is generated for each net. It provides **routing guides** that define which regions of the chip each connection should pass through. However, it does not determine the exact metal layers or detailed wire paths.
  
2. **Detailed Routing**:
   - This step uses the global routing guides to implement the actual wiring. It assigns specific metal layers and detailed routes for each signal, ensuring that all design rules are met (such as spacing, width, and via placement).

The goal of routing is to minimize congestion, optimize performance, and ensure that signals are routed efficiently, with minimal interference between different metal layers.

![Screenshot 2024-09-07 014851](https://github.com/user-attachments/assets/444b085f-ed39-4be6-bb4a-c1fecdc0b6c7)

Step 6: Sign Off - After routing is complete, we'll create the final layout. This layout will then undergo two types of verification:

1. **Physical Verification**: This involves checking the design rules to ensure the final layout matches the intended design and adheres to all specifications.

2. **Timing Verification**: This involves performing Static Timing Analysis to make sure that the timing requirements of the design are met.

**Introduction to OpenLANE and Strive chipsets**
**OPENLANE** is an automated RTL to GDSII design flow that integrates various tools like OpenROAD, Yosys, Magic, Netgen, Fault, CVC SPEF-Extractor, CU-GR, Klayout, and several scripts for design exploration and optimization. It began as an open-source project aimed at enabling a true Open Source tape-out experiment.

**striVe** represents a family of fully open-source System-on-Chips (SoCs), which include open Process Design Kits (PDKs), open Electronic Design Automation (EDA) tools, and open Register Transfer Level (RTL) designs.
![Screenshot 2024-09-07 014911](https://github.com/user-attachments/assets/509f7703-9242-4986-827b-a4d41949826b)
The main goal of OPENLANE is to produce a clean GDSII with no human intervation (no-human-in-the-loop). here the meaning of clean is that:

No LVS violations

No DRC Violations

No timing Violations

OPENLANE is tuned for skyWter130nm open PDK. it can be used to harden Macros and chips.there is two mode of operation Autonomus : it is the push botton flow. with the push botton , it is a some time base design and due to this push botton, we get final GDSII

interactive : here we can run comamds and steps one by one.

It has large number of design examples(43 designs with their best configurations).
**Introduction to OpenLANE detailed ASIC design flow**


The **design exploration utility** is also used for continuous integration (CI) regression testing. We run OpenLANE on about 70 designs and compare the results to the best-known outcomes.

**Design for Test (DFT)** involves several processes: scan insertion, automatic test pattern generation, test pattern compaction, fault coverage analysis, and fault simulation. After these steps, physical implementation is carried out using the OpenROAD app. The physical implementation process includes:

1. **Floor/Power Planning**
2. **Inserting Decoupling Capacitors and Tap Cells**
3. **Global and Detailed Placement**
4. **Post-Placement Optimization**
5. **Clock Tree Synthesis (CTS)**
6. **Global and Detailed Routing**

Whenever the netlist is modified (e.g., by CTS or post-placement optimization), verification is necessary. LCE (yosys) is used to ensure the functionality remains unchanged after netlist modifications.

**Antenna Rule Violations** occur when metal wire segments act as antennas, collecting charges that can potentially damage transistor gates during fabrication.
![Screenshot 2024-09-07 015031](https://github.com/user-attachments/assets/78d48d77-2295-4032-a250-b67716f1f959)

**Familiarize Yourself with Open-Source EDA Tools:**
- **OpenLANE Directory Structure**: Understand the directory layout for effective navigation and utilization.

**Basic Linux Commands:**
- `cd`: Change directory to a specific folder.
- `ls`: List contents of the current directory.
- `pwd`: Display the present working directory.
- `mkdir`: Create a new directory.
- `command --help`: Show usage information for a command.
- `clear`: Clear the terminal screen.

**Sky130_fd_sc_hd PDK Details:**
- **"sky130"**: Process node or name.
- **"fd"**: Foundry (SkyWater Foundry).
- **"sc"**: Standard cell library files.
- **"hd"**: High-density variant.

The Sky130_fd_sc_hd variant includes various technology files like Verilog, SPICE, TechLEF, MagLEF, MAG, GDS, CDL, LIB, LEF, etc. TechLEF files provide layer information.
**Design Preparation Step:**

When starting with OpenLANE, you should use `flow.tcl` because, as the name suggests, it guides you through the design flow using the script. 

- **With Interactive Switch**: You can perform the design steps one by one, allowing you to control each stage of the process.
- **Without Interactive Switch**: OpenLANE will run the entire flow from RTL to GDSII automatically.

Once you start OpenLANE, you’ll notice that the prompt changes to reflect the new environment.
![Screenshot 2024-09-07 024615](https://github.com/user-attachments/assets/12c6ff4c-a6be-4343-a4bd-66e069c8fa0a)
Now we have to input all the packages which required to run the flow.
![image](https://github.com/user-attachments/assets/1aa905a2-9616-499f-89ac-64afe8bafcfb)

Now, here we are ready to execute the command.

Now, if we are going into the design folder in openlane, there are nearly 30-40 designs are already builted. Out of them we can open any of the design. for example, here we are opening the picorv32a.v design. In this design we can see many files are available. i.e., scr, config.tcl, etc. This config.tlc file contains every details about the design. for example, details about enrollment, clock period, clock period port etc.
Now, in openlane, we are going to run the synthesis, but before synthesis, we have to prepare design setup stage. for that command is  'prep -design picorv32a'

**Review Files After Design Preparation and Running Synthesis:**

After finishing the design preparation, follow these steps:

1. **Check the `picorv32a` Directory**: In this directory, a folder named `run` will be created, and inside it, you'll find a subfolder with today's date. This folder contains various subfolders required by OpenLANE.

2. **Inspect the `temp` Folder**: Inside the `temp` folder, locate the `merged.lef` file. This file, generated during the preparation phase, includes detailed information about wires, layers, and cells.

   - **Opening `merged.lef`**: By examining this file, you can review all the layout and layer information relevant to the design.
![image](https://github.com/user-attachments/assets/e876d8b3-30b0-45d6-8588-7cbaba2a5d95)


1. **Folder Structure Review**:
   - **Result Folder**: Remains empty until tasks are executed.
   - **Report Folder**: Contains folders related to synthesis, placement, floorplanning, CTS, routing, Magic, and LVS.

2. **Config File**:
   - **`config.tcl`**: This file, found in the same directory as the design folder, includes default parameters used during the run. If you make changes to the configuration (e.g., core utilization in floorplanning), the `config.tcl` file will update accordingly, allowing you to verify that your modifications are reflected in the execution.

3. **Running Synthesis**:
   - Use the command `run_synthesis` to start the synthesis process. This typically takes about 3-4 minutes to complete.

By following these steps, you can effectively manage and verify your design flow in OpenLANE.
![Screenshot 2024-09-07 030225](https://github.com/user-attachments/assets/7bd70062-291d-4c91-a117-28af54b68ef8)
![Screenshot 2024-09-07 030246](https://github.com/user-attachments/assets/585cf2dd-79a2-4524-8ac3-9f98db33bd6f)

**Steps to characterize synthesis results**
From the data of synthesis, total number of counter D_flip-flops is 1613. and the number of cells is 14876.
![Screenshot 2024-08-30 045620](https://github.com/user-attachments/assets/94be0f00-224d-414e-8e8c-9ece660c5dea)

After running the synthesis, the **flop ratio** is calculated as:

\[
\text{Flop Ratio} = \frac{\text{Number of Flip-Flops}}{\text{Number of Total Cells}}
\]

In your case, the **flop ratio** is **10.84%**.

Before running the synthesis, the **result folder** was empty. However, after running the synthesis, all the necessary mapping has been completed by **ABC (And-Inverter Graph-Based Synthesis)**, which performs technology mapping and optimizations during synthesis. This results in new data being populated in the result folder.

### Day 2 - Good Floor Planning Considerations

**Chip Floor Planning Considerations**:
- The primary goal of floor planning is to determine the core and die's width and height, optimizing space for the netlist, cells, and other design elements.
- Key factors include the **utilization factor** (how much area is used by standard cells) and the **aspect ratio** (ratio of width to height of the core).

#### Core and Die Dimensions:
- The **Core** refers to the area occupied by logic cells, while the **Die** includes the core along with the additional margins for pads and I/O.
  
#### Netlist Example:
Consider a netlist with two flip-flops and some combinational logic (like AND/OR gates). A **netlist** describes the connections between electronic components like logic gates and flip-flops.

#### Area Calculation:
- **Assumptions**:
  - Standard cell dimensions: **1 unit × 1 unit** (Area = 1 sq. unit)
  - Flip-flop dimensions: **1 sq. unit** (same as standard cell)

Now, using these dimensions, we can calculate the area of the core by adding up the space occupied by each element in the netlist.

- If your netlist contains:
  - 2 flip-flops: \(2 \times 1 \, \text{sq. units} = 2 \, \text{sq. units}\)
  - Assume the combinational logic (AND/OR gates) takes up additional space, say 3 sq. units.
  
The **total core area** would then be:

\[
\text{Total Core Area} = 2 \, \text{(flip-flops)} + 3 \, \text{(gates)} = 5 \, \text{sq. units}
\]

This area represents how much space the netlist occupies on the silicon wafer, excluding wire dimensions.

![Screenshot 2024-09-07 031151](https://github.com/user-attachments/assets/eb83fea0-e336-495b-9384-8638abc9b6e2)

Before that will remove all the wires and bring all the flip flops and logic gates in a single plate. So after combining them together width and length will be 2 Sq. units each and if we calculate the total area the it will be 4 Sq. units. So now we have the rough calculation of minimum area occupied by the netlist.
![Screenshot 2024-09-07 031303](https://github.com/user-attachments/assets/aa130ea0-46ab-4faf-b524-7d2259053ae9)

### What is the 'Core' and 'Die' Section of a Chip?

In chip design, we work with a **silicon wafer** where all the logic is implemented. The two key sections of a chip are the **Die** and the **Core**:

- **Die**: This is a small piece of semiconductor material on which the main circuit is fabricated. It includes both the core and peripheral regions. The die is the overall physical entity that houses all the circuits, and it’s the section cut from the larger wafer.

- **Core**: Inside the die, the core is the specific area where the fundamental logic of the design resides. This is where all the main computational logic, such as gates, flip-flops, and other essential design elements, are placed. The core focuses on functionality, while the die includes the core plus additional components like input/output (I/O) pads, power distribution, and margins for the package.

![Screenshot 2024-09-07 031504](https://github.com/user-attachments/assets/114b6c03-af1b-4eb2-8220-0be87e9f9544)

To place the logic inside the core, we assume that the netlist occupies the entire core area, meaning the **utilization factor** is 100%.

### Utilization Factor Calculation:
The formula for **Utilization Factor** is:

\[
\text{Utilization Factor} = \frac{\text{Area occupied by the netlist}}{\text{Total area of the core}}
\]

Given dimensions:
- **Area occupied by the netlist**: 4 sq. units
- **Total core area**: \( 2 \, \text{units} \times 2 \, \text{units} = 4 \, \text{sq. units} \)

\[
\text{Utilization Factor} = \frac{4 \, \text{sq. units}}{4 \, \text{sq. units}} = 1
\]

This means the core has utilized all available space with no remaining unused area.

### Aspect Ratio:
The formula for the **Aspect Ratio** is:

\[
\text{Aspect Ratio} = \frac{\text{Height of the core}}{\text{Width of the core}}
\]

Given:
- **Height**: 2 units
- **Width**: 2 units

\[
\text{Aspect Ratio} = \frac{2 \, \text{units}}{2 \, \text{units}} = 1
\]

An aspect ratio of **1** indicates that the core (and thus the chip) is **square-shaped**. If the aspect ratio were not 1, it would indicate a rectangular shape.

Let's take the new dimensions: **width = 4 units** and **height = 2 units**.

### Utilization Factor Calculation:
Given that the **area occupied by the netlist** is still 4 sq. units, and the new **total area of the core** is:

\[
\text{Total core area} = 4 \, \text{units} \times 2 \, \text{units} = 8 \, \text{sq. units}
\]

Using the formula:

\[
\text{Utilization Factor} = \frac{\text{Area occupied by netlist}}{\text{Total area of the core}} = \frac{4 \, \text{sq. units}}{8 \, \text{sq. units}} = 0.5
\]

This means the netlist occupies **50%** of the core area, leaving the rest unused.

### Aspect Ratio Calculation:
The **Aspect Ratio** is:

\[
\text{Aspect Ratio} = \frac{\text{Height}}{\text{Width}} = \frac{2 \, \text{units}}{4 \, \text{units}} = 0.5
\]

An aspect ratio of **0.5** indicates that the chip is **rectangular in shape**.

### Using the Leftover Area:
The **remaining 50%** of the core space can be used to place additional cells such as **buffers**, **decoupling capacitors**, or any other necessary components. This helps improve the performance and power distribution within the design.

![Screenshot 2024-09-07 031849](https://github.com/user-attachments/assets/4063cc62-0ada-44b3-bcf5-af33540dbe69)

Let's take another example with a **square chip** of dimensions **4 × 4 sq. units**.

### Utilization Factor Calculation:
- **Total core area** = \( 4 \, \text{units} \times 4 \, \text{units} = 16 \, \text{sq. units} \)
- Assuming the **area occupied by the netlist** is 4 sq. units:

\[
\text{Utilization Factor} = \frac{\text{Area occupied by netlist}}{\text{Total core area}} = \frac{4 \, \text{sq. units}}{16 \, \text{sq. units}} = 0.25
\]

This means only **25%** of the chip area is utilized by the netlist, leaving **75%** available for additional cells and routing layers.

### Aspect Ratio Calculation:
The **Aspect Ratio** is:

\[
\text{Aspect Ratio} = \frac{\text{Height}}{\text{Width}} = \frac{4 \, \text{units}}{4 \, \text{units}} = 1
\]

Since the aspect ratio is **1**, the chip is **square-shaped**.

### Leftover Area Usage:
With **75% of the area** free, this space can be used for:
- **Routing**, which involves connecting cells with metal layers.
- Additional cells like **buffers** or **decoupling capacitors** to improve signal integrity and power distribution.

This flexibility allows for more efficient designs, ensuring that the available space is effectively utilized.
![Screenshot 2024-09-07 032041](https://github.com/user-attachments/assets/3ad3b342-0ea3-48b5-8a24-f6e6c9600b4b)

### Defining Locations of Preplaced Cells:

Imagine we have a large combinational logic circuit with **N logic gates** that performs a certain function. To make it easier to manage, we can break this big circuit down into smaller sections. We will split the entire circuit into **two parts**, each containing a smaller number of gates. These two parts will be treated as separate blocks, and each block will be implemented on its own.

By defining specific locations for preplaced cells within these blocks, we can optimize their performance and simplify the design process.
![Screenshot 2024-09-07 032129](https://github.com/user-attachments/assets/1647f62a-6795-4f6c-883f-6e87825d8f8c)

In both the blocks lets extend the input output pins and now we will black box the boxes and detached them. After black boxing, the upper portion is invisible from the top or invisible to the one , who is looking into the main netlist. now will seperate them out as two different IP's or modules.
Advantage of doing this is we can reuse them multiple times after implimenting once only. Similary there are other IP's also available for eg. Memory, Clock-gating cell, Comporator, MUX all of these are part of the top level netlist.They recieve some signals and perform functions and deliver the outputs but the functionality of the cell is implemented only once.

The arrangement of these IP's in a chip is refferd as floorplanning.

These IP's have user-defined locations, and hence are placed in chip before automated placement and routing are called "pre-placed cells".

These cells are placed in such a way that, the placement and routing tool do not touch the location of the cell.
![Screenshot 2024-09-07 032513](https://github.com/user-attachments/assets/d5dadff7-dc44-40ef-9b94-c5fe7e4b3ec9)
### Decoupling Capacitors Surrounding Pre-placed Cells

In digital circuits, particularly in the blocks we've previously discussed, **decoupling capacitors** are used around pre-placed cells to stabilize the supply voltage during switching events.

#### Example: Consider a Circuit with an AND Gate
- When the AND gate switches its state (from 0 to 1 or 1 to 0), a certain amount of **switching current** is required to charge or discharge the small capacitance present in the circuit.
- This capacitance must be fully charged to represent logic 1 and fully discharged to represent logic 0.

Assume the capacitance is **0**. Now, components like **Rdd** (resistance) and **Ldd** (inductance) represent parasitic elements in the power supply lines. During a switching operation, the circuit demands a **peak current**.

#### Voltage Drop:
Due to the presence of **Rdd** and **Ldd**, there will be a **voltage drop** across these elements, meaning the voltage at **Node A** won’t be exactly **Vdd**; it will be **Vdd'** (slightly lower due to the drop). This can cause instability in the circuit’s operation.

#### Role of Decoupling Capacitors:
To prevent this voltage drop from affecting the circuit’s performance, **decoupling capacitors** are placed near the pre-placed cells. These capacitors store charge and release it during switching, ensuring that the voltage stays close to **Vdd** and minimizing any drops. This keeps the circuit stable during rapid switching events, reducing noise and improving overall performance.
![Screenshot 2024-09-07 032647](https://github.com/user-attachments/assets/c26288a0-71f6-40a6-b687-0ba6b6320581)
So, due to this if ideal logic 1 = 1 volt then here practically it can be less then 1 volt i.e., 0.97 volts (Vdd'). So, for any signal to be considered as Logic '0' and '1' in the NM low and NM high range. It is danger case.
![Screenshot 2024-09-07 032918](https://github.com/user-attachments/assets/459d359b-4401-45d0-b011-47ef2ddc7715)
To solve this problem,, we have to put De-coupling capacitor in parallel with the circuit. Every time the circuit switches, it draws current from Cd, whereas, the RL network is used to replenish the charge into Cd. And the amount of current needed for the circuit is supplied by the De- Coupling Capacitor.
![image](https://github.com/user-attachments/assets/0d53f891-21fd-450c-8090-b6aed1b4ebff)
In a chip, decoupling capacitors are strategically placed between different blocks (like **Block A**, **Block B**, and **Block C**) to ensure stable power supply during switching events. Here's how it works:

- **Decoupling capacitors** are located between the blocks, and their role is to maintain the power supply by providing the required charge during switching. This ensures that voltage drops due to parasitic elements like resistance (**Rdd**) and inductance (**Ldd**) do not impact the circuit's performance.

- In this setup, each block relies on these capacitors to supply the needed current during transitions, preventing any disruption in the voltage level. 

By placing these capacitors between the blocks, we make sure that the **local communication** between the blocks is stable and that the power supply remains consistent across the entire chip. This reduces noise and enhances performance.
![image](https://github.com/user-attachments/assets/6fbcf832-2f08-4888-97f5-90137d35a0ff)


### Power Planning and Voltage Stability

In chip design, power planning ensures that all parts of the circuit receive a stable power supply. Here's how it works in the context you described:

1. **Local Circuitry as a Black Box**:
   - Consider the local circuitry as a black box that can be replicated multiple times. This circuitry has logic at the boundaries and uses decoupling capacitors to handle local current demands.

2. **Signal Transmission**:
   - When a signal is sent from a driver to a load (e.g., transitioning from logic 0 to logic 1), it's crucial to maintain signal integrity along the driver-to-load line. This ensures that the load receives the correct signal without distortion.

3. **Power Supply Considerations**:
   - For a 16-bit bus, which must retain the same signal strength from the driver to the load, sufficient power must be supplied to the bus. 
   - If decoupling capacitors are not placed along the bus (which might be impractical), and the power supply is far from the bus, voltage drops can occur between the supply and the bus.

4. **Voltage Drop Issue**:
   - Because the power supply is distant, there will be inherent voltage drops along the power distribution network. This drop can lead to insufficient power being delivered to the bus, potentially causing signal integrity issues.

### Solutions and Considerations:

- **Reduce Distance**: Minimize the distance between the power supply and critical parts of the bus to reduce voltage drops.
- **Increase Power Distribution Efficiency**: Improve the power distribution network to minimize resistance and inductance along the paths.
- **Strategic Placement of Decoupling Capacitors**: Even if it's not feasible to place capacitors everywhere, placing them strategically along the bus or near critical components can help maintain voltage stability.

Effective power planning ensures that the entire chip operates reliably, despite the challenges posed by distance and the absence of decoupling capacitors in some areas.
![image](https://github.com/user-attachments/assets/cb371712-1823-4314-8c3d-813e96661309)
When we say one particular line of 16-bit bus is logic 1 it says that the capacitor is being charged to Vdd, and whenever we say logic 0 it says that the capacitor is discharged to ground.Let consider this 16 bit bus connected to inverter. So, all the capacitor are initially charged will get discharged and vice-versa due to inverter.
![image](https://github.com/user-attachments/assets/e0b0fbeb-d3fc-4795-8656-42b1df332638)

But the problem is occurs due to all capacitor is connected to the single ground. This will cause a bump in 'ground' tap point during discharging. That bump is called as Ground Bounce. If the size of the bump exceeds the noise margin levelit might enter into an undefined state and due to undefined state it can either go to logic 1 or logic 0. So here thing becomes unpredictable
![image](https://github.com/user-attachments/assets/0d0fdf69-7593-4a09-9fcb-61120b89784d)
Also , all capacitors which were'0' volts will have to charge to 'V'volts through single 'vdd'tap point. This will cause lowering of voltage at Vdd tap point. As long as this voltage drop is in noise margin level we are good enough but if it goes into an undefined region then things become unpredictable.
![image](https://github.com/user-attachments/assets/a3a25347-7fbf-482e-b0c4-cd4055e501ff)
The phenomenon we have seen was causing the lowering of the supply voltage,this problem occured because power has applied to one point only. The solution of the problem is use multiple power supply. So, every block will take charge from neartest power supply and similarly dump the charge to the nearer ground. this type of power supply is called mesh.
![image](https://github.com/user-attachments/assets/d47c4495-2c3a-41d0-af20-4eeb34a8799b)
And the power planning is shown below,
![image](https://github.com/user-attachments/assets/6f87864c-992a-4f8d-8dbc-9c7e6b94be35)


### Pin Placement and Logical Cell Placement

Let's consider a design that needs to be implemented with the following components:

1. **Circuit Details**:
   - **Circuit 1** is driven by **clk1** and has an input **Din1** and an output **Dout1**.
   - **Circuit 2** is driven by **clk2** and has an input **Din2** and an output **Dout2**.

2. **Preplaced Cells**:
   - **Blocka**: This preplaced cell takes **Din1** and **Din2** as inputs.
   - **Blockb**: This preplaced cell takes **clk1** and **clk2** as inputs and produces **ClkOut**.

3. **Ports**:
   - **Input Ports**: **Din1**, **Din2**, **Clk1**, **Clk2**
   - **Output Ports**: **Dout1**, **Dout2**, **ClkOut**

### Explanation:
- **Pin Placement**: Position the input and output pins to make sure they connect easily to their respective circuits and blocks.
- **Logical Cell Placement**: Place **Blocka** near **Din1** and **Din2**, and place **Blockb** close to **clk1** and **clk2**. This ensures that each block can efficiently connect to its inputs and outputs.
- **Avoid Blockages**: Make sure the placement of these cells doesn’t obstruct the routing of other signals or interfere with the design. 

This setup ensures efficient signal routing and clear connections between circuits and blocks.
![image](https://github.com/user-attachments/assets/edf079a8-811b-4196-91e7-1e77bce36bfc)
et's have one more design that needs to be implemented. this types of circuits are very much helpful to understand the timing analysis of inter clocks. now complete design becomes like given below which has 6 input ports and 5 output ports. The connectivity information between the gates is coded using VHDL/Verilog language and is called as 'Netlist'.
![image](https://github.com/user-attachments/assets/fd1954d6-fb0d-4ec4-aab2-0470b75b1c9c)
Let's put this netlist in the core which we have designed before and let's try to fill this empty area between core and die with the pin information. The frontend team who decides the netlist connectivity input and output and the backend team who done the pin placements. So according to the pin placements, we have to locate the preplaced blocks nearer to the inputs of the preplaced blocks.
![image](https://github.com/user-attachments/assets/49a7a3ce-b880-47c6-b62d-fb905b1f63a3)
### Pin Placement and Blockage Considerations

1. **Clock Pin Size**:
   - **Clock-in** and **clock-out** pins are larger than input and output pins. This is because clock signals are continuously distributed throughout the chip and need to travel quickly. A larger pin size ensures a lower resistance path, which allows for faster and more efficient signal transmission.

2. **Logical Cell Placement Blockage**:
   - The area around clock pins where cell placements are restricted is shown as blockages in the layout. This is because these areas must be kept clear to avoid interference with routing paths and ensure that cells can be placed without obstructing the essential signal lines.

3. **Floor Plan Preparation**:
   - With pin placement and blockages defined, the floor plan is ready for the **Placement** and **Routing** steps. This ensures that the design is well-organized and prepared for the next stages of the chip design process.


**Steps to run floorplan using OpenLANE**
Before run the floorplanning, we required some switches for the floorplanning. these we can get from the configuration from openlane.
![image](https://github.com/user-attachments/assets/a414ce5a-81cf-400b-b485-c5a5b414de22)
Here we can see that the core utilization ratio is 50% (bydefault) and aspect ratio is 1 (bydefault). similarly other information is also given. But it is not neccessory to take these values. we need to change these value as per the given requirments also.
![image](https://github.com/user-attachments/assets/3cbdc736-8e04-4241-9c3e-b9abc4a007e2)
Here, (FP_IO MODE) 1, 0 means pin positioning is random but it is on equal distance.

In the OpenLANE lower priority is given to system default (floorplanning.tcl), the next priority is given to config.tcl and then priority is given to PDK varient.tcl (sky130A_sky130_fd_sc_hd_congig.tcl).

Now we see, with this settings how floorplan run.
Here FP_PDN files are set the power distribution network. These switches are set in the floorplane stage bydefault in OpenLANE.
Here, (FP_IO MODE) 1, 0 means pin positioning is random but it is on equal distance.

In the OpenLANE lower priority is given to system default (floorplanning.tcl), the next priority is given to config.tcl and then priority is given to PDK varient.tcl (sky130A_sky130_fd_sc_hd_congig.tcl).

Now we see, with this settings how floorplan run.
### Reviewing Floorplan Files and Viewing the Floorplan

1. **Check the Config.tcl File**:
   - Inside the **run** folder, you’ll find a file named **config.tcl**. This file includes all the settings used in the design flow.
   - By opening **config.tcl**, you can see the various parameters that have been set for the current flow. These parameters determine how the design is processed and how the floorplan is created.

2. **Viewing the Floorplan**:
   - To view the floorplan, use the configuration details from **config.tcl**. These settings help in understanding how the cells and pins are arranged.
   - Utilize design tools like OpenROAD to generate and inspect the floorplan based on the configurations. This helps in ensuring that everything is placed correctly according to the design rules and specifications.
To watch how floorplane looks, we have to go in the results. in the result, one def( design exchange formate) file is available. if we open this file, we can see all information about die area (0 0) (660685 671405), unit distance in micron (1000). it means 1 micron means 1000 databased units. so 660685 and 671405 are databased units. and if we devide this by 1000 then we can get the dimensions of chips in micrometer.
so, the width of chip is 660.685 micrometer and height of the chip is 671.405 micrometer.

### Viewing the Actual Layout

To view the actual layout after running the flow, follow these steps:

1. **Open the Magic Tool**:
   - Use the following command to open the Magic tool with the appropriate technology file and design definition:

     ```bash
     magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech \
           lef read ../../tmp/merged.lef \
           def read picorv32a.floorplan.def
     ```

2. **Press Enter**:
   - After entering the command, press Enter. This will launch the Magic tool with the specified technology file and design layout.

3. **View the Layout**:
   - Once Magic opens, you’ll be able to see the layout of your design. You can inspect the placement of cells, routing, and overall design to ensure everything meets the specifications.

This process allows you to visualize and verify the layout generated from the design flow.
![config tcl in picorv32a](https://github.com/user-attachments/assets/dba98c89-f57d-4f5c-81cd-b90353b23278)
![after running floorplan checking file](https://github.com/user-attachments/assets/b592208d-d8e6-4c2e-93f7-05c41b18fdf3)
![commands results _floorpaln](https://github.com/user-attachments/assets/39c39149-4351-4cc4-adec-96839402a809)
![Screenshot 2024-08-31 123714](https://github.com/user-attachments/assets/e4c34fe1-bb58-430b-bf1e-b26dff930a09)
![magiclayout](https://github.com/user-attachments/assets/ae8aafe3-96ff-4d59-a5d7-3cebde9db61e)

**Review floorplan layout in Magic**
In the layout we can see that, input output pins are at equal distance.after selecting (To select object, first click on the object and then press 's' from keyboard. the object will hight lited. to zoom in the object, click on the object and then press 'z' and for zoom out press 'sft+z') one input pin, if we want to check the location or to know at on which layer it is available, we have to open tkcon window and type "what". it will shows all the details about that perticular pin.
so, it show that the pin is in the metal 3.similarly doing for the vertical pins, we find that this pin is at metal 2.
Along with the side rows,the Decap cells are arranged at the border of the side rows.here we can see that first standerd cells is for buffer 1. similarly other cells are for buffer 2, AND gate etc.
![metal layout](https://github.com/user-attachments/assets/279c4d02-7d74-4679-908d-43d0a0171da6)
![metal2](https://github.com/user-attachments/assets/7c9284aa-6b0d-47ed-b8cf-4dbc05077100)
![metal 3](https://github.com/user-attachments/assets/da31b135-2080-4a35-a575-3a9c73b31f94)
![subcell selected](https://github.com/user-attachments/assets/029463b3-5039-40ba-8169-9ae7b9d3551f)
### Library Building and Placement

**Netlist Binding and Initial Placement Design**

1. **Bind Netlist with Physical Cells**:
   - In the design process, the netlist defines the connectivity and functionality of gates and flip-flops abstractly. However, in physical design, these components need to be mapped to actual physical shapes with specific dimensions.
   - For example, a NOT gate might be represented as a triangular shape in design tools, but it is actually implemented as a rectangular box with specific width and height.
   - Similarly, AND gates, OR gates, and flip-flops are modeled as boxes with defined dimensions. This is because real-world components have physical sizes and shapes, even if they are represented abstractly in the netlist.

2. **Assign Physical Dimensions**:
   - Each component in the netlist (gates, flip-flops, etc.) is assigned physical dimensions based on its real-world counterpart.
   - These dimensions help determine how each component will be placed on the chip and ensure that the layout accurately reflects the physical design constraints.

This process ensures that the abstract design described by the netlist is accurately translated into a physical layout with appropriate dimensions for each component.
![image](https://github.com/user-attachments/assets/88257239-6d87-47b4-bb76-74a0c780c821)

**Understanding the Library**

1. **Library Concept**:
   - Think of a library as a collection of books, where each book represents a different type of gate, flip-flop, or block used in the design.
   - In this context, each "book" (or cell) in the library has a specific shape, size, and timing information.

2. **Types of Libraries**:
   - **Physical Library**: Contains information about the shape and size of each cell. This is akin to having the dimensions and layout details of each "book."
   - **Timing Library**: Contains delay information and other timing characteristics of each cell. This helps in understanding how fast each cell can operate.

3. **Cell Variants**:
   - Libraries often include various versions (or "flavors") of each cell. For instance, a standard cell might come in different sizes. Larger cells typically have lower resistance paths, allowing them to work faster and with less delay.

4. **Selecting Cells**:
   - Based on the timing requirements and available space in the floorplan, you can choose the appropriate cells from the library. For example, if speed is critical, you might select larger cells with lower resistance paths. If space is a constraint, you might choose smaller cells.

This approach ensures that the physical design can be optimized for both performance and space efficiency by leveraging the information and options provided in the library.
![image](https://github.com/user-attachments/assets/2fdefecf-bfe4-420f-afde-fd7c21ce395b)
### Placement

**Steps in the Placement Process**

1. **Preparation**:
   - **Netlist**: This provides the connectivity and functional details of the gates and flip-flops.
   - **Floorplan**: The layout that defines the overall area, input and output ports, and space available for placing components.
   - **Cell Dimensions**: Each gate and flip-flop has been assigned specific physical dimensions.

2. **Placement**:
   - **Physical View**: Convert the abstract representation of gates from the netlist into their physical shapes and sizes.
   - **Layout on Floorplan**: Place each cell onto the floorplan according to the provided dimensions and connectivity information.
   - **Connectivity**: Ensure that the connections between the cells match the netlist, respecting the defined physical layout and connectivity constraints.

3. **Execution**:
   - **Place Cells**: Position each gate and flip-flop on the floorplan based on the netlist’s connectivity and the cell sizes.
   - **Verify Placement**: Check that all cells are correctly placed and connected according to the design specifications and that there is no overlap or routing issues.

This process ensures that the design is physically implemented on the chip according to the specifications, enabling further steps like routing and optimization.
![image](https://github.com/user-attachments/assets/0600917c-f5a2-4d66-8d2e-4359e5e593e0)
Now, we have the floorplan where we have the preplaced cells from the previous slides, Plcement will make syre that the pre placed cells locations are not affected they are kept as it as and the second thing which will be taken care of that is no cell should be placed over the pre-placed cells. We need to place the physical view of the netlist onto the floorplan in such a fashion that logical connectivity should be maintained and that particular circuit should interact with their input and output ports to maintain the timing and the delay will be minimal.
![image](https://github.com/user-attachments/assets/848e15d2-fba9-4d19-b531-480bf6e57f5d)
Here first we will see the arrangement of the remaining parts from the netlist onto the floorplan.We have placed all the element in such manner that all elements are closed to it's input and output pins. But, the distance of FF1 of Stage 4 and Din4 is still far them others. By optimizing the placement, we can solve this problem.
![image](https://github.com/user-attachments/assets/08f63325-7d57-4a01-ac29-b5d7be636f8d)
### Optimize Placement Using Estimated Wire Length and Capacitance

**Optimizing Placement:**

1. **Estimate Capacitance and Wire Length**:
   - Before routing, estimate the capacitance and resistance based on the length of the wire connecting components. For example, consider the wire from `Din2` to `FF1`. A long wire results in high capacitance and resistance, which can affect the signal quality and timing.

2. **Signal Integrity**:
   - If the wire length is too long, the signal from `Din2` might not be reliably received by `FF1` due to the large distance. To ensure the signal reaches `FF1` correctly, intermediate steps can be added to maintain signal integrity.

3. **Use Repeaters**:
   - **Repeaters** (or buffers) are used as intermediate stages to regenerate and amplify the signal. They help in maintaining signal strength and quality over long distances by reconditioning the original signal.
   - Place repeaters at intervals along the wire to break down the long distance into manageable segments, ensuring the signal remains strong and clear.

4. **Area Consideration**:
   - While repeaters help in preserving signal integrity, they also consume additional area on the floorplan. The more repeaters used, the larger the area required.
   - Balance the need for signal integrity with the available space to optimize the floorplan effectively.

By carefully placing repeaters and managing the wire lengths, you can improve signal integrity while considering the trade-off with floorplan area.
![image](https://github.com/user-attachments/assets/ec427d8f-085b-4b15-a81c-dd68eb4b3e20)
In the stage 1, there is no need of any repeater to transmit the signal. But in stage 2, due to high distance, the lenth of wire is high and signal is not transmitted in perticular range. so we required repeater.
![image](https://github.com/user-attachments/assets/16dc0441-14f0-4778-9657-2482bd1c96d8)

**Final placement optimization**
As similar to stage 2, in Stage 3 also we required the buffer between gate2 and FF2.Stage 4 is bit tricky as compared to other stages.Now we have to check that, what we have done is correct or not. For that we need to do Timing analysis by considering the ideal clocks and according to the data of analysis, we will understand that, the placement is correct or not
![image](https://github.com/user-attachments/assets/fbb11fb9-607f-4ad7-89ab-025b27497f10)
![image](https://github.com/user-attachments/assets/267c3028-fa55-4b28-8a95-54cac8246d7c)
### Need for Libraries and Characterization

**IC Design Flow Overview**:

1. **Logic Synthesis**:
   - **Objective**: Convert RTL (Register Transfer Level) code into a hardware representation using gates.
   - **Output**: Arrangement of gates that implements the functionality described in RTL.

2. **Floorplanning**:
   - **Objective**: Define the size of the Core and Die based on the output from logic synthesis.
   - **Purpose**: Create a physical layout that accommodates all components.

3. **Placement**:
   - **Objective**: Place logic cells on the chip to optimize initial timing and layout.
   - **Purpose**: Ensure efficient arrangement of cells to improve performance.

4. **Clock Tree Synthesis (CTS)**:
   - **Objective**: Design a clock distribution network so that all clock signals reach their destinations simultaneously and with consistent timing.
   - **Purpose**: Ensure proper timing for all clocked elements.

5. **Routing**:
   - **Objective**: Connect cells according to their characterization and design requirements.
   - **Purpose**: Establish the electrical connections between components.

6. **Static Timing Analysis (STA)**:
   - **Objective**: Analyze timing characteristics such as setup time, hold time, and the maximum frequency the circuit can achieve.
   - **Purpose**: Verify the timing constraints are met for reliable operation.

**Role of Libraries and Characterization**:
- **Libraries**: Provide the physical and timing information for gates and cells used in the design. They include data on cell sizes, delays, and power consumption.
- **Characterization**: Involves measuring and defining the electrical and timing properties of cells to ensure accurate performance predictions throughout the design process.

In summary, libraries and characterization are crucial for defining cell properties and ensuring accurate performance analysis and optimization throughout the IC design flow.
### Congestion-Aware Placement Using RePlAce

Currently, our focus is on minimizing congestion rather than timing constraints. The goal is to reduce congestion in the layout.

Placement is carried out in two stages: **Global Placement** and **Detailed Placement**. During global placement, cell positions are adjusted without legalizing them, whereas detailed placement involves finalizing the positions to meet all design rules.

**Global Placement**: 
- This stage aims to minimize wire lengths and improve overall layout efficiency.
- Legalization is not performed here, so cells are placed with the primary goal of reducing wire congestion.

**Detailed Placement**:
- After global placement, detailed placement adjusts cell positions to ensure they comply with all design constraints and rules.

To view the placement, you can open the Magic file. This file will show the actual layout of the standard cells after placement has been completed. The Magic tool provides a visual representation of the cell arrangement, as shown below.
![placement design](https://github.com/user-attachments/assets/238dc48a-2911-4ef6-953d-d34ad29088d8)
If we zooom into this, we find the buffers, gates, flip flops in this.
![placement done subcell view](https://github.com/user-attachments/assets/2daa1245-daaf-4128-a235-671c9bc39aa4)

### Cell Design and Characterization Flows

**Inputs for Cell Design Flow**:

In the cell design flow, gates, flip-flops, and buffers are referred to as "standard cells." These standard cells are organized within a section called the "Library." The library contains various cells that perform the same functionality but come in different sizes. This allows designers to select cells based on their specific needs for functionality and physical dimensions.
![image](https://github.com/user-attachments/assets/cd964501-9ed7-4bc5-8953-36700259248e)
f you lokk into one of the inverter from the library the cell design flowis as follows

The inverter has to represented in form of the shape, drive strength, power charracteristic and so on. Here cell design flow is devided into three parts.

Inputs

Design steps

Outputs

1)Inputs:- Inputs required for cell design is PDKs, DRC and LVS rules SPICE models, library and user defined specs. In DRC& LVS rules tech file is provided which contains design rules and actual values. Rules can be converted in to code. SPICE MODEL tells about threshold voltage equation.
![image](https://github.com/user-attachments/assets/8dbdc60a-0342-40d1-9032-8d682832f128)

**Circuit design steps**
The seperation between the power rail and the ground rail defines the cell height. Cell width depends upon the timing and drive strength.

2)design steps:- Design involves three steps which are circuit design, layout design, characterization.

In circuit Design there are two steps.

First step is to implement the function itself and second step is to model the PMOS nad NMOS transistor in such a fashion in order to meet the libraray.

3)Outputs

The typical output what we get from the circuit design is CDL(circuit description language) file,GDSII,LEF,extracted spice netlist(.cir).
![image](https://github.com/user-attachments/assets/7e96c10f-3ab7-4960-bda0-965c1e540cee)
Layout design step
In Layout Design First step is to get the function implemented through the MOS transistor through a set of PMOS and NMOS transistor and the second step is to get the PMOS network graph and the nNMOS network graph out of the design that has been implemented.
![image](https://github.com/user-attachments/assets/6bc8f753-49ca-4be2-b92f-a42f9316f61a)
After getting the network graphs next step is to obtain the Euler's path. Eule's path is basically the path which is traced only once
![image](https://github.com/user-attachments/assets/a7062855-1e8f-48f5-bf5f-74476fe8c0c5)
Next step is to draw stick diagram based on the Euler's path. This stick diagram is derived out of the circuit diagram.
![image](https://github.com/user-attachments/assets/d573f21a-d980-4bb2-9e79-54de7ac9d4d2)
Next step is to convert this stick diagram into a typical Layout, into a proper layout and then get the proper rule we have discissed earlier. Once we get the particular layout then we have the cell width, cell length and all the specifications will be there like drain current, pin locations and so on.
![image](https://github.com/user-attachments/assets/7b90a779-9585-4d7d-9bcb-366ea1d08c91)

Next and Final step is to extract the parasatics of that particular layout and charaterise it in terms od timing. So before that the output of the layout design will be GDSll. Once you get the extracted spice netlist then we characterize it. Characterization helps in getting timing, noiseand power information

### Typical Characterization Flow

Here's a step-by-step guide to building the characterization flow based on the inputs:

1. **Read the Model**: Begin by importing the model that defines the cell's characteristics.
2. **Read the Extracted SPICE Netlist**: Import the SPICE netlist that describes the cell's electrical connections and components.
3. **Define/Recognize Buffer Behavior**: Identify and specify the behavior of the buffer or cell based on its functionality.
4. **Read Subcircuits**: Import and analyze the subcircuits, such as the inverter, which are integral to the cell's operation.
5. **Attach Power Supplies**: Connect the necessary power supplies to the circuit to ensure it operates correctly during simulation.
6. **Apply Stimulus**: Introduce the appropriate input signals or stimulus to the circuit to test its response.
7. **Provide Output Capacitance**: Specify the load capacitance that the cell will drive, which impacts its performance.
8. **Provide Simulation Command**: Finally, execute the simulation with the appropriate command:
   - For transient analysis: Use the `.tran` command.
   - For DC analysis: Use the `.dc` command.

This characterization flow helps in accurately modeling and testing the behavior of standard cells to ensure they meet design specifications.
![image](https://github.com/user-attachments/assets/de65f9fe-4730-421d-b008-4068a3c17462)
Next step is to feed in all this inputs from 1 to 8 in a form of a configuration file to the characterization software "GUNA" .

This software will generate power, noise and timing model.
![image](https://github.com/user-attachments/assets/7c65ca4b-f021-4767-a29e-a17d557698e5)
### General Timing Characterization Parameters: Timing Threshold Definitions

When working with timing characterization, understanding various threshold points of a waveform is crucial. These threshold points help in analyzing and defining the performance of the circuits. 

One important parameter is the **"Timing Threshold Definitions."** This involves understanding and defining specific points on a waveform that indicate how the circuit behaves under different conditions. For instance, consider the following example:

- **Slew_low_rise-thr**: This term represents a threshold value on the waveform that is typically close to 0. It is used to describe the point where the waveform begins to transition from low to high. The typical value for this threshold is around 20% of the maximum transition value, though it can vary and sometimes be 30% depending on the specific application or standard being followed.

These threshold points are essential for accurately characterizing and timing circuits, ensuring that they perform correctly within their intended specifications.
![image](https://github.com/user-attachments/assets/92c55772-50ca-4c27-ad13-2bdcf4400753)
![image](https://github.com/user-attachments/assets/53f59637-864b-4dff-9bfe-4295299cbbc4)
![image](https://github.com/user-attachments/assets/9811b5d8-2389-4ce3-ab09-1709d2aa4b35)
![image](https://github.com/user-attachments/assets/fabe124c-f3b9-488c-b7c9-3d1f6d36caf9)
Now, taking the waveform of input stimulus which is input of the first buffer and with that taking output of the first buffer.Similar as a slew, thresolds are for delay also available. for that same as slew, we have to take some rise and fall points from the waveforms. this tresolds are almost 50%.
![image](https://github.com/user-attachments/assets/dd821e8b-5eff-49e5-9ba0-c0d32585d724)
![image](https://github.com/user-attachments/assets/d9009ed0-5137-448c-b987-2b5321fcfeb3)
![image](https://github.com/user-attachments/assets/6a9fe528-5d5e-43e2-887a-7df56769afe7)
![image](https://github.com/user-attachments/assets/32540116-1598-4a5c-b370-a0ec2d3e9c70)
### Propagation Delay and Transition Time

To analyze circuit performance, key timing parameters such as propagation delay and transition time are calculated using waveform thresholds. Here’s how you can calculate these values:

1. **Propagation Delay**:
   - **Definition**: The propagation delay is the time it takes for a signal to propagate through a gate or circuit from the input to the output.
   - **Calculation**: To find the propagation delay, subtract the time when the input reaches a certain threshold from the time when the output reaches the corresponding threshold.
   - **Formula**: 
     \[
     \text{Propagation Delay} = \text{Time(out\_rise\_thr)} - \text{Time(in\_rise\_thr)}
     \]
   - **Example**: If the output rises to 50% of its final value at time \( t_{out} \) and the input rises to 50% of its final value at time \( t_{in} \), then:
     \[
     \text{Propagation Delay} = t_{out} - t_{in}
     \]

2. **Transition Time**:
   - **Definition**: Transition time refers to the duration it takes for a signal to transition between two states, such as from low to high or vice versa.
   - **Calculation**: This can be derived by analyzing the waveform to measure the time interval between specific threshold points.
   - **Example**: If we’re interested in the transition time to rise from 10% to 90% of the final value, you would calculate the time difference between these points.

These calculations help in understanding how quickly a circuit can respond to changes and how efficiently signals propagate through various stages. Accurate timing characterization is crucial for designing high-performance digital systems.
![image](https://github.com/user-attachments/assets/aba8d915-1b55-40c6-b445-b041997cf210)
In tLet's take another example where we have choosed threshold point correctly but still can get a negative delay. Because uotput comes before the input that's why we are getting negative delay here, which is not acceptedhe above example in_rise_thr and out_fall)thr was kept at 50%. But if the threshold ponit moves to the top the the output comes before the input and we see negative delay and negative delays are not accepted. So the reason behind having this negative delay is poor choice od threshold point so thr choice of the threshold point is really important.
Transition time= time(slew_high_rise_thr)- time(slew_low_rise_thr)

or

transition time = time(slew_high_fall_thr)- time(slew_low_fall_thr)

Let's say we have the waveform to understand the slew calculation.
![image](https://github.com/user-attachments/assets/a880bcc1-cf0f-4fc4-9a84-e06de65a754e)
![image](https://github.com/user-attachments/assets/d1e285e6-3a55-4539-b241-7ab5b9efa954)
To adjust pin locations in floorplanning, follow these steps:

1. **Check Current Configuration:** Identify the current pin placement mode by checking the configuration settings. Use the command:
   ```
   env(FP_IO_MODE)
   ```

2. **Modify Configuration:** Change the pin placement mode by updating the configuration setting. For example, if it’s currently set to `1`, change it to `2`:
   ```
   env(FP_IO_MODE) 2
   ```

3. **Run Floorplanning:** Execute the floorplanning process again to apply the new pin placement settings.

4. **Verify Changes:** After running the updated floorplanning, check the changes in pin locations using Magic Layout:
   ```
   magic -T /path/to/technology/file lef read /path/to/merged.lef def read /path/to/updated.floorplan.def
   ```

This will show you the updated layout with the new pin positions.o, here we can see that there are no pins in the upper half side. all pins are in the lower half of the core.
![placement design](https://github.com/user-attachments/assets/e507de53-44d8-4255-86a6-98cbab4c1072)
![placement done subcell view](https://github.com/user-attachments/assets/ae134937-159e-4e22-849b-8ec514a19d50)
![changing pin from floorplan file](https://github.com/user-attachments/assets/0f55c05a-0fac-4875-9a22-0b4ffc525c4b)
![pin config from 1 to 2](https://github.com/user-attachments/assets/591c1f04-12af-4ff7-b3a2-c8c29bfbec1d)
![run floorplan after 1 to 2 pin change config](https://github.com/user-attachments/assets/bb31fdbd-0821-4a6b-8020-eba3ae527e8f)
![pin_config_change](https://github.com/user-attachments/assets/fbdd315c-d5fc-4ee1-a604-3d324d65acac)

### SPICE Deck Creation for CMOS Inverter

**VTC - SPICE Simulations:**

To begin with, you need to create a SPICE deck, which serves as a detailed netlist outlining the connectivity and components of your circuit. This deck includes the inputs provided for simulation and specifies the points where outputs will be measured.

**Component Connectivity:**

In the SPICE deck, you must define how the substrate pin is connected. The substrate pin is crucial as it affects the threshold voltage of both PMOS and NMOS transistors. Properly defining this connection ensures accurate simulation of the transistor behavior.
![image](https://github.com/user-attachments/assets/2571848d-3446-4b12-a902-a8d10445958b)
Component values:- Values for the PMOS nad NMOS. We have taken the same size of both PMOS and NMOS.
![image](https://github.com/user-attachments/assets/9b71cf2d-299c-4774-a089-9a7ed2132bb4) 
dentify the nodes:- Node mean the points between which there is a component.These nodes are required to define the netlist.
![image](https://github.com/user-attachments/assets/cce25b9c-3b87-4251-b658-3d631030458a)
Name the nodes:- Now we wiil name these nodes as Vin, Vss, Vdd, out.
![image](https://github.com/user-attachments/assets/297422be-b519-4b5f-9f38-7102df1b000d)
Now we will start writing the SPICE deck. It's written like shown below

Drain- Gate- Source- Substrate

For M1 MOSFET drain is connected to out node, gate is connected to in node, PMOS transistor substrate and Source is connected to Vdd node.

For M2 MOSFET drain is connected to out node, gate is connected to in node, NMOS source and substrate are connected to 0.
![image](https://github.com/user-attachments/assets/aae29649-9c8d-4a3b-b299-4b10b102b34a)

**SPICE simulation lab for CMOS inverter**
Till now we have described the connectivity information about CMOS inverter now we will describe the other components connnectivity information like load capacitor, source. Let's seee the connectivity of output load capacitor.

It is connected between out and the node 0. And it's value is 10ff. Supply voltage(Vdd) which is connected between Vdd and node 0 and value of it is 2.5 , Similarly we have input voltage which is connected between Vin and node 0 and its value is 2.5.
![image](https://github.com/user-attachments/assets/18810a33-285e-4ea6-a3b1-33627e6767bb)
Now we have to give the simulation commands in which we are swiping the Vin from 0 to 2.5 with the stepsize of 0.05. Because we want Vout while changing the Vin.
![image](https://github.com/user-attachments/assets/48bc4892-b764-4b69-8a09-9309948e9d1f)
Final step is to model files. It has the complete description about NMOS and PMOS.
![image](https://github.com/user-attachments/assets/3b2e8558-e5e2-4e3d-80a3-4cfc6c667419)
Now we will do the SPICE simulation for the particular values. And will get the graph
Now, doing other simulation in which we change the PMOS width to 3 times of NMOS width. and after diong the simulation, we get the graph like this shown below
The difference between these two graphs is that in the second graph the transfer charactoristic is lies in the ecxact middle of the graph where in the first graph it is lies left from the middle of the graph.
![image](https://github.com/user-attachments/assets/87bf1ed1-f21e-40b5-a282-c5217c5f97a5)
![image](https://github.com/user-attachments/assets/2fe8777b-1cb6-405e-885e-3682aacdc6d6)
**Switching Threshold \( V_m \)**

The switching threshold \( V_m \) is a crucial parameter in evaluating the robustness of CMOS inverters. Despite variations in the width of NMOS and PMOS transistors, the waveform shape remains consistent. This means that CMOS technology is reliable and maintains its characteristic behavior across different transistor sizes. 

When the input voltage (\( V_{in} \)) is low, the output (\( V_{out} \)) is high, and vice versa. This consistent behavior across various CMOS devices highlights why CMOS logic is widely used in gate design.

The switching threshold \( V_m \) is defined as the point where \( V_{in} \) equals \( V_{out} \). This parameter indicates the voltage level at which the inverter switches states, demonstrating the inverter's robustness and reliability.
![image](https://github.com/user-attachments/assets/13d4d526-0c00-4ee1-8263-f296039b78c5)
n this figure, we can see that at Vm~0.9v, Vin=Vout. This point is very critical point for the CMOS because at this point there is chance that both PMOS and NMOS are turned on. If both are turned on then there are high chances of leakage current(Means current flow direcly from power to ground).

By comparing this both the graph we can understang the concept of switching thresold voltage.
![image](https://github.com/user-attachments/assets/72acffd9-f291-4b5e-991e-e4f9841080e8)
In the graph below we can identify that the PMOS and NMOS are in which region. The direction of current flowing is different for NMOS nad PMOS.
![image](https://github.com/user-attachments/assets/6ddb47be-9b2b-4d04-9279-318f6bcc741d)
Static and dynamic simulation of CMOS inverter
In Dynamic simulation we will know about the rise and fall delay of CMOS inverter and how does it varying with Vm. In this simulation everything else will remian same except the input which is provided will be a pulse and simulation command will be .tran

The graph Time vs Voltage will be plotted here from where we can calculate the rise and fall delay.
![image](https://github.com/user-attachments/assets/a98b93a7-d07c-4e0d-8dc0-1b0b3b98e0ec)
**Lab Steps to Git Clone `vsdstdcelldesign`**

1. **Copy the Clone Address**: Go to the repository page and copy the clone URL. This is typically found under the "Code" button.

2. **Open Terminal**: Open the terminal in your OpenLANE directory.

3. **Run Git Clone Command**: Paste the clone address into the terminal after the `git clone` command. For example:
   ```bash
   git clone <clone-address>
   ```

4. **Check the Directory**: After running the command, a new folder named `vsdstdcelldesign` will be created in your OpenLANE directory.

These steps will create a local copy of the `vsdstdcelldesign` repository in your OpenLANE environment.
now, if we open the openlane directory, we find the vsdstdcelldesing folder in the openlane directory.Now if we goe to the vsdstdcelldesign folder and open it, we get the .mag file,libs file etcnow, let's open the .mag file and see that which layers are used to build the inverter. But before opening the mag file, we need tech file. so we will copy this file from this given below address, And do copy by cp command to the location which is given below.Now, we can see that this file is copied in the vsdstdcelldesign folder..Now, here to see the layout in magic, we don't need to write the whole address because we copy the tech file here.Now, we can see the layout of CMOS inverter in the magic like this
![sky 130 A tech created](https://github.com/user-attachments/assets/b8b9a951-2ac9-4af3-af99-235a6352558a)
![git clone](https://github.com/user-attachments/assets/8e128b50-0d08-40c4-9167-a4fbd5f32b0f)
![opening stick layout](https://github.com/user-attachments/assets/9ba62e6e-c912-40d9-8417-caf761d6414a)
![stick layout](https://github.com/user-attachments/assets/637c1d9c-db06-4df3-98d8-5253dc0a1a44)

**Inception of layout ̂A CMOS faabrication process
Create Active regions**
1) selecting a substrate:- we have a p-type silicon substrate having high resistivity(5-50ohm) well dopped, and orintation(100).

2) creating active region for transistor:- Region where you see PMOS and NMOS. On p-type substrate we are going to create some small pockets which will be called as active region and in these pockets we are going to create PMOS and NMOS transistor. Will cretae isolation between each and every pockets.

We create the isolation layer by depositing the Sio2 layer (~40nm) on the substrate. Now, we are depositing the Si3N4 layer (~80 nm) on the Sio2 layer.
![image](https://github.com/user-attachments/assets/30705294-e133-462d-9583-ed22b5708d13)
Before creating the pocket identify the region where we need to crete the pocket. Now will deposite a layer of photoresist(~1um) on which we will create some mask1 using UV light
![image](https://github.com/user-attachments/assets/00405148-5fd2-48e2-80a1-44f9c29e6d07)
Unwanted area has been exposed using UV light. And we get pattern the exposed area is getting washed away.
In the next step mask will be removed and doing etching of Si3N4 layer on the exposed area.
![image](https://github.com/user-attachments/assets/9b40b7b3-5c10-449b-9b81-2f62736b87bd)
Now, next step is to remove photoresist by chamical reaction, because now to Si3N4 layer itslef behaves like good protecting layer for Sio2 layer. now,We will place it in the oxidation furnace. if we do LOCOS (local oxidation of silicon) process, the exposed sio2 part will grow and bird break also form. This grown sio2 will provide the perfect isolation between two PMOS and NMOS. This is how we protect two transistor communicating with each other.
![image](https://github.com/user-attachments/assets/61f774a8-3110-433b-a4df-40e65b7061ab)
Formation of N-well and P-well
3) N-well and P-well formation:- we can not form P-well and N-well at a same time. we have to protect a region while forming one of the region by photoresist. And then using mask 2 and UV light, we will do patterning of photoresist to form P-well.
![image](https://github.com/user-attachments/assets/54981046-9cc7-4b89-a08e-61d073792909)
Now, the area where we want to form the P-well is exposed. now we remove the mask and by applying the ion implantaton method (~200kev)to form P-well using Boron. But still it is P implant. After performing the high temparature anneling, it will become P-well.
![image](https://github.com/user-attachments/assets/799dc96b-c724-4282-87b4-8850d9fe30eb)
We wiil do a similar process to form N-well by using mask 3 and using Phosphorus ions
![image](https://github.com/user-attachments/assets/cce211e2-08b9-4d78-97c8-9353f367f2de)
Till now depth of wells are not define. so, by putting into the high temparature furnace (drive-in diffusion), we will define the depth of wells.

![image](https://github.com/user-attachments/assets/95367890-3bc8-4571-afd8-8ed63ab3e68c)

**Formation of gate terminal**
4)Gate formation:- Gate terminal is the most important terminal of the PMOS and NMOS because from the gate terminal only we can control the thresold voltage. doping concentration and oxide capacitance will control the thresold voltage.so, first we are maintain the doping concentration here. for that we use mask 4 and again doing the ion implantation of boron ion at lower energy (~60kev).
![image](https://github.com/user-attachments/assets/63c7a710-a9f5-450a-879c-df76507e6a08)
same process we will repeat for N-well also by using mask 5 and Arsenic ion.
![image](https://github.com/user-attachments/assets/673b8439-4fda-4f59-9fb2-0fea943c5585)
Next step is that we have to fix the oxide layer. but before that we have to remove the oxide layer because this layer is got dammeged because of the privious processes. so,first we remove the layer using HF solution and again re-grown the high quality oxide layer with same thickness.

The final step is the deposition of polysilicon layer over oxide layer with more impurities for low resistance gate terminal.Then etched out this polysilicon layer by using mask 6 and photoresist.
after etching, remove the photoresist and gate terminal looks like,
![image](https://github.com/user-attachments/assets/c16e9c04-b2ac-4e5d-adc7-5944e026b155)

**Lightly doped drain (LDD) formation**
5) LDD formation:- Here, we actully want P+,P-,N doping profile in the PMOS and N+,N-,P doping profile for NMOS. Reason for that is

Hot electron effect

short channel effect

For the formation of LDD, we again do ion implantation in P-well by using mask 7 and here we use phosphoros as a ion for light doping.
![image](https://github.com/user-attachments/assets/a31fa1b5-15a5-4bf3-b208-a7a3b5f5465d)
Same process we will repeat for N-well. there we use mask 8 and BOron Ion.
![image](https://github.com/user-attachments/assets/512c6805-6bdf-44f4-bd5a-35cd273ae299)
Now, by creating the spacers, we can protect the actual structre remain constant of P-implantt and N-implant. For that we deposite a thick Sio2 or Si3N4 layer over the gate tereminal.
![image](https://github.com/user-attachments/assets/a5f81362-0fe1-4892-a66f-e63dcf075390)
Now, we do Plasma anisotropic etching. By that side-wall spacers are formed.
![image](https://github.com/user-attachments/assets/1f95c24f-4a38-487d-9a14-c1514be10344)

**Source Ã�Â� drain formation**
6)source-drain formation

Next step is deposite the very thin screen oxide layer to avoid the effect of channeling.
![image](https://github.com/user-attachments/assets/14ca5bb7-08b3-4df4-ab5e-14f9e05eaab8)
Now to form the drain and source, again we do the ion implantation of arsenic at 75kev to create the N+ implant by using mask 9 in the P-well to form PMOS
![image](https://github.com/user-attachments/assets/a1c671f6-048d-4ae4-8a38-806542012e79)
Same process we will repeat for NMOS by using the mask 10 and boron ion in the N-well at 50kev to creat P- implant.
Now we put this Half made CMOS into the high temparature (1000 degree)anneling. So P+ implant and N+ implant now become the source and drain.
![image](https://github.com/user-attachments/assets/d4a0bd2b-01e1-4680-9d61-e81a495cea8e)

**Local interconnect formation**
7)steps tp form contacts and local interconnects:- First step is remove the thin screen oxide layer by etching. Then deposite the titanium (Ti) using sputtering. here Ti is used because Ti has very low resistivity.
Next step is to create the reaction between Ti layer and source, gate, drain of CMOS. For that wafer is heated at about 650-700 degree temparature in N2 ambient for about 60 seconds. and after reaction, we can see the titanium siliside over the wafer. One more reaction is heppend there between Ti and N. and it results the TIN which is used for local communication.
Now by using mask 11 and photoresist, we will etched out the TIN and make perticular contacts. TIN is etched out by using RCA cleaning.
Now, local interconnects are formed after etching and removing the photoresist.
![image](https://github.com/user-attachments/assets/f41235b9-8b28-43a8-9936-0c8d786d7436)
![image](https://github.com/user-attachments/assets/ea2ef46d-77d2-4891-8829-8a994fb84e44)

**Higher level metal formation**
8)Higher level metal formation:- These steps are very semilar like previous steps. First thing that we are noticing is that the surface is non planner. it is not good to use this type of non planner serface for matel interconnects because of the problems regarding the metal disconinuty. so, we have to plannerize the surface by depositing the thick layer of sio2 with some impurity to make less resistive layer. and then we used CMP (chemical mechanical polishing) technique to plannerise the surface.
Now using mask 12 and photorsist we etched the sio2 layer to diposite the metal in it.Now remove the photoresist and seposite the thin later of TIN (~10nm) over the wafer. Because TiN is act as very good adession layer for sio2 and also act as a barrier between bottom layer and top layer of metal interconnects.Next step is to deposite the blanket tungsten (W) layer over the wafer. and then do the CMP here to plannerize the surfacehis W is act as a contact holes and this holes needs to connect to the Higher metal layer. so we will deposite the Al (aluminium) layer.Then by using the mask 13 and photoresist, we etched the W layer out to form the contact at perticular place by Plasma etching.
This is our first level of metal interconnets. now we again do the same process as above to deposite the second level of metal interconnect by using mask 14 for etched out the sio2 and using mask 15 for etched out Al leyer.
.And finally our CMOS is looks like this after the fabrication.
![image](https://github.com/user-attachments/assets/9f9a6791-e009-476a-9403-b7b53f627faf)

**Lab introduction to Sky130 basic layers layout and LEF using inverter**
In the Sky130 process, each color represents a different layer in the layout:

- **Local Interconnect**: Shown in blue-purple.
- **Metal 1**: Indicated by light purple.
- **Metal 2**: Displayed in pink.
- **N-Well**: Represented by a solid dashed line.
- **N-Diffusion**: Shown in green.
- **Polysilicon Gate**: Highlighted in red.
- **P-Diffusion**: Displayed in brown.

In the Tkcon window, you can see the selected area for NMOS devices. Similarly, you can verify the PMOS devices. This allows you to check whether the CMOS layout is functioning correctly.
similarly we will check for the output terminal also.(by double pressing "S" to select the entire thing at output Y).
o, we can see that "Y" is attached to locali in cell def sky130_inv.

we can check the source of the PMOS is connected to the ground or not. and similarly we can check it for NMOS also.
![stick layout](https://github.com/user-attachments/assets/e09e25c5-4eae-4bca-baee-67d796109ba5)
![showing inverter  pmos region](https://github.com/user-attachments/assets/7e996440-65f9-430a-acf3-222b0ba5e4b5)
**Lab steps to create std cell layout and extract spice netlist**
To extract the file from here, we have to write the command in tckon window. and the comand is extract all Now let's go to this location from the terminal. it is exctracted.
we will use this .ext file to create the spice file to be use with our ngspice tool. for that we have apply the command ext2spice cthresh 0 rthresh 0. this will not create anything new. now again we have to type ext2spice command in tckon window.
so, now we are checking the location and at there spice file has been created.
![extracting inverter](https://github.com/user-attachments/assets/76a2a32f-bb5f-43f0-b45b-ed1e44478b00)

![ext2spice](https://github.com/user-attachments/assets/94b4d3cd-f0ff-4850-b32c-ce8c7a44d309)

![sky 130 inv spice](https://github.com/user-attachments/assets/7dd8ca52-cb7c-4a96-99f7-562e147f2de1)
![spice extraction](https://github.com/user-attachments/assets/5269c4bd-a3b6-4c78-a29d-da50d6e74189)

**Sky130 Tech File Labs
Lab steps to create final SPICE deck using Sky130 tech**
here, we can see the all details about the connectivity of the NMOS and PMOS and about the power supply also.

X0 is NMOS and X1 is PMOS and both's connectivity is shown as GATE DRAIN SUBSTATE SOURCE
Now we have to include the PMOS and NMOS lib files. it is inside the libs folder in the vsdstdcellsdesign folder.
so, now we include this file in the terminal by .include ./libs/pshort.lib and .include ./libs/nshort.lib command.

And then set the supply voltage "VDD" to 3.3v by VDD VPWR 0 3.3V command. and similarly set the value of VSS also.

Now, we need to specify the input files. by Va A VGND PULSE(0V 3.3V 0 0.1ns 2ns 4ns).

Also add the command for the analysis like, .tran 1n 20n, .control , run,.endc,.end.
![spice extraction](https://github.com/user-attachments/assets/f51c2cf0-cb0e-423b-b20f-412248e572ec)
![Screenshot 2024-09-02 105806](https://github.com/user-attachments/assets/8e945129-3f94-4e86-9396-f53e3f5a6acd)
![image](https://github.com/user-attachments/assets/13bb06f3-1bf0-4608-b7cf-335c1bb9e3cd)
Now, ploting the graph here by command, plot y vs time a.
![image](https://github.com/user-attachments/assets/23e779e9-23fd-4cc3-8450-84308bf23ecd)
NOw if we increase the C3 value from 0.024ff to 2ff the graph will look like this, graph become more smoother.
![image](https://github.com/user-attachments/assets/ab0212b5-45a9-4500-bd08-79674faf9229)

**Lab steps to characterize inverter using sky130 model files**
Here, we have to find value of 4 parameters.

rise time
it is time taken to the output waveform to 20% value to 80% value.
so, rise time= (2.2489 - 2.1819)e-09 = 66.92 psec.
fall time
it is the time take by output for transition from 80% to 20%.
so, rise time= (4.09512 - 4.05264)e-09 = 42.51 psec.
propagation delay
it is the time difference between the 50% of input and 50% of the output.
so, propogation delay =(2.2106 - 2.15012)e-09 = 60.48 psec.
cell fall delay
it is time for output falling to 50% and input is rising to 50%

so, cell fall delay =(4.07735 - 4.04988)e-09 = 27.47 psec.

We have successfully characterized our inverter. Our next objective is to create a lef file using the layout and we will plugin this lef file in the picorv32a core

**Lab introduction to Magic tool options and DRC rules**
To know more about the Magic DRC we can go to the website:- http://opencircuitdesign.com/magic/Technologyfiles/TheMagicTechnologyFileManual/DrcSection

Link to Google_Skywaters Design Rules: - https://skywater-pdk.readthedocs.io/en/main/rules/periphery.html

For reference , we can use the github repo of Google-Skywater: - https://github.com/google/skywater-pdk
Here's a step-by-step guide for downloading and setting up the lab files for DRC corrections using the Sky130 PDK:

1. **Navigate to the Home Directory**:
   ```bash
   cd ~
   ```

2. **Download the Lab Files**:
   ```bash
   wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz
   ```

3. **Extract the Downloaded File**:
   ```bash
   tar xfz drc_tests.tgz
   ```

4. **Navigate to the Extracted Lab Folder**:
   ```bash
   cd drc_tests
   ```

5. **List All Directories**:
   ```bash
   ls -al
   ```

6. **View the .magicrc File**:
   ```bash
   gvim .magicrc
   ```
   This file is the startup script for Magic and specifies where to find the technology file. You can make changes to this file if necessary.

7. **Start the Magic Tool with Better Graphics**:
   ```bash
   magic -d XR &
   ```
This setup will help you get started with the lab exercises for DRC corrections using the Sky130 PDK.
Content of .magicrc file by using command vi .magicrc
![drc_test](https://github.com/user-attachments/assets/bbded307-0e04-486b-870d-caf1c1094eaa)
![magic_crc](https://github.com/user-attachments/assets/661ef936-0eea-4934-93d0-59ca59501897)
![content of magicrc file](https://github.com/user-attachments/assets/459eb6ac-5ab2-4205-8527-da46e107ab76)

**Here’s how to use Magic and check DRC for Sky130 tech-rules:**

1. **Open Magic with Enhanced Graphics**:
   ```bash
   magic -d XR
   ```

2. **Load the Layout File**:
   - Go to the **File** menu in Magic and select **Open**.
   - Open the `met3.mag` file.

3. **Explore DRC Values**:
   - You will see different layouts with various DRC (Design Rule Check) values displayed as rule numbers. The rule numbers can be referenced from the Google-Skywater documentation.

4. **Check DRC in Selected Layout Area**:
   - In the **tkcon** window, select a blank area in the layout.
   - Hover the mouse pointer over the metal3 contact icon.
   - Press the `p` key to enter the `tkcon` command mode.
   - Type `pek` and press Enter in the **tkcon** window.
   - Execute the command `cif see VIA2` in the **tkcon** window.

5. **View Results**:
   - You will see a series of black squares appearing in the selected area, representing the VIA2 layers. 

This process helps in visualizing and verifying the design rules and layout in Magic.
![met3 mag file](https://github.com/user-attachments/assets/9f2e853f-10b2-4001-8daf-107ae2e552d1)
![poly rules](https://github.com/user-attachments/assets/b55b1430-dfe5-4a83-81ad-9abd9197da97)
![drc why metal 3](https://github.com/user-attachments/assets/b116cbc1-5a8d-4a0d-aaa4-c4e39ecd5057)
![image](https://github.com/user-attachments/assets/8c3b2db7-7bb2-439c-ac4e-4d802529b4b2)

**LAB To fix the `poly.9` error in the Sky130 tech-file using Magic, follow these steps:**

1. **Open the `poly.mag` File**:
   - Start Magic with enhanced graphics:
     ```bash
     magic -d XR
     ```
   - In the **tkcon** terminal, load the `poly.mag` file:
     ```bash
     load poly.mag
     ```

2. **Review the `poly.9` Rule**:
   - Check the specific rule `poly.9` on the Skywater documentation website or relevant sources.

3. **Edit the `sky130A.tech` File**:
   - Navigate to the `drc_tests` directory where `sky130A.tech` is located.
   - Open `sky130A.tech` with a text editor (e.g., `vim` or `nano`):
     ```bash
     vim sky130A.tech
     ```
   - Search for `poly.9` within the file. It will be listed under both the `POLY` and `uhrpoly` sections.
   - Correct the rules as necessary based on the documentation.

4. **Save and Close the File**:
   - Save the changes and exit the text editor.

5. **Reload the Technology File in Magic**:
   - In the **tkcon** terminal, reload the updated tech file:
     ```bash
     tech load sky130A.tech
     ```

6. **Run DRC Check**:
   - Execute the DRC check to verify if the `poly.9` error has been resolved:
     ```bash
     drc check
     ```

By following these steps, you should be able to address and fix the `poly.9` error in the Sky130 tech-file.
![poly mag](https://github.com/user-attachments/assets/e9dac824-be5a-45f2-97e9-a0c7a21f3c7b)
![poly 9 rule](https://github.com/user-attachments/assets/92f3bf45-7903-4390-85b8-88832c2c4432)
![very correc1](https://github.com/user-attachments/assets/1bafb5b5-d86d-4b34-9925-9ff781952367)
![very correct 2](https://github.com/user-attachments/assets/868fe172-99d8-44af-af0e-8da8b5c5b21e)
![very correct tech](https://github.com/user-attachments/assets/8e0eb8d1-4bc4-4749-8b59-ff639719fecd)

**Lab to implement poly resistor spacing and address any related issues in the `sky130A.tech` file, follow these steps:**

1. **Open Magic Tool**:
   - Start Magic with enhanced graphics:
     ```bash
     magic -d XR
     ```
   - Load the `poly.mag` file in Magic:
     ```bash
     load poly.mag
     ```

2. **Check Existing DRC Errors**:
   - Find and review the `poly.9` rule by examining the layout in the Magic window.
   - To locate errors, select the problematic area in the Magic window.

3. **Edit the `sky130A.tech` File**:
   - Open the `sky130A.tech` file located in the `drc_tests` directory using a text editor:
     ```bash
     vim sky130A.tech
     ```
   - Locate the section related to poly resistor spacing. Update the file to correctly define the spacing between poly resistors and adjacent structures such as diffusion regions and taps.
   - Save your changes and close the text editor.

4. **Reload the Technology File**:
   - In the **tkcon** terminal within Magic, reload the updated tech file:
     ```bash
     tech load sky130A.tech
     ```

5. **Check for Errors**:
   - Run a DRC check to identify any errors:
     ```bash
     drc check
     ```
   - For a detailed description of any errors, select the area with the error in the Magic window and run:
     ```bash
     drc why
     ```
   - This command will provide a description of why the DRC error occurred, helping you to understand and fix the issues.

By following these steps, you will be able to implement correct poly resistor spacing and address any associated DRC errors in your layout.
![image](https://github.com/user-attachments/assets/1b34e75e-28b2-4abb-b8b4-baac58bb9a06)
![image](https://github.com/user-attachments/assets/80acadfe-2f54-4ea3-9bf2-605936bd3b4a)
![image](https://github.com/user-attachments/assets/9fa62a1b-78cf-4c47-b405-0b50b029cae3)
**LABTo address the DRC error related to `nwell.6` and understand it as a geometrical construct,** follow these steps:

1. **Open the Magic Tool**:
   - Start Magic with enhanced graphics:
     ```bash
     magic -d XR
     ```

2. **Load and Examine the Layout**:
   - Open the `nwell.mag` file in Magic:
     ```bash
     load nwell.mag
     ```
   - In the layout:
     - **Deep nwell** is shown in yellow stripes.
     - **Nwell** is shown in a dotted green pattern.

3. **Identify the DRC Error**:
   - Look for areas where the yellow stripes (deep nwell) and dotted green (nwell) are improperly configured or missing. This visual representation helps in locating the specific region where the rule `nwell.6` fails.

4. **Check the Error in the Tech File**:
   - Open the `sky130A.tech` file using a text editor:
     ```bash
     vim sky130A.tech
     ```
   - Search for the `nwell.6` rule:
     - Look for any missing or incorrect rules that could be contributing to the error.
   - Make the necessary changes to correct the rules based on the observations from the Magic tool.

5. **Save and Reload the Tech File**:
   - Save your changes and close the text editor.
   - Reload the updated tech file in Magic:
     ```bash
     tech load sky130A.tech
     ```

6. **Run DRC Check**:
   - Execute the following commands to perform a detailed DRC check:
     ```bash
     drc style drc(full)
     drc check
     ```
   - These commands will help you identify any remaining or new DRC errors and provide insights into geometrical issues related to `nwell.6`.

7. **Review and Fix Errors**:
   - Analyze the results of the DRC check. If any errors persist, use the information to adjust the layout or tech rules accordingly.

By completing these steps, you will address the `nwell.6` error and ensure that the DRC rules are correctly implemented in your design.
![nwell changes](https://github.com/user-attachments/assets/911b3df6-6aaa-45fc-a360-b2ad9b1a055f)
![bloat all](https://github.com/user-attachments/assets/62db3906-9c88-40bd-a608-92ec48273873)
![nwell](https://github.com/user-attachments/assets/1980d43c-8db6-4921-abeb-105c1e326801)
![nwell 6](https://github.com/user-attachments/assets/1e95d9a5-ea3d-4fe6-be2d-cdc6ecadc229)

**Lab challenge to find missing or incorrect rules and fix them**
Now we will open the magic tool and execute the commands 'drc style drc(full)' and 'drc check'.
![image](https://github.com/user-attachments/assets/0a7e9f64-a394-4c34-a2d5-d3dff08a85a8)

**LabTo convert grid information to track information and integrate it into your design flow**, follow these steps:

1. **Extract .lef File from .mag File**:
   - Use Magic to export the LEF file from your layout:
     ```bash
     magic -d XR
     ```
   - Open your layout file in Magic:
     ```bash
     load your_layout_file.mag
     ```
   - Export the LEF file:
     ```bash
     write_lef your_layout_file.lef
     ```

2. **Understand Standard Cell Guidelines**:
   - **Ports Placement**: Ensure that the input and output ports of your standard cells are aligned with the intersection of vertical and horizontal tracks.
   - **Cell Dimensions**: The width of the standard cell should be an odd multiple of the track pitch, and the height should be an odd multiple of the vertical track pitch.

3. **Check Track Information**:
   - Locate the track information file in your PDK directory:
     ```bash
     cat pdk/sky130/libs.tech/openlane/sky130_fd_sc_hd/track.info
     ```
   - Review the contents to understand the track pitch and other relevant details.

4. **Ensure Compliance**:
   - Verify that your standard cells comply with the guidelines by checking their dimensions and port placements against the track information provided in `track.info`.

By following these steps, you can ensure that your cell designs align with the track grid and are ready for integration into your design flow.
To convert the grid information into track information for ensuring proper alignment in the layout, follow these steps:

1. **Open the Track File**: Start by opening the track file located at `pdk/sky130/libs.tech/openlane/sky130_fd_sc_hd/track.info`. This file contains information about the track spacing and layout for different metal layers.

2. **Open Tkcon Window**: Launch the Tkcon window in Magic by using the command `magic -d XR`.

3. **Use the Help Grid Command**: In the Tkcon window, type the command `help grid` to get detailed information on how to convert grid data into track information.

4. **Convert Grid to Tracks**: Based on the information from the help command, apply the necessary conversions to align ports on the intersection of the tracks. This involves ensuring that the ports are placed on the specified grid points that match the track intersections for layers like li1, metal 1, and metal 2.

5. **Verify Layout**: After conversion, verify that the ports are correctly placed at the intersections of the tracks as per the specifications.

This process ensures that the layout adheres to the design rules for metal layers and that the ports are correctly aligned for routing.
Now we can see that, the ports has been placed at the intersection of the tracks. But between the boundaries, 3 boxes are covered. so our second requirment also satisfies here.

Lab steps to convert magic layout to std cell LEF
Now, we will need to decide on the port name and its values. we can set the values for different ports, and for the power and ground port, we will need to make changes in the 'attach to layer' as Metal1.
After these parameters are set once, we are ready to extract the lef file from the mag
Now, we open this file in the magic by the command

magic -T sky130A.tech sky130_vsdinv.mag &

To extract the lef file we have to write the command in the tckon window as given below,

lef write

so it will create a lef file and we can check it in the vsdstdcellsdesign folder by using command ls -ltr.
To include a new cell in the synthesis flow and ensure it is properly integrated with your design, follow these steps:

1. **Move the .lef File**: After creating the `.lef` file, you need to place it in the correct directory for your synthesis tool. This typically involves moving the file to the `src` folder, where all the design files are located.

   ```bash
   cp path/to/your_file.lef path/to/picorv32a/src/
   ```

   Replace `path/to/your_file.lef` with the actual path to your `.lef` file and `path/to/picorv32a/src/` with the path to the `src` folder in your `picorv32a` project.

2. **Update Synthesis Configuration**: Ensure that the synthesis configuration is aware of the new `.lef` file. This might involve updating configuration files or scripts used by your synthesis tool. For example, you might need to add the `.lef` file to your synthesis command or configuration script.

3. **Run Synthesis**: With the new `.lef` file in place and configuration updated, you can run the synthesis tool to include the new cell in the design. This step will ensure that the new cell is considered during synthesis and that timing and placement are adjusted accordingly.

   ```bash
   run_synthesis
   ```

4. **Verify Integration**: After synthesis, verify that the new cell has been integrated correctly. Check the synthesis reports and any logs to ensure that the cell is functioning as expected and that there are no issues related to its integration.

5. **Update Timing Libraries**: If necessary, update your timing libraries to reflect any changes introduced by the new cell. This may involve updating delay tables or other timing-related files.

By following these steps, you'll ensure that your new cell is properly included in the synthesis flow and that your design reflects the changes accurately.
this is how the library file looks like. We have different library files named as typical,slow ,fastHere We need to modify the config.tcl file of picorv32a directory,

So open the config.tcl file of picorv32a directory and add the commands shown in below image :
OPENLANE :- Now we will go to the open lane directory and execute the docker command.

Will Execute the following commands in a line
../flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]      
add_lefs -src $lefs
run_synthesis
![tracks info](https://github.com/user-attachments/assets/46f1fd97-0d93-48e0-b2e1-57b6105151a7)
![trackfile](https://github.com/user-attachments/assets/fc124ebf-b034-4ff6-87a1-3c9e997c2c2e)
![grid](https://github.com/user-attachments/assets/c08462d2-4b34-4d9a-a658-a52bb3403eb4)
![grid change](https://github.com/user-attachments/assets/4b8b80f4-2293-49df-bccb-c394363ac4c7)
![port](https://github.com/user-attachments/assets/e140750c-eb72-40e8-8eff-8988f00788fd)
![what](https://github.com/user-attachments/assets/83d6b5e4-7f73-4dfd-b1f2-7d4092230f1b)
![portselection](https://github.com/user-attachments/assets/ca5053ca-4dfd-470f-a71f-60fd49cf3a1b)
![sky130_inv mag](https://github.com/user-attachments/assets/21b19d5b-77d0-48e6-a465-63baa5a72c83)
![lef file](https://github.com/user-attachments/assets/d5ce14eb-0d22-4353-981c-f0aa356ea6da)
![extract lef](https://github.com/user-attachments/assets/56524433-f84b-4a0c-8c43-5b0c1c6becd8)
![lef file ](https://github.com/user-attachments/assets/def61d74-8594-4c39-88e8-cb379a9660e3)
![sky130_vsdinv](https://github.com/user-attachments/assets/5ced01f6-a6df-40d9-8586-a630cb3e840c)
![libs library](https://github.com/user-attachments/assets/aca231ba-3152-4279-ab1c-ee2fe9c2ac55)
![slow lib file](https://github.com/user-attachments/assets/1bbd007d-747f-4455-a8bc-88697b5e7caf)
![fast lib ](https://github.com/user-attachments/assets/0efbb460-c521-4156-a5da-9a451b645750)
![all 3 lib file](https://github.com/user-attachments/assets/879004f8-c0aa-4688-aa06-12fa0dbfc3fd)
![copied all lib file](https://github.com/user-attachments/assets/4eee767c-c71b-45fa-84b4-dc0de3e4dcf9)
![openlane run](https://github.com/user-attachments/assets/0a7fab33-7e99-4c21-8508-79f18fe1aba5)
![synthesis successful, slack tns wns](https://github.com/user-attachments/assets/fbee955e-69c0-4221-bcce-5a4da8585195)

### Introduction to Delay Tables

**Delay tables** are essential tools in digital circuit design and timing analysis. They help characterize the propagation delays of logic gates and interconnects within an integrated circuit. The key purpose of delay tables is to provide a detailed account of how different signals will propagate through various paths in a circuit, given specific input conditions. This information is crucial for optimizing performance and ensuring that timing constraints are met.

#### **Key Concepts:**

1. **Delay Table Structure:**
   - **Input Conditions:** Specifies the input signals or conditions for which the delays are measured.
   - **Output Delays:** Lists the corresponding propagation delays from input to output for each condition.

2. **Types of Delays:**
   - **Propagation Delay:** The time it takes for a signal to travel from the input to the output of a gate.
   - **Setup Time:** The minimum time before the clock edge that input signals must be stable to ensure correct data sampling.
   - **Hold Time:** The minimum time after the clock edge that input signals must remain stable to ensure correct data sampling.

3. **Application in Timing Analysis:**
   - **Static Timing Analysis (STA):** Delay tables are used to evaluate the timing of each path in the circuit to ensure it meets the required timing constraints.
   - **Path Analysis:** Helps in determining the critical paths that could potentially violate timing requirements.

4. **Impact on Design:**
   - **Optimization:** By understanding the delays, designers can optimize the placement of gates and adjust the routing to minimize delays and improve performance.
   - **Power Consumption:** Accurate delay information helps in balancing performance with power consumption by optimizing clock speeds and reducing unnecessary switching.

### Power-Aware Clock Tree Synthesis (CTS)

Power-aware CTS is a technique used to optimize the clock distribution network in an integrated circuit while considering power consumption. By controlling the propagation of the clock signal through the use of enable pins in gates, power consumption can be significantly reduced.

#### **How It Works:**

1. **Enable Pins in Gates:**
   - **AND Gate:**
     - **Enable Pin = Logic '1':** Allows the clock signal to propagate through the gate.
     - **Enable Pin = Logic '0':** Blocks the clock signal, preventing it from propagating.
   - **OR Gate:**
     - **Enable Pin = Logic '0':** Allows the clock signal to propagate.
     - **Enable Pin = Logic '1':** Blocks the clock signal.

2. **Advantages:**
   - **Reduced Power Consumption:** By blocking the clock signal in certain areas of the circuit, the switching activity is reduced, leading to lower power consumption.
   - **Improved Efficiency:** Optimizes the clock tree to only distribute the clock where it is needed, minimizing unnecessary power usage.

3. **Implementation:**
   - **Power Management:** The clock tree is designed with power management features that dynamically enable or disable clock distribution based on the circuit's operational state.
   - **Design Trade-offs:** Balancing between power savings and performance is crucial. The design needs to ensure that critical timing requirements are met while achieving power efficiency.
Power-aware CTS is an effective strategy for managing power consumption in complex digital designs, making it a valuable technique in modern IC design and optimization.
![image](https://github.com/user-attachments/assets/9e6d66b3-8b5e-4d3f-ac81-9cff1c80325f)
Let's say we have a clock tree, The buffer present at the first input is driving the load of second two buffers. We have splited the buffer and in clock gating technique we have just swaped the buffer with and gate so now will all the other characteristic will be same or will get changed will see in coming steps.
![image](https://github.com/user-attachments/assets/3b885edc-e96a-4e53-9df4-66b8af6acbec)
Before swaping the buffer with gate we have made some assumptions which are follows
![image](https://github.com/user-attachments/assets/5af4ef52-5508-4179-8c5f-22850c0da35e)
Assume c1=c2=c3=c4=25fF
Assume Cbuf1=Cbuf2=30fF
Total Cap at node 'A'=> 60fF
Total Cap at node 'B'=> 50fF
Total Cap at node 'C'=> 50fF
We have made some observations from here which are as follows

2 levels of buffering
At every level,each node driving same load
Identical buffer at same level
So the output capacitance of the buffer for the entire circuit is not constant, load at the output will be varying and since the load is varying so input transition is also varying.

So becuase of this variation in output and input we will have varity of delays so how to capture that delay we will see with delay tables

How delay tables are prepared?

For this purpose we have carried out the one buffer from the circuit and and seperately varying its input transition within some range of let's say 10ps-100ps than the output load will also vary so we willl characterise the delay and put the data in tabular format.
![image](https://github.com/user-attachments/assets/a65c91ac-a852-4702-9a3e-799185a434c6)
Delay table usage Part 1
Let's take the example for other buffers.
![image](https://github.com/user-attachments/assets/9bd445b1-19ea-400e-8cef-6b8df5b97b4f)
For practical example let's say we have the input transition of 40ps of buffer1 the output capacitance of this particular buffer is 60ff. The delay of the cell in this case is lies between x9-x10.

So the values which are not available in the delay table those are extrapolated from the given data so we can take the range in that case.

Delay table usage Part 2
Now we have to calculate the delay of buffer 2 and after that we can find the latency at the 4 clock end points.

Here input transition is common for both the buffers. now assuming that the transition is around the 60psec and load at both the buffers is 50fF. so it will give the delay of y15.

The total delay from input to the output is= x9' + y15.(here we are ignoring the delay of the wires). that means the skew at the any output point is zero.

If load is not same at the every nodes, the skew will not be the zero.

Lab steps to configure synthesis settings to fix slack and include vsdinv
We will try to modify the parameters of our cell by referring the README.md file in the configuration folder in openlane directory

The README.md file contains information about the parameters of the cell.


In the OpenLANE directory, execute the following commands:

```bash
prep -design picorv32a -tag 01-04_12-54 -overwrite
```

This command is used to overwrite existing files with previous simulation values.

```bash
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
```

These commands set the LEF files for the design.

```bash
echo $::env(SYNTH_STRATEGY)
set ::env(SYNTH_STRATEGY) "DELAY 3"
echo $::env(SYNTH_BUFFERING)
echo $::env(SYNTH_SIZING)
set ::env(SYNTH_SIZING) 1
echo $::env(SYNTH_DRIVING_CELL)
run_synthesis
```

These commands set the synthesis strategy, buffering, sizing, and driving cell parameters, and then run the synthesis.

After running synthesis, it was observed that the timing results show negative slack values:

- **Worst Negative Slack (WNS):** -24.89
- **Total Negative Slack (TNS):** -759.46



After running the synthesis, we observed an increase in chip area and an improvement in slack values.

Since the synthesis for the `picorv32a` design was successful, the next step is to perform floorplanning using the command `run_floorplan`. However, due to an error encountered during this step, we need to first repeat the synthesis using the earlier commands. Once synthesis is completed again, we can proceed with the following commands for floorplanning:

- `init_floorplan`
- `place_io`
- `tap_decap_or`

With floorplanning successfully completed without errors, we can now run the placement step. Placement is successful, and there are no errors. Finally, we will execute the `expand` command in the Tkcon window.
![readme md poening](https://github.com/user-attachments/assets/994f77fd-a495-4229-a5f7-ea2357626d47)
![readme md](https://github.com/user-attachments/assets/267c87a0-2f0a-46a7-b285-6e12036b36ca)
![edited design file](https://github.com/user-attachments/assets/c1e8cf1f-1225-4da2-a032-51deba56ddc4)
![chip area](https://github.com/user-attachments/assets/8721db90-d302-4d50-8655-4591c5090ff1)
![rewrite command](https://github.com/user-attachments/assets/691816d6-f06d-47dd-866f-7584f78266b9)
![chip area increase change](https://github.com/user-attachments/assets/8a0e4b2d-400c-47a1-81a5-a7622e680deb)
![synthesis tns =0](https://github.com/user-attachments/assets/0e88347a-339a-45f1-9d26-8674e66d2f1f)
![run_floorplan](https://github.com/user-attachments/assets/a10cefe3-1816-4ce7-b13c-9d6928f557c3)
![floor](https://github.com/user-attachments/assets/c2d395c9-ea47-473c-9474-1d9c82fd1182)
![placement analysis](https://github.com/user-attachments/assets/6d900e56-5e0f-4843-8de4-4fd5f15af71e)
![openining layout](https://github.com/user-attachments/assets/c460403b-01c4-4723-ab01-89c55586a8eb)
![layout](https://github.com/user-attachments/assets/e3b33ac9-e299-428d-bf0b-5cf651846de3)
![zoomview](https://github.com/user-attachments/assets/7341d1f4-4b08-4ea5-ae46-ef9ea9f4f734)
![expand2](https://github.com/user-attachments/assets/6c5ac4cb-67e4-4969-b811-8a6296835f76)
![expand](https://github.com/user-attachments/assets/468ef856-e0e5-488b-b681-176277a52d99)

**Timing analysis with ideal clocks using openSTA**
Setup timing analysis and introduction to flip-flop setup time
Timing analysis (with ideal clock):- Let's start the setup analysis with the ideal clock(single clock). specifications of the clock is

clock frequency =1 GHz

clock period =1 ns

Now will do the analysis between '0' and 'T' clock period. We sent at edge to the launch flop at '0' clock period and at T=1ns period the second edge reached to capture flop.
Let's say here we have combinatonal delay of theta and set up timing analysis says that this combinational delay should be less than the T for system to work properly.
![image](https://github.com/user-attachments/assets/85a3ad3f-fb8b-4278-aa66-d1ca695940ca)
Now let's open the capture flop and we will see some combinational circuit there it has several MOSFETs , several logics,resistances and capacitances inside it.Also have the time graph for this particular flop
When there is logic '0' or logic '1' of clock 1 the delay of MUX1 and MUX2 will restrict or effect the combinational delay requirement.

So there is some finite amount of time which is required to the D input to settle and this amount of time is reffered to as SET UP TIME.

Hence finite time 's' required before clk edge for 'D' to reach Qm.

So, we can write that the internal delay of the MUX1 = set up time(S).

So, now θ<T becomes θ<(T-S).

Introduction to clock jitter and uncertainty
So in Jitter the clock is being created by PLL(phase-locked loops) and the clk source is expected to sent the clk signal at exactly 0,T,2T,....But that clk source might or might ot be able to generate the clk exactly at 0 or any other certain time because of it's inbuilt variations that is called jitter. Jitter is refered as temporary variation of the clk pulse.
![image](https://github.com/user-attachments/assets/a36306d9-2a95-426a-81c5-e6c4ce1296f4)
Let's consider this uncertantity time(US) in consideration. So, now equation will become θ<(T-S-US). Now assuming 'S'=0.01ns and 'US'=0.09ns. by taking this, Let's identify the timing path in our circuit stage 1 and stage 3 logic path has single clock.

Now,we have to identify the combinational path delay for the both logics.
![image](https://github.com/user-attachments/assets/9caaf42b-0a67-4d2a-924c-5d2bdd778d6d)
![image](https://github.com/user-attachments/assets/1bdf778a-c4e7-4dc8-ae96-6a4d8d5c886b)
**Lab steps to configure OpenSTA for post-synth timing analysis**
We have do STA on the picorv32a design which had timing violations.First we will run the synthesis using the following commands in openlane directory
docker
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
set ::env(SYNTH_SIZING) 1
run_synthesis
Now we have to make a new pre_sta.conf file. We can do this by vim editor or in simple text editor also.
Now we will create a my_base.sdc file which will have the definitions of environment variables.

Now, we also need to create my_base.sdc file having the data shown in below image in openlane/designs/picorv32a/src directory
Now will go to the openlane directory in a new terminal and execute the sta pre_sta.conf command


