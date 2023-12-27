# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure
/* write all the steps invloved */



### PROGRAM 
```
Program for flipflops  and verify its truth table in quartus using Verilog programming.

UP COUNTER

Module upcounter(clk,a);

input clk;

output reg[3:0];

always @(posedge clk)

begin

a[3]=(a[2]&a[1]&a[0])^a[3];

a[2]=(a[1]&a[0])^a[2];

a[1]=(a[0]^a[1]);

a[0]= ^a[0];

end

endmodule

DOWN COUNTER

Module downcounter(clk,a);

input clk;

output reg[3:0]a;

always @(posedge clk)

begin

a[3]=(~a[2]&~a[1]&~a[0])^a[3];

a[2]=(~a[1]&~a[0])^a[2];

a[1]=(~a[0]^a[1]);

a[0]=1^a[0];

end

endmodule
```
developed by :Monish S
Reg.no:212223040115

### RTL LOGIC UP COUNTER AND DOWN COUNTER  

UP COUNTER 
![image](https://github.com/Monishsaravanan/Exp-7-Synchornous-counters-/assets/145743227/97e5506c-dbac-4971-854e-2157c4fdc9b6)
Down Counter
![image](https://github.com/Monishsaravanan/Exp-7-Synchornous-counters-/assets/145743227/141f2596-078e-4b6a-9965-d16c8b87f5ae)

Program for flipflops  and verify its truth table in quartus using Verilog programming.

 
















### TIMING DIGRAMS FOR COUNTER  
up counters
![image](https://github.com/Monishsaravanan/Exp-7-Synchornous-counters-/assets/145743227/b24c308f-f5cc-41ea-9d90-b9f27dbbaff4)
Down counter
![image](https://github.com/Monishsaravanan/Exp-7-Synchornous-counters-/assets/145743227/f0831ce0-004c-4893-af40-4104fd9f5f1b)




### TRUTH TABLE 
up counter
![image](https://github.com/Monishsaravanan/Exp-7-Synchornous-counters-/assets/145743227/c8f0b996-0cfe-46f8-b40c-babed629adba)
down counter
![image](https://github.com/Monishsaravanan/Exp-7-Synchornous-counters-/assets/145743227/17c718f5-8f0e-4444-ab58-1ff49ba93575)








### RESULTS 
    Thus synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.
