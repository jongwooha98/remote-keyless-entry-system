Project 1


NI Multisim Design



Physical Circuit Implementation

A finite state machine of remote keyless entry system is designed with a discrete logic using NAND gates and D flip flop. First, NI Multisim is used for the simulation. After the simulation on Multisim, physical components are implemented on a circuit same as how they are placed on Multisim. NI MyDAQ is used as a power source.

 

Project 2


MainVI: LabVIEW Block Diagram



SubVI: DIO_Action Engine



Physical I/O with switches and LEDs

The remote keyless entry system is now implemented using LabVIEW. Four tactile pushbutton switches are used for inputs: Lock(L), Unlock(U), Power Door(P), and Reset(R). Five outputs: Driver Door Locked(DD), Other Doors Locked(OD), Side Door Open(SD), Alarm(A), and Clock(CLK) are indicated by LEDs. DIO_Action Engine, which is a subVI to our main system, is used to connect physical I/O to the mainVI. MainVI realizes the finite state machine using loops and case structures. Input booleans are converted to numbers which are used for case structures that check current state and next state, then take actions correspondingly. Frequency is set to 0.5Hz. For this, the clock is designed by providing 0V and 5V every one second, which represents up and down of the clock (bright for one second and dark for one second, so a total of two seconds in one cycle). Reset is polled every 25ms and it is asynchronous to the clock.

 

Project 3
To make Complex Programmable Logic Device (CPLD), WinCUPL is used.



Physical Circuit Implementation



3 D-type flip flops are used to implement the FSM. PRESENT and IF are used to realize each state and its next state.



Before programming the chip, test vectors are used as a simulation to check the functionality of the code.

 

Project 4
C language was used to code a microcontroller. For this project, LCD is used alongside LEDs to print out the output states.



Physical Circuit Implementation

 



I defined an input as a 16-bit unsigned integer by bitwise manipulation. There are 8 inputs which are used for cases to determine the next state of FSM.



C language is used to realize the state machine. A netted case-switch statement is used.



Each case has its output for both LEDs and LCD display.



A 2 seconds clock cycle is implemented using ‘delay’.

Throughout the semester, I liked that we got to have some hands-on experience in building a physical implementation using both software and hardware. Especially, I enjoyed implementing FSM using different methods. A finite state machine is a system that inputs change its state, and outputs are corresponding to its state. From realizing a finite state machine in![image](https://user-images.githubusercontent.com/18746327/126802390-47d99519-e94a-4abf-b6c5-9a9ef916f3a9.png)
 four different methods, I was able to obtain skills in discrete logic, LabVIEW, and CPLDC, microcontroller.



Realizing FSM using Discrete logic with NAND gates, a hex inverter, and a D type flip flop.



Realizing FSM using LabVIEW.



Realizing FSM using a Complex Programmable Logic Device.



Realizing FSM using a microcontroller.
