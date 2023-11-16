# Experiment-07- Encoders-and-decoders 
## AIM:
To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
## HARDWARE REQUIRED:
PC, Cyclone II , USB flasher
## SOFTWARE REQUIRED: 
Quartus prime
## THEORY 

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
Developed by: nivetha a
RegisterNumber:  21
*/

## ENCODER:
```
module enc(a0,a1,a2,y0,y1,y2,y3,y4,y5,y6,y7);
input y0,y1,y2,y3,y4,y5,y6,y7;
output a0,a1,a2;
or(a0,y7,y5,y3,y1);
or(a1,y7,y6,y3,y2);
or(a2,y7,y6,y5,y4);
endmodule

```
## DECODER:
```

module dec (a0,a1,a2,y0,y1,y2,y3,y4,y5,y6,y7);
input a0,a1,a2;
output y0,y1,y2,y3,y4,y5,y6,y7;
wire a0bar,a1bar,a2bar;
not(a0bar,a0);
not(a1bar,a1);
not(a2bar,a2);
and(y0,a0bar,a1bar,a2bar);
and(y1,a0,a1bar,a2bar);
and(y2,a0bar,a1,a2bar);
and(y3,a0,a1,a2bar);
and(y4,a0bar,a1bar,a2);
and(y5,a0,a1bar,a2);
and(y6,a0bar,a1,a2);
and(y7,a0,a1,a2);
endmodule

```



### RTL LOGIC  

## ENCODER:
![282741841-45b612d6-4b40-42f2-b5a1-b8deec667f69](https://github.com/nivetharajaa/Experiment-08-Encoders-and-decoders-/assets/120543388/dd99807d-3fad-458d-8df4-31d568080f7a)


## DECODER:
![282741864-da28368d-92af-466b-8e62-f2ff5b648f18](https://github.com/nivetharajaa/Experiment-08-Encoders-and-decoders-/assets/120543388/de0bf3fa-da35-4174-9c38-a838017b61b2)






### TIMING DIGRAMS  

## ENCODER:
![282741920-a48919c6-c892-44a1-a944-72892ac3ef83](https://github.com/nivetharajaa/Experiment-08-Encoders-and-decoders-/assets/120543388/12a38d80-4040-4985-9c0e-09c7e3697647)


## DECODER:
![282741957-0982fd82-d1db-4ec7-b284-a750c5f9718e](https://github.com/nivetharajaa/Experiment-08-Encoders-and-decoders-/assets/120543388/aeeb210b-a914-434c-b3ca-92e428145e85)



### TRUTH TABLE 
## ENCODER:
![282741992-671cd690-fef1-4886-8d22-06a382e9617d](https://github.com/nivetharajaa/Experiment-08-Encoders-and-decoders-/assets/120543388/d802f553-6813-4d41-a092-5f09ab9b13e4)


## DECODER:
![282742013-3f8d8259-2884-4bca-a0f3-16dc686b37b3](https://github.com/nivetharajaa/Experiment-08-Encoders-and-decoders-/assets/120543388/1857529d-ac70-43a9-a692-2df464af6889)





### RESULTS 
thus the program to design encoder and decoder is successfully completed
