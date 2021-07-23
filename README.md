# Remote Keyless Entry System

## Part 1

![image](https://user-images.githubusercontent.com/18746327/126802492-45387ecd-9b7c-4669-9a98-110fd2f69fcd.png)
*NI Multisim Design*

![image](https://user-images.githubusercontent.com/18746327/126802553-034dae5b-b836-4c10-aed3-edf8d10ab8bc.png)
*Physical Circuit Implementation*

A finite state machine of remote keyless entry system is designed with a discrete logic using NAND gates and D flip flop. First, NI Multisim is used for the simulation. After the simulation on Multisim, physical components are implemented on a circuit same as how they are placed on Multisim. NI MyDAQ is used as a power source.


## Part 2

![image](https://user-images.githubusercontent.com/18746327/126802606-daa7734e-f5f3-4d69-a327-cb6605f02fe9.png)
*MainVI: LabVIEW Block Diagram*

![image](https://user-images.githubusercontent.com/18746327/126802676-494dbc75-cd74-4d6e-b523-81f55654f7dc.png)
*SubVI: DIO_Action Engine*

![image](https://user-images.githubusercontent.com/18746327/126802626-ced500fa-e1c8-4e8c-8128-0edd41c08b70.png)
*Physical I/O with switches and LEDs*

The remote keyless entry system is now implemented using LabVIEW. Four tactile pushbutton switches are used for inputs: Lock(L), Unlock(U), Power Door(P), and Reset(R). Five outputs: Driver Door Locked(DD), Other Doors Locked(OD), Side Door Open(SD), Alarm(A), and Clock(CLK) are indicated by LEDs. DIO_Action Engine, which is a subVI to our main system, is used to connect physical I/O to the mainVI. MainVI realizes the finite state machine using loops and case structures. Input booleans are converted to numbers which are used for case structures that check current state and next state, then take actions correspondingly. Frequency is set to 0.5Hz. For this, the clock is designed by providing 0V and 5V every one second, which represents up and down of the clock (bright for one second and dark for one second, so a total of two seconds in one cycle). Reset is polled every 25ms and it is asynchronous to the clock.

## Part 3

To make Complex Programmable Logic Device (CPLD), WinCUPL is used.

![image](https://user-images.githubusercontent.com/18746327/126802734-53c8b0c4-71e7-46eb-9651-f30da42ce6c9.png)
*Physical Circuit Implementation*

![image](https://user-images.githubusercontent.com/18746327/126802777-b307cf0a-54b5-4bf4-8984-ee03061f53d0.png)
3 D-type flip flops are used to implement the FSM. PRESENT and IF are used to realize each state and its next state.

![image](https://user-images.githubusercontent.com/18746327/126802806-79361963-bcee-443c-936f-45f8651462c3.png)
Before programming the chip, test vectors are used as a simulation to check the functionality of the code.

## Part 4

C language was used to code a microcontroller. For this project, LCD is used alongside LEDs to print out the output states.

![image](https://user-images.githubusercontent.com/18746327/126802837-6e62a383-87d5-498e-aeec-d8368753b92d.png)
*Physical Circuit Implementation*

![image](https://user-images.githubusercontent.com/18746327/126802897-319bb39e-acc9-4186-beb6-29eea5ac9632.png)
I defined an input as a 16-bit unsigned integer by bitwise manipulation. There are 8 inputs which are used for cases to determine the next state of FSM.

![image](https://user-images.githubusercontent.com/18746327/126802934-6c398eed-a1ef-4034-87bf-44efc0a7c9e3.png)
C language is used to realize the state machine. A netted case-switch statement is used.

![image](https://user-images.githubusercontent.com/18746327/126802975-994292ed-a224-4ef4-83c3-ee7509d38b68.png)
Each case has its output for both LEDs and LCD display.

![image](https://user-images.githubusercontent.com/18746327/126803011-8caf7cdb-8a4f-481f-b233-8544998db223.png)
A 2 seconds clock cycle is implemented using ‘delay’.


### Final Circuit Implementation
![image](https://user-images.githubusercontent.com/18746327/126803138-d040973e-0ebf-4b88-b3ad-ea376c475713.png)

![image](https://user-images.githubusercontent.com/18746327/126803162-62caf5b0-b334-45a5-a79a-71b3b66735a1.png)

![image](https://user-images.githubusercontent.com/18746327/126803179-f9d5d23b-33a8-412f-bfb9-175793153010.png)

![image](https://user-images.githubusercontent.com/18746327/126803207-2fcb98e1-43a1-41c9-a397-64f75f5823c0.png)

