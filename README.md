# SIMD-Processor-using-OpenLane
Application-Specific Integrated Circuit (ASIC) implementation of 16 bit SIMD processor

The Verilog source code used for this project was implemented by Tingyuan LIANG:\ https://github.com/zslwyuan/Basic-SIMD-Processor-Verilog-Tutorial

## SIMD Architecture
SIMD stands for Single Instruction, Multiple Data. It is a parallel computing architecture where a single instruction is applied to multiple data elements simultaneously, enabling efficient processing of large datasets. The core of the processor is a 16 bit SIMD ALU with three basic computation units: SIMD adder, SIMD multiplier and SIMD shifter. 
The ALU operation will take two clocks. The first clock cycle will be used to load values into the registers. The second will be for performing the operations. There are 48 operations supported by the processor consisting of 18-bit instructions with 6 bit opcode.

![image](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/assets/97625007/0022a4f2-7ed1-4f8c-b4b5-154f7444c079)

## Source code
### Verilog modules
- [src/simd.v](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/25f1564c557ffd2edaf65dd7780281489e60535e/src/simd.v)
- [src/SIMDadd.v](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/25f1564c557ffd2edaf65dd7780281489e60535e/src/SIMDadd.v)
- [src/SIMDmultiply.v](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/25f1564c557ffd2edaf65dd7780281489e60535e/src/SIMDmultiply.v)
- [src/SIMDshifter.v](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/25f1564c557ffd2edaf65dd7780281489e60535e/src/SIMDshifter.v)

![WhatsApp Image 2024-03-19 at 15 46 19_8075aee1](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/assets/97625007/56b5c73e-32e8-4a2e-a5ae-1b8fe718a1e4)

### SDC file
- [src/simd.sdc](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/10ec341aa3fb616f1912017e0a281f5f38f2968d/src/simd.sdc): Declared clock period as 16.5ns

<img width="480" alt="sdc file" src="https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/assets/97625007/911b0ff5-acc7-4aee-9a95-b26a323f0ebf">

## OpenLane flow
- [init/pin_order.cfg](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/c3e9fc8553d93cbd47e3d529deb13c69b487363e/init/pin_order.cfg)
: The pin_order file decides the placement of input-output pins at the periphery of the floorplan

- [init/config.json](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/c3e9fc8553d93cbd47e3d529deb13c69b487363e/init/config.json)
: The configuration parameters are declared using the config.json file. These parameters help in exploring various designs. We observe a trade-off between power, area and delay at various stages of OpenLane execution depending on the parameters declared

## Results
- [report/multi_corner_sta.power.rpt](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/c3e9fc8553d93cbd47e3d529deb13c69b487363e/report/multi_corner_sta.power.rpt)
: The power report obtained after the signoff shows the power consumed for multiple corners

- [report/multi_corner_sta.summary.rpt](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/c3e9fc8553d93cbd47e3d529deb13c69b487363e/report/multi_corner_sta.summary.rpt)
: The STA report gives the summary about the setup time and hold time slack

- [gds/simd.gds](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/blob/c3e9fc8553d93cbd47e3d529deb13c69b487363e/gds/simd.gds)
: We obtain the GSDII file using KLayout

![WhatsApp Image 2024-03-25 at 20 06 38_a218b3d9](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/assets/97625007/144aee75-8920-4f95-9419-b37245aed862)

The layout can also be viewed using gui.py:

![WhatsApp Image 2024-03-25 at 21 16 27_766947d9](https://github.com/jalakjk13/SIMD-Processor-using-OpenLane/assets/97625007/4fd48034-c457-413a-a8f5-5c127968339c)

## Errors and fixes




