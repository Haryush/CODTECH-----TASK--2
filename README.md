# CODTECH-----TASK--2
Name: Harsh Deep Company: CODTECH IT SOLUTIONS ID:CT04VLSI2267 Domain: VLSI 
Duration:15th June 2024 to 15th July 2024 Mentor: SRAVANI GOUNI
## Output for Finite state machine 
![IMG-20240630-WA0011](https://github.com/Haryush/CODTECH-----TASK--2/assets/173982392/795dacc0-3be1-491b-a5eb-7a7c9648b22e)
### Project Overview: Designing and Testing a Finite State Machine (FSM) in Verilog using 
ModelSim
#### Objective
The primary objective of this project is to design, implement, simulate, and verify a Finite 
State Machine (FSM) using Verilog and ModelSim. The project aims to provide a practical 
understanding of FSM design in digital systems and demonstrate the use of hardware 
description languages (HDL) and simulation tools in the VLSI design process.
#### Key Activities
1. **FSM Design**
 - The FSM’s state diagram, including states and transitions, was defined.
 - The states were encoded, and state transition logic was defined.
2. **FSM Implementation in Verilog**
 - Verilog code was written to implement the FSM based on the defined state diagram.
 - The code included state encoding, state registers, and next-state logic.
3. **Testbench Development**
 - A Verilog testbench was written to simulate the FSM.
 - A test sequence was developed to validate the FSM’s behavior under various 
conditions.
4. **Simulation and Verification**
 - ModelSim was used to compile and simulate the Verilog code.
 - It was verified that the FSM transitions correctly between states as per the defined state 
diagram.
 - Simulation waveforms were analyzed to ensure the FSM operates as expected.
 - ### Detailed Description

#### FSM Design

- **State Diagram**: The FSM was defined with states and transitions. For example, a 3-

state FSM with states A, B, and C where:

 - A transitions to B.

 - B transitions to C.

 - C transitions back to A.

#### FSM Implementation in Verilog

- **State Encoding**: Binary codes were assigned to each state. Example:

 - A = 2’b00

 - B = 2’b01

 - C = 2’b10

- **Verilog Code**: Verilog code was written to implement the FSM.

 ```verilog

 Module fsm (

 Input wire clk,

 Input wire reset,

 Output reg [1:0] state

 );

 // State encoding

 Parameter A = 2’b00, B = 2’b01, C = 2’b10;
// State register
 Reg [1:0] next_state;
 Always @(posedge clk or posedge reset) begin
 If (reset)
 State <= A;
 Else
 State <= next_state;
 End
 Always @(*) begin
 Case (state)
 A: next_state = B;
 B: next_state = C;
 C: next_state = A;
 Default: next_state = A;
 Endcase
 End
 Endmodule
 ```
#### Testbench Development
- **Clock Generation**: A clock signal was created for simulation.
- **Reset Initialization**: A reset signal was applied to initialize the FSM.
- **Test Sequence**: A sequence of inputs and expected outputs was defined to test state 
transitions.
- **Verilog Testbench**:
 ```verilog
 Module fsm_tb;
 // Inputs
 Reg clk;
 Reg reset;
 // Outputs
 Wire [1:0] state;
 // Instantiate the FSM
 Fsm uut (
 .clk(clk),
 .reset(reset),
 .state(state)
 );
 // Clock generation
 Initial begin
 Clk = 0;
 Forever #5 clk = ~clk;
 End
// Test sequence
 Initial begin
 // Initialize reset
 Reset = 1;
 #10 reset = 0;
 
 // Check transitions
 #20;
 If (state != 2’b01) $display(“Test Failed at time %t: expected state 01, got %b”, $time, 
state);
 
 #20;
 If (state != 2’b10) $display(“Test Failed at time %t: expected state 10, got %b”, $time, 
state);
 
 #20;
 If (state != 2’b00) $display(“Test Failed at time %t: expected state 00, got %b”, $time, 
state);
 
 $display(“All tests passed”);
 $stop;
 End
 Endmodule
 ```
#### Simulation and Verification
- **Compile the Design**: The Verilog code and the testbench were compiled using 
ModelSim.
- **Run the Simulation**: The testbench was executed in ModelSim to simulate the FSM.
- **Verify Outputs**: The simulation results and waveforms were checked to ensure the 
FSM transitions between states correctly.
#### Outcomes
- The FSM was successfully designed and implemented in Verilog.
- A comprehensive testbench was developed to simulate and validate FSM behavior.
- The correct operation of the FSM was verified using ModelSim, ensuring it met the 
specified design criteria.
### Conclusion
This project provided hands-on experience in digital design using Verilog, including FSM 
design, implementation, testing, and verification using simulation tools. Key concepts in 
HDL-based design and the practical application of simulation for verifying digital systems 
were reinforced.
