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

  It requires "System software" which contains OS, Compiler & Assembler. Where OS provides efficient environment to compiler & Assembler to talk to the hardware. First of all, the application which is nothing but a task that we want to perform through the computer is written in Higher level languages such as C,C++. And then it is passing through the compiler, which produces **.exe file** (in case of Windows OS). **.exe file** contains the instruction which is understand by the assembler. This sets of instructions are in the form of assembly language. After passing through the assembler, the instructions are converted into the form of 0's & 1's.

  Let's take the example of timer application.  
  ![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/86cfc996-ec8f-4e86-a2d4-681cefaad441)  
  In above image, timer application is written in C language and that code is converted into the set of instruction through compiler. At last that sets of instruction is process into the hardware by passing through the assembler. Here, we are considering chip as a hardware.

  If we try to dive little bit deeper into the system software, their is an abstract interface is exist. Which make the job of OS, easy. That is known as Instruction Set Architecture or 'architecture' of computer. Better the interface, better the performance.  
![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/cef1ab85-4e15-4ecf-a9c5-94325d6a9ee0)  

  That's where the first step of ASIC flow start, that is "Specification". That's where the role of architecture engineer come into the picture. The job of the architecture engineer is to create interface based on specification. And based on interface, the RTL code is written by using HDL language.
  Below Image is Illustrate the overview of complete ASIC design which is devided in 3 parts.  
![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/5aa840a2-efb3-4b6e-adc1-f6b9995c5ed2)

</details>  
<details>
 <summary>
   SoC Design and ASIC Flow </summary>  

- As we seen earlier the overview of the ASIC design, the first part is RISC-V Instructions Set Architeture. Before explaining what is RISC-V? Let's we understand why RISC-V? and Where it is used in Real life?
- Let's we see the computer interms of hardware point of view. Below is the image of Arduino Leonardo Board.  
  ![image](https://github.com/ShahHarsh2711/NASSCOM_VSD_SoC/assets/100216184/e316e38c-c9af-4e20-89b0-b0e2b7854767)

</details>
