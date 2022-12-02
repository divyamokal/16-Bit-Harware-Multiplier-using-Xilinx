# 16-Bit-Harware-Multiplier-using-Xilinx
In this project, I have created a 16 bit hardware multiplier in a software ie. Xilinx. It takes any 16 Bit binary number and the processes the output in the form of product of two numbers

`timescale 1ns / 1ps
module Multiplier(a,b,p);
input [15:0]a,b;

wire [15:0]m0;
wire [16:0]m1;
wire [17:0]m2;
wire [18:0]m3;
wire [19:0]m4;
wire [20:0]m5;
wire [21:0]m6;
wire [22:0]m7;
wire [23:0]m8;
wire [24:0]m9;
wire [25:0]m10;
wire [26:0]m11;
wire [27:0]m12;
wire [28:0]m13;
wire [29:0]m14;
wire [30:0]m15;


wire [31:0]s1,s2,s3,s4,s5,s6,s7,s8,s9,s10,s11,s12,s13,s14,s15;
output [31:0]p;

assign m0 = {16{a[0]}} & b[15:0];
assign m1 = {16{a[1]}} & b[15:0];
assign m2 = {16{a[2]}} & b[15:0];
assign m3 = {16{a[3]}} & b[15:0];

assign m4 = {16{a[4]}} & b[15:0];
assign m5 = {16{a[5]}} & b[15:0];
assign m6 = {16{a[6]}} & b[15:0];
assign m7 = {16{a[7]}} & b[15:0];

assign m8 = {16{a[8]}} & b[15:0];
assign m9 = {16{a[9]}} & b[15:0];
assign m10 = {16{a[10]}} & b[15:0];
assign m11 = {16{a[11]}} & b[15:0];

assign m12 = {16{a[12]}} & b[15:0];
assign m13 = {16{a[13]}} & b[15:0];
assign m14 = {16{a[14]}} & b[15:0];
assign m15 = {16{a[15]}} & b[15:0];



assign s1 = m0 + (m1<<1);
assign s2 = s1 + (m2<<2);
assign s3 = s2 + (m3<<3);
assign s4 = s3 + (m4<<4);
assign s5 = s4 + (m5<<5);
assign s6 = s5 + (m6<<6);
assign s7 = s6 + (m7<<7);

assign s8 = s7 + (m8<<8);
assign s9 = s8 + (m9<<9);
assign s10 = s9 + (m10<<10);
assign s11 = s10 + (m11<<11);
assign s12 = s11 + (m12<<12);
assign s13 = s12 + (m13<<13);
assign s14 = s13 + (m14<<14);
assign s15 = s14 + (m15<<15);

assign p = s15;

endmodule



`timescale 1ns / 1ps


module TestBench;

	// Inputs
	reg [15:0] a;
	reg [15:0] b;

	// Outputs
	wire [31:0] p;

	// Instantiate the Unit Under Test (UUT)
	Multiplier uut (
		.a(a), 
		.b(b), 
		.p(p)
	);
	initial begin
		a = 16'b1100000111000001;
		b = 16'b1100001011000010;
	end
endmodule
