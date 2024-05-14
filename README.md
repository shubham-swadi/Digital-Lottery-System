# Digital-Lottery-System-using-Verilog
We live in a world surrounded by digital equipments of all sorts.
Inspired by all the digitalization around us, me and my teammate M N Vishnu tried to implement a Digital Lottery System using components of digital electronics and Verilog hardware description language.
The output/ lottery winner was decided by the internal logic of the circuit.
To generate a random winner, we made use of Linear Feedback Shift Register(LFSR) .

## Linear Feedback Shift Register (LFSR)
A linear feedback shift register is a type of shift register which consists of flip-flops connected in series.
It is primarily used in digital circuits for pseudorandom number generation.
The term "Shift Register" indicates that the bits are moved from one flip-flop to next flip-flop after every clock pulse.
The "Linear Feedback" aspect of LFSR comes from the way it generates its next state based on its current state.
The new bit that enters the the first (leftmost) flip-flop is determined by a linear combination of bits stored at particular positions in the shift register at that particular cycle.
This combination is achieved with the help of EXOR gates which introduce a level of non-linearty despite its linear name.

The LFSR starts with an inital state which are the bits stored in the flip-flops.
After every clock pulse, the bit moves rightwards.
The last bit is again fed back.
Thee feedback mechanism involves selecting bits from different flip-flops of current state and sending them with and EXOR operation to some other flip-flop as next state.
The bits fed back to and from are selected based on the required properties of LFSR.
Thus, a new sequence is generated after every clock pulse.

LFSR might appear random but they are deterministic and repeat themself after certain amounts of clock pulses.

Here is the schematic of the LFSR circuit we used
![lfsr](https://github.com/shubham-swadi/Digital-Lottery-System/assets/122473812/1f0d37a9-fc3c-40b8-a3c7-c8cc126ad048)


## Inputs to the circuit
- Clock Pulse- Clock Pulse is an important control signal for any sequential circuit.
- Lucky bit- 
- Reset bit- The reset bit when turned high resets the lottery to the initial state i.e. lucky queue is set to zero and participant id is also set to zero.
- Write bit- The lucky bit is fed into the lucky queue when the write bit is turned high.
- Stop bit- The stop bit can be used to signal the end the input sequence.

## Outputs of the circuit
- Counter Display- The counter display shows the current number of participants in the lottery.
- Winner Display- The winner display shows the participant ID of the winner.  

## Logic & Implementation

## Verilog Code
The above circuit was implemented by coding in verilog. The verilog code for the circuit can be found in the `test.v` file in the repository. 

## Testbench & Simulation
To test the correct working of the system, a testbench was designed.
The testbench generates random lucky bits, clock, write pulse and stop signal, and then checks the output of the system to make sure that it is correct.
The testbench also included a built-in graphical interface with the help of GTKWave.
GTKWave is a simulation interface which helped to obtain the following waveforms.

![simulation1](https://github.com/shubham-swadi/Digital-Lottery-System/assets/122473812/49d34b36-1531-4dc0-9f0d-a32ebf55bd7b)
![simulation2](https://github.com/shubham-swadi/Digital-Lottery-System/assets/122473812/cab130a0-c544-4b55-bbc5-bdcce87729c0)

The testbench used can be found in the `ttb.v` file in the repository.

## Future Scope
The given circuit can be implemented on basic FPGA boards such as Digilent Basys 3 Artix-7 FPGA Trainer Board.

## Conclusion
A digital lottery system was successfully designed & simulated on Verilog.
Key concepts of digital electronics and hardware description languages were learnt in the process.
This project serves as an introduction to future projects on design of digital systems.

## Refernces
- [Digital Electronics basic](https://nesoacademy.org/ec/05-digital-electronics)
- [NPTEL NOC:Digital Circuits and Systems](https://nptel.ac.in/courses/117106114)
- [ASIC World Directory](http://asic-world.com/verilog/index.html)
- [HDLBits Verilog Practice](https://hdlbits.01xz.net/wiki/Main_Page)
