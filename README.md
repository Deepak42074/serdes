 # Serdes

Serdes(Serializer/Deserializer) is a functional block  which provide high speed data transmission from one chip to another or within chip. It provides data transmission over single line or differential pair in order to minimize number of input-output pins and interconnects .

Serializer converts low speed parallel stream of data into high speed serial  LVDS(Low volatge Differential Signaling) data stream and transmit the serial stream of data over a high speed connection to the receiver (Deserializer) which converts the serial data stream back to parallel stream of data.Inshort serializer functional block performs PISO(Parallel In Serial Out) and deserializer functional block performs SIPO(Serial In Parallel Out) operation.


# Table of Contents  
- [Serdes Block Diagram](#Serdes-Block-Diagram)  
- [Serializer](#Serializer)  
- [Serializer Timing Diagram](#Serializer-Timing-Diagram)
- [Input CML latch ](#Input-CML-latch)
- [CML latch Timing Diagram](#CML-latch-Timing-Diagram)
- [PISO Register](#PISO-Register)
- [Phase Locked Loop](#Phase-Locked-Loop)
- [LVDS driver](#LVDS-driver)
- [Future Work](#future-work) 
- [Author](#Author)
- [Acknowledgements](#Acknowledgements)  
- [Contact Information](#Contact-information) 

## Serdes Block Diagram
Basic block diagram of serdes is shown below:

![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/serdes.png)

## Serializer:
The main function of serializer is to transform LVTTL/LVCMOS parallel input data stream into serial high speed LVDS data stream which can be transmitted at high speed electrical interface.
The serializer functional block has following internal blocks:

<dl>
    <dd> 1. Input CML latch </dd>
    <dd> 2. PISO shift register </dd>
    <dd> 3. Phase locked loop </dd>
    <dd> 4. LVDS output driver </dd>
</dl>

The  block Diagram of Serializerfor 4-bit parallel data stream is shown below:


![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/Serializer_Block_Diagram.png)

## Serializer Timing Diagram:

This timing diagram shows parallel to serial conversion till input of LVDS(excluding LVDS output):

![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/serializer_timing.png)


## Input CML latch 
A CML(Current Mode Logic) latch consists of an input data tracking stage(using MOSFETS M1 and M2) which sense and track data variation and a regenerative cross-coupled pair (using MOSFETS M3amd M4) used to store the data.The track and latch modes are determined by the clock signal inputs to second differential pair(MOSFET M5 and M6).
The sampling/tracking pair works as a CML buffer and when it is activated by the clock "HIGH" signal , it tracks the input data and transfers it to the outputs. This is known as the sampling mode of the latch. The hold pair becomes active when  the clock polarity changes to " LOW" . The cross-coupled transistors in the latch pair form a regenerative positive feedback structure which retains the output data at the current state.
<!-- When CLK is HIGH ,the tail current flows completely through the tracking circuit, thereby allowing Vout to track Vin(Tracking pair works as CML buffer. In the latch-mode, when the signal CLK goes low, the tracking stage is disabled, whereas the latch pair is enabled storing the logic state at the output.The output of latch remains same till CLK is low.-->

The block diagram of conventional CML latch circuit is shown below :

![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/Conventional_CML_Latch.png)

## CML latch Timing Diagram:

![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/CML_latch_timing.png)

## PISO Register
Parallel-in serial-out (PISO ) shift register loads data parllely in all registers and shift serially on clock by clock basis.Parallel data is loaded in D-FF and it is shifted serially with the hwlpp of 2:1 MUX which is controlled by shift/load bar line.When shift/load bar is "0" data is loaded parallely in all registers and when shift/load bar is "1"
data is shifted serially from LSB to MSB and serial output is taken at MSB.
Below diagram shows parallel to serial conversion diagram of 4-bit parallel data.

![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/PISO.png)

## Phase Locked Loop
The phase locked loop take in a signal to which it locks and can then output this signal from its own internal VCO.PLL is locked at the input reference clock.It is a feedback mechanism by which phase error between a input and locally generated signal is minimized. Here PLL is used to generate high frequency clock output for given input clock. The frequency of output clock to PLL which will be transmitted is same as frequency of input clock.

## LVDS driver
LVDS transmitters are designed for high speed applications requiring minimum power consumption,space and noise.It accepts LVTTL/LVCMOS input and translates them to low voltage differential output minimizing electomagnetic interference and power dissipation.The differential output tansition depends on output load capacitance (CL) and load resistance(RL)  matched to transmission line.

Below diagram shows LVDS differential output and corresponding waveform:

![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/LVDS.png)

LVDS Propagation delay and transition time waveform:
![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/LVDS_waveform.png)



## Future Work
* To specify CML Latch, Control Logic, PLL,LVDS  and complete serializer specifications.

## Author
* Deepak verma

## Acknowledgements  
* Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.

## Contact Information  
* Deepak verma ,B.Tech(Electronics and Communication),IIIT Sonepat -deepak074.verma@gmail.com
* Kunal Ghosh, Director, VSD Corp. Pvt. Ltd. - kunalghosh@gmail.com











