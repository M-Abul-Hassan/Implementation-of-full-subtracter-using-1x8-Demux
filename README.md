# Implementation-of-full-subtracter-using-1x8-Demux
A full subtractor using a 1x8 Demultiplexer is a digital circuit that performs binary subtraction with borrow, using a 1x8 Demultiplexer and basic logic gates. The circuit takes three binary inputs, A, B, and Bin, and produces two binary outputs, D (difference) and Bout (borrow).

## Program code:

module full_sub(diff,borrow,Y0,Y1,Y2,Y3,Y4,Y5,Y6,Y7,A,B,Bin,X );  
input A,B,Bin,X;  
output diff,borrow,Y0,Y1,Y2,Y3,Y4,Y5,Y6,Y7;  
demux S1(.I0(Y0),.I1(Y1),.I2(Y2),.I3(Y3),.I4(Y4),.I5(Y5),.I6(Y6),.I7(Y7),.Y(X),.S0(A),.S1(B),.S2(Bin));  
assign diff = Y1 | Y2 | Y4 |Y7;  
assign borrow = Y1 | Y2 | Y3 | Y7;  
endmodule  
module demux(I0,I1,I2,I3,I4,I5,I6,I7,Y,S0,S1,S2);  
input Y,S0,S1,S2;  
output I0,I1,I2,I3,I4,I5,I6,I7;  
reg I0,I1,I2,I3,I4,I5,I6,I7;  
always @ (*)  
begin  
case ({S0,S1,S2})   
3'd0 : {I0,I1,I2,I3,I4,I5,I6,I7} = {Y,7'd0};   
3'd1 : {I0,I1,I2,I3,I4,I5,I6,I7} = {1'd0,Y,6'd0};   
3'd2 : {I0,I1,I2,I3,I4,I5,I6,I7} = {2'd0,Y,5'd0};   
3'd3 : {I0,I1,I2,I3,I4,I5,I6,I7} = {3'd0,Y,4'd0};   
3'd4 : {I0,I1,I2,I3,I4,I5,I6,I7} = {4'd0,Y,3'd0};   
3'd5 : {I0,I1,I2,I3,I4,I5,I6,I7} = {5'd0,Y,2'd0};  
3'd6 : {I0,I1,I2,I3,I4,I5,I6,I7} = {6'd0,Y,1'd0};   
3'd7 : {I0,I1,I2,I3,I4,I5,I6,I7} = {7'd0,Y};   
endcase     
end   
endmodule   


## Timing Diagram





















## Hardware implementation on Nexys 4


