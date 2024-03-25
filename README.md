# SIMD-Processor-using-OpenLane
Application-Specific Integrated Circuit (ASIC) implementation of 16 bit SIMD processor

The Verilog source code used for this project was implemented by Tingyuan LIANG: https://github.com/zslwyuan/Basic-SIMD-Processor-Verilog-Tutorial

## SIMD Architecture
SIMD stands for Single Instruction, Multiple Data. It is a parallel computing architecture where a single instruction is applied to multiple data elements simultaneously, enabling efficient processing of large datasets. The core of the processor is a 16 bit SIMD ALU with three basic computation units: SIMD adder, SIMD multiplier and SIMD shifter. 
The ALU operation will take two clocks. The first clock cycle will be used to load values into the registers. The second will be for performing the operations. There are 48 operations supported by the processor consisting of 18-bit instructions with 6 bit opcode.

![image](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/assets/97625007/0022a4f2-7ed1-4f8c-b4b5-154f7444c079)

## Source code
### Verilog modules
[src/simd.v](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/25f1564c557ffd2edaf65dd7780281489e60535e/src/simd.v)\
[src/SIMDadd.v](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/25f1564c557ffd2edaf65dd7780281489e60535e/src/SIMDadd.v)\
[src/SIMDmultiply.v](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/25f1564c557ffd2edaf65dd7780281489e60535e/src/SIMDmultiply.v)\
[src/SIMDshifter.v](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/25f1564c557ffd2edaf65dd7780281489e60535e/src/SIMDshifter.v)

![WhatsApp Image 2024-03-19 at 15 46 19_8075aee1](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/assets/97625007/56b5c73e-32e8-4a2e-a5ae-1b8fe718a1e4)

### SDC file
[src/simd.sdc](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/10ec341aa3fb616f1912017e0a281f5f38f2968d/src/simd.sdc)

Declared clock period as 16.5ns

<img width="480" alt="sdc file" src="https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/assets/97625007/911b0ff5-acc7-4aee-9a95-b26a323f0ebf">

## OpenLane flow
The pin_order file decides the placement of input-output pins at the periphery of the floorplan.

The configuration parameters are declared using the config.json file. These parameters help in exploring various designs. We observe a trade-off between power, area and delay at various stages of OpenLane execution depending on the parameters declared.

## Results




## Errors and fixes




