ECE281_Lab3
===========

Elevator Controller Variations

__*SCHEMATIC*__


![](https://github.com/dustyweisner/ECE281_Lab3/blob/master/ElevatorControllerSchematic.jpg?raw=true)



The code was separated into two parts rather than three like the three machines that make the state machine work. These include the next state logic, the state memory, and the output logic. In the shell, the code was not as good as it could be because the next state logic and the state memory were combined. The following shows the good and the bad code:


__*GOOD CODE*__


Within the [Moore Elevator Controller](https://github.com/dustyweisner/ECE281_Lab3/blob/master/MooreElevatorController_Shell.vhd), the bottom portion where the floor output logic is defined is good code because it is separated from the other two sections.This is the ouput logic coding:    
floor <= "0001" when (floor_state = floor1) else  
			"0010" when (floor_state = floor2) else  
			"0011" when (floor_state = floor3) else  
			"0100" when (floor_state = floor4) else  
			"0001"; 


__*BAD CODE*__


Also within the [Moore Elevator Controller](https://github.com/dustyweisner/ECE281_Lab3/blob/master/MooreElevatorController_Shell.vhd) is the next state logic at the top after process that stores current values. The state memory is also intermixed, and it includes the cases of whens and if statements.


__*BASIC MOORE*__


*SEEN BY DR. NEEBEL* - The moore design implements the up-down and stop inputs to make the current state output.


__*BASIC MEALY*__


*SEEN BY DR. NEEBEL* - The mealy design implements the up-down and stop inputs to make the current state output, and to output the next state on the seven segment LED.


__*MORE FLOORS*__


*SEEN BY DR. NEEBEL* - The more floors design implements 8 floors (in this case the first 8 prime numbers) and outputs them in the first to seven segment LEDs.
