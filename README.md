# NASSCOM_VSD_SoC_Workshop
> Documentary of 5 Days workshop "Digital VLSI SoC Design and Planning" conducted by VSD &amp; NASSCOM

## Day 1: Inception of open-source EDA tool OpenLANE & Sky130 PDK  
   As per the title the 1st day is to give glimps of Complete Digital VLSI SoC Design and Planning & how we can do this everything by the help of **EDA tool** and the most important thing which is the *blood* of the complete design is **Sky130 PDK**.  
   This day is further devided in 3 major parts.  
<details>
 <summary>
   How to talk to Computer </summary>  

- As we know that the widely known digital electronic system is our **computer**. Which is working based on **0's &amp; 1's** (AKA Machine/Binary Language). Any computer system contains **Hardware &amp; Software**. If we look computer interms of software point of view, we can get to know about different types of applications such as MS Office, Paint, Notepad ETC. As we know that computer is working only based on 0's &amp; 1's. And most softwares or applications are in the form of humanly readable language. To convert the humanly readable language to machine language, Below is the Basic Flow which Illustrate How Computer Talks with Hardware.
![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/fee221b5-264b-4577-9ea9-baa3e8f8410c)
- As we can see in above image, System software is helping the application to talk to hardware, which contains OS, Compiler & Assembler. Where OS provides efficient environment to compiler & Assembler to talk to the hardware. First of all, the application which is nothing but a task that we want to perform on the computer is written in higher level languages such as C,C++. And then it is passing through the compiler, which produces **.exe file** (in case of Windows OS). **.exe file** contains the sets of instruction which is understand by the assembler. This sets of instructions are written based on assembly language. After passing through the assembler, the instructions are converted into the form of 0's & 1's, which is understand by computer.
- Let's take the example of timer application.  
  ![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/86cfc996-ec8f-4e86-a2d4-681cefaad441)
- In above image, timer application is written in C language and that code is converted into the set of instruction through compiler. At last that sets of instruction is process into the hardware by passing through the assembler. Here, we are considering chip as a hardware.
- If we try to dig one step deeper into the system software, their is an abstract interface is exist. Which make the job of OS easy. That is known as Instruction Set Architecture or 'architecture' of computer. Better the interface, better the performance.  
  ![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/cef1ab85-4e15-4ecf-a9c5-94325d6a9ee0)
- That's where the first step of SoC flow start, that is "Specification". That's where the role of architecture engineer come into the picture. The job of the architecture engineer is to create interface based on specification. And based on interface, the RTL code is written by using HDL language.
- Below Image is Illustrate the overview of SoC design which is devided in 3 parts.  
![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/5aa840a2-efb3-4b6e-adc1-f6b9995c5ed2)
- And try to understand the flow of SoC design(RTL to GDS-II) right from RISC-V Architecture (which we can develope using HDL language also known as RTL code) to Layout (GDS-II File)
![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/2838b479-4c2f-434c-ba08-6b4d98c59cf2)
</details>  

<details>
 <summary>
   SoC Design and ASIC Flow </summary>  
   
- As we seen earlier the overview of the SoC design, the first part is RISC-V Instructions Set Architeture. Before explaining what is RISC-V? Let's we try to understand where it is used in Real life?  
- Let's we see the computer interms of hardware point of view. Below is the image of Arduino Leonardo Board. The funtionality of computer and arduino is quite similar, So Let's dig into the hardware and try to understand the importante role of RISC-V Architecture.
![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/93a26894-e9de-4554-b58c-87c2e8f8835d)
- As we can see that, their are so many tiny electronics components are soldered on the PCB Board such as MicroUSB Port, 5mm Powersupply port, Push button, LEDs, Diodes, Capacitors, Jumpers, Transistors and most importante component which is hoghlited by yellow ring is Integrated Chip (AKA IC/Microcontroller). And this complete 
PCB Board is developed based on below given overview of the schematic. So let's dig one step deep into the hardware.
![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/909bf4e1-7449-4773-8889-1428c9c1bea8)
- As we can see that, Processor/SoC is the center of the all componets which communicationg with other components.  
- So, Let's try to see and understand the IC.  
  ![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/b5a5646e-f1f8-4197-a755-51e2b9817e25)  
- Above image is the shows the outer package with it's size and type of the IC.
- **QFN-48** is the type of IC Package and **7mm X 7mm** is the size of IC.
- That's where the role of Physical design engineer come into the picture, who decides the type of package and size of the IC.
- That's what the end result/product that VLSI Industry are producing. That's where the complete VLSI ecosystem are build to produce that IC.
- Around the IC, the Input &amp; Output pins are their.
- But, Inside the package the chip/die is placed in the center of the package and the connection of I/O Pins of IC with Internal pins of chip/Die is shown in below image.  
  ![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/8d021aa6-86cd-475e-ba69-b7ea4c211714)
- Let's dig one step more into the deep. We can see as below image, which shows the internal structure of chip/Die.  
 ![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/7c22962a-9fb4-427a-8dde-090206076aef)
- As we can see that, their are majorly 3 types of area is exist on the chip
  - **Die**:
  - **Pads**:
  - **Core**:
    - In the core area all standard cells, macros and IP's are placed. The given below image illustrate that.
![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/72b6351a-e529-4564-904f-a31d9e0be754)
 - **Foundary IP's**:
 - **Macros**:

![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/b5161ad3-6541-4ec9-8f47-afd1003c0e9c)
</details>  


<details>
 <summary>
   Get familiar with open-source EDA Tool (OpenLANE) </summary>  
</details>

## Day 2: Good & bad Floorplanning and Introduction to Standard Cells  
<details>
 <summary>
  Chip Floor planning considerations </summary>  
</details>
<details>
 <summary>
   Library Binding and Placement </summary>  
</details>
<details>
 <summary>
   Cell design and characterization flow </summary>  
</details>
<details>
 <summary>
   General timing characterization parameters </summary>  
</details>

## Day 3: Design library cell using Magic Layout and ngspice characterization
<details>
 <summary>
   Labs for CMOS inverter ngspice simulations </summary>  
</details>
<details>
 <summary>
    Inception of Layout of CMOS fabrication process </summary>  
</details>
<details>
 <summary>
    Sky130 Tech File Labs </summary>  
</details>

## Day 4: Pre-layout timing analysis and importance of good clock tree 
<details>
 <summary>
   Timing modelling using delay tables </summary>  
</details>
<details>
 <summary>
    Timing analysis with ideal clocks using openSTA </summary>  
</details>
<details>
 <summary>
   Clock tree synthesis TritonCTS and signal integrity </summary>  
</details>
<details>
 <summary>
  Timing analysis with real clocks using openSTA </summary>  
</details>

## Day 5: Final steps for RTL2GDS using tritonRoute and openSTA
<details>
 <summary>
   Routing and design rule check (DRC) </summary>  
</details>
<details>
 <summary>
   Power Distribution Network and routing </summary>  
</details>
<details>
 <summary>
   TritonRoute Features </summary>  
</details>
<details>

