# SRAM
Design of a 6T full CMOS SRAM (1k x 32bit) using open souce memory compiler OpenRAM using SCMOS Technology
# What is SRAM ?
- Static random-access memory is a type of random-access memory that uses latching circuitry to store each bit. SRAM is volatile memory; data is lost when power is removed. The term    static differentiates SRAM from DRAM which must be periodically refreshed.
- The data storage cell, i.e., the 1-bit memory cell in static RAM arrays, invariably
consists of a simple latch circuit with two stable operating points (states). Depending on
the preserved state of the two-inverter latch circuit, the data being held in the memory cel
will be interpreted either as a logic "0" or as a logic " 1." To access (read and write) the
data contained in the memory cell via the bit line, we need at least one switch, which is
controlled by the corresponding word line, i.e., the row address selection signal. Usually, two complementary access switches consisting of nMOS pass transistors are implemented to connect the 1-bit SRAM cell to the complementary bitlines (columns). This can be likened to turning the car steering wheel with both left and right hands in complementary directions.

# Table Of Contents
- [Overview](#Overview)
    - [Project Details](#Project-Details)
    - [Basics of Working Principle of a SRAM](#Basic-Working-of-SRAM) 
- [Schematic Design and Simulation](#Schematic-design-&-Simulation)
     - [Trasnsistor sizing](#Transistor-Sizing)
     - [6T cell](#6T-cell)
     - [Pre charge Clock](#Pre-charge-clock)
     - [Sense amplifier](#Sense-amplifier)
     - [Write driver](#Write-driver)
     - [Timing Diagram For Read and Write](#Timing-diagram)
# Project Details
 - Organisation :Advance VLSI Lab, [Silicon Institute Of Technology,Bhubaneswar]
 - Instructors  :[Prof. Saroj Kumar Rout], [Prof. Santanu Sarangi]
 - About        :In this project, we design a novel six-transistor (6T) single-ended static random access memory (SE-SRAM) cell for ultra-low-voltage applications.
 - Keywords     :Ultra-low-vltage application, SRAM, Memory cells, Memory Compiler
 - Classification :IC design using Open-Source Tools
 - Tools used : Spice simulation-[NGSpice], Layout design-[Magic], Memory compiler-[OpenRAM]
 - Technology used:  MOSIS Scalable CMOS ([SCMOS]):[SCMOS] is a *lambda-based* scalable design rules that can be interfaced to many CMOS fabrication process available at MOSIS. 
 - Typical MOS parameters:
    - **NMOS**: tox=7.6nm, nch=1.7e17/cm^3, Vt0=0.49V, un(mobility)=445 cm^2/Vs
    - **PMOS**: tox=7.6nm, nch=1.7e17/cm^3, Vt0=-0.66V, up(mobility)=151 cm^2/Vs
    - Vdd=5V, Lmin=0.4um, Wmin=0.6um
# Basic Working of SRAM
- **Basic block diagram for a SRAM IP**
    - The basic SRAM IP constitute of a 6T cell array, Sense amplifier array, Write Driver array, Precharge array, Address decoder and a wordline driver
    - ![alt text](https://user-images.githubusercontent.com/49194847/100307628-56bd1c00-2fcc-11eb-99dc-e23c7501f2f5.png)
- **6T cell** 
     - A low-power SRAM cell may be designed simply by using cross-coupled CMOS inverters
     - ![alt text](https://user-images.githubusercontent.com/49194847/100307234-54a68d80-2fcb-11eb-9a73-0753d59bd340.png)
- **Read Operation**
    - Let's assume initially the 6T cell is containing 0.Then the effective circuit topology will be like as the image shown below (considering the bit lines are precharged to Vdd) :When M3 and M4 turned on then Vc will discharge thus varying V1 and now the change is voltage of bit line will be sensed by sense amplifier and will be interpreted as 0.
     - ![alt text](https://user-images.githubusercontent.com/49194847/100306663-e57c6980-2fc9-11eb-8096-2ed351e49d88.png)
- **Write Operation**
   - Now let's consider initially the circuit was containing 1 and we want to modify the content to 0.Now for the cell containing 1 effective circuit will be like :Now to write 0 into it we forced the bit line to 0 by writing circuitory.But to modify the content V1 should be =0 As we designed circuit such in a way V2 can't go above Vtn so we have to force V1 > Vtn so that M2 will turn off.
    - ![alt text](https://user-images.githubusercontent.com/49194847/100307328-8fa8c100-2fcb-11eb-9d64-b9a1cc66b057.png)


* * *
[Silicon Institute Of Technology,Bhubaneswar]: https://www.silicon.ac.in/sitbbsr/
[Prof. Saroj Kumar Rout]: https://www.linkedin.com/in/sroutk/
[Prof. Santanu Sarangi]: https://www.linkedin.com/in/santunu-sarangi-b731305b/
[OpenRAM]:              https://openram.soe.ucsc.edu/
[OpenRAMgit]:           https://github.com/VLSIDA/OpenRAM 
[OpenRAMpaper]:         https://ieeexplore.ieee.org/document/7827670/
[SCMOS]:                https://www.mosis.com/files/scmos/scmos.pdf
[NGSpice]:              http://ngspice.sourceforge.net
[NGSpiceMan]:           http://ngspice.sourceforge.net/docs/ngspice-html-manual/manual.xhtml
[Magic]:                http://opencircuitdesign.com/magic/
[Netgen]:               http://opencircuitdesign.com/netgen/
[6t]: https://user-images.githubusercontent.com/49194847/100247200-158f2280-2f60-11eb-8081-27fadc15dadc.png
