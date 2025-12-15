# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**



1. Open Quartus Prime and create a new project for the JK flip-flop.
2. Create a new Verilog file and type the JK flip-flop program.
3. Declare the inputs j, k, clk and outputs q, qbar as reg.
4. Initialize q and qbar inside an initial block to set the starting state.
5. Use an always @(posedge clk) block to update the output on every positive clock edge.
6. Implement the JK characteristic equation using q <= (j & ~q) | (~k & q).
7. Assign qbar <= ~q to generate the complement output.
8. Save and compile the program to check for errors.
9. Create a simulation file and add the module for waveform testing.
10. Apply different combinations of j, k, and clock pulses in the waveform editor.
11. Run the simulation to observe q and qbar transitions.
12. Compare the simulated results with the JK truth table.

**PROGRAM**

/* 
   Program for JK flip-flop and verification of its truth table 
   using Verilog in Quartus Prime.
   Developed by: Monica R
   Register Number: 25010138
*/


```

module jkflip(j,k,clk,q,qbar);
input j,k,clk;
output reg q,qbar;
initial 
begin
q=1'b0;
q=1'b1;
end 

always @(posedge clk)
begin 
q<=(j&~q)|(~k&q);
qbar<=~q;
end
endmodule
```

**RTL LOGIC FOR FLIPFLOPS**
<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/e856fa44-cf9e-4337-b7f4-468973550749" />


**TIMING DIGRAMS FOR FLIP FLOPS**
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/c69f9d6b-2f32-4ace-8bf5-6ba26bb8275e" />



  
**Result**

The JK flip-flop was successfully designed and implemented using Verilog in Quartus Prime. The RTL schematic and timing diagram were obtained, and the observed output waveforms matched the theoretical JK flip-flop truth table, confirming correct functionality.
