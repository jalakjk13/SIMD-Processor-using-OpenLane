# SIMD-Processor-using-OpenLane
Application-Specific Integrated Circuit (ASIC) implementation of 16 bit SIMD processor

The Verilog source code used for this project was implemented by Tingyuan LIANG: https://github.com/zslwyuan/Basic-SIMD-Processor-Verilog-Tutorial

## SIMD Architecture
SIMD stands for Single Instruction, Multiple Data. It is a parallel computing architecture where a single instruction is applied to multiple data elements simultaneously, enabling efficient processing of large datasets. The core of the processor is a 16 bit SIMD ALU with three basic computation units: SIMD adder, SIMD multiplier and SIMD shifter. 
The ALU operation will take two clocks. The first clock cycle will be used to load values into the registers. The second will be for performing the operations. There are 48 operattions supported by the processor consisting of 18-bit instructions with 6 bit opcode.

![image](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/assets/97625007/0022a4f2-7ed1-4f8c-b4b5-154f7444c079)


