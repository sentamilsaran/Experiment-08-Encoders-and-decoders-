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
/* write all the steps invloved */



### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by:sentamilsaran S 
RegisterNumber: 22008684 
*/
i)ENCODER:
module exp8(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);

output a,b,c;

input d0,d1,d2,d3,d4,d5,d6,d7;

or(a,d4,d5,d6,d7);

or(b,d2,d3,d6,d7);

or(c,d1,d3,d5,d7);

endmodule

ii)DECODER:

module dec(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);

output d0,d1,d2,d3,d4,d5,d6,d7;

input a,b,c;

assign d0=(~a & ~b & ~c) ;

assign d1=(~a & ~b &c);

assign d2=(~a & b &~c);

assign d3=(~a & b &c);

assign d4=(a &~b&~c);

assign d5=(a &~b&c);

assign d6=(a&b&~c);

assign d7=(a&b&c);

endmodule






### RTL LOGIC  
Encoder

![image](https://user-images.githubusercontent.com/123304969/213966460-21d11ebd-bfee-4d98-b577-427983c13647.png)

Decoder

![image](https://user-images.githubusercontent.com/123304969/213966475-6857ffb9-a600-4dc4-8cec-574f333e2546.png)







### TIMING DIGRAMS  
Encoder

![image](https://user-images.githubusercontent.com/123304969/213966538-1c18a1e4-67e0-413a-8758-e5f4282a91bb.png)
![image](https://user-images.githubusercontent.com/123304969/213966549-789418e1-3ff9-4110-ac06-1e5c4569d90c.png)
![image](https://user-images.githubusercontent.com/123304969/213966559-b1709215-8f5f-4094-bbc8-9b526cee22bc.png)

Decoder

![image](https://user-images.githubusercontent.com/123304969/213966576-d02b2dc3-0bc6-475d-883a-d5d8b5b294ce.png)


### TRUTH TABLE 
Encoder

![image](https://user-images.githubusercontent.com/123304969/213966603-0f801d7c-c625-490b-b7e7-3924773390e0.png)

Decoder

![image](https://user-images.githubusercontent.com/123304969/213966629-c8db3002-e29a-4911-8372-7a577b6327dd.png)


### RESULTS 
Thus 8 to 3 Encoder and 3to8 Decoder are implemented successfully using verilog and validate its outputs
