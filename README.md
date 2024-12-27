This project implements a Morse Code Generator using a Finite State Machine (FSM) in Verilog. It encodes alphabets into Morse code using a sequence of dot and dash signals and includes a testbench for verification.

PROJECT OVERVIEW

The Morse Code FSM is designed to generate Morse code for alphabets (A-J) based on their standard representation.
It uses a Finite State Machine (FSM) to:
Encode each character into its Morse code sequence.
Output dot and dash signals sequentially for the character.

A testbench is included to verify the FSM behavior by:
Simulating the input of alphabets A-J.
Generating Morse code sequences.
Decoding Morse code back into the corresponding alphabets.

FEATURES

Converts input alphabets (A-J) into Morse code signals (dot and dash).
Includes a testbench for simulation and verification.
Modular design for easy integration into larger systems.
Handles reset functionality for FSM initialization.

SYSTEM ARCHITECTURE
The system is composed of:
FSM Design (morse_rtl): Handles state transitions and generates Morse code signals.
Testbench (morse_code_fsm_tb): Simulates the FSM behavior and verifies the outputs.

MODULES

Inputs:
clk: Clock signal.
rst: Reset signal to initialize the FSM.
alphabet: 4-bit input representing the input character.

Outputs:
dot: High for Morse . output.
dash: High for Morse - output.

FSM States:
Idle state (0): Waits for a valid alphabet input.
Encoding states: Transition through states to output the Morse code for the input character.
Return to idle after completing the Morse code sequence.
2. morse_code_fsm_tb
The testbench verifies the functionality of the morse_rtl module.

Simulation Flow:
Generates a clock signal.
Asserts the reset signal to initialize the FSM.
Applies test cases by providing alphabets (A-J) as inputs.
Captures and decodes Morse code signals into corresponding alphabets.

Outputs:
Verifies dot and dash signals for correct Morse code generation.
Decodes Morse signals to confirm accuracy.

SIMULATION RESULTS
The simulation was conducted for alphabets A-J with the following expected results:

Input Alphabet	Morse Code	Dot (.)	Dash (-)
A (4'b0000)	. -	High	High
B (4'b0001)	- . . .	High	High
C (4'b0010)	- . - .	High	High
D (4'b0011)	- . .	High	High
E (4'b0100)	.	High	Low
F (4'b0101)	. . - .	High	High
G (4'b0110)	- - .	High	High
H (4'b0111)	. . . .	High	Low
I (4'b1000)	. .	High	Low
J (4'b1001)	. - - -	High	High

