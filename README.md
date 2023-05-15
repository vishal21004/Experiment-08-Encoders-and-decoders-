# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure
Step-1: create module encoder and decoder.

Step-2: Get inputs and outputs for encoders and decoders.

Step-3: perform or operation for encoder and and logic for decoders.

Step-4: perform RTL LOGIC and get waveform.

Step-5: End the module.

### PROGRAM 
```
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: M.A.Vishal
RegisterNumber: 212222230177
```
### ENCODER
```
module encoder (d0,d1,d2,d3,d4,d5,d6,d7,x,y,z);
input d0,d1,d2,d3,d4,d5,d6,d7;
output x,y,z;
or (x,d4,d5,d6,d7);
or (y,d2,d3,d5,d7);
or (z,d1,d3,d5,d7);
endmodule

```
### DECODER
```
module exp8(a0,a1,a2,y0,y1,y2,y3,y4,y5,y6,y7);
input a0,a1,a2;
output y0,y1,y2,y3,y4,y5,y6,y7;
wire a0bar,a1bar,a2bar;
not (a0bar,a0);
not (a1bar,a1);
not (a2bar,a2);
and (y0,a0bar,a1bar,a2bar);
and (y1,a0bar,a1bar,a2);
and (y2,a0bar,a1,a2bar);
and (y3,a0bar,a1,a2);
and (y4,a0,a1bar,a2bar);
and (y5,a0,a1bar,a2);
and (y6,a0,a1,a2bar);
and (y7,a0,a1,a2);
endmodule
```

### RTL LOGIC  
![exp8 encoder rtf](https://github.com/bharathraj1905/Experiment-08-Encoders-and-decoders-/assets/121490575/f28c6c82-ccc3-4926-b446-100a49720c64)

![digital exp8 decoder rtl](https://github.com/bharathraj1905/Experiment-08-Encoders-and-decoders-/assets/121490575/38e14422-ef1e-42f5-97af-5b9e6aad7ec8)
### TIMING DIGRAMS  
![digital exp8 encoder](https://github.com/bharathraj1905/Experiment-08-Encoders-and-decoders-/assets/121490575/57cd5ff4-8e62-4b45-8ee2-b1937be8e6ce)

![digital exp8 decoder](https://github.com/bharathraj1905/Experiment-08-Encoders-and-decoders-/assets/121490575/9bf873c4-41ee-432c-bb35-cce46a4fdf68)
### TRUTH TABLE 
![encoder truth table](https://github.com/bharathraj1905/Experiment-08-Encoders-and-decoders-/assets/121490575/0277ee5a-f422-435a-9242-ae5c3f44d2d0)

![decoder truth table](https://github.com/bharathraj1905/Experiment-08-Encoders-and-decoders-/assets/121490575/f99d0305-e90e-4f01-9b65-f2b1ba83ba4f)
### RESULTS 
Thus the program to desing encoder and decoder is completed.
