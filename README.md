# Serdes

Serdes(Serializer/Deserializer) is a functional block  which provide high speed data transmission from one chip to another or within chip. It provides data transmission over single line or differential pair in order to minimize number of input-output pins and interconnects .

Serializer converts low speed parallel stream of data into high speed serial  LVDS(Low volatge Differential Signaling) data stream and transmit the serial stream of data over a high speed connection to the receiver (Deserializer) which converts the serial data stream back to parallel stream of data.Inshort serializer functional block performs PISO(Parallel In Serial Out) and deserializer functional block performs SIPO(Serial In Parallel Out) operation.


# Table of Contents  
- [Serdes Block Diagram](#Serdes-Block-Diagram)  
- [Serializer](#Serializer)  
- [Serializer Timing Diagram](#Serializer-Timing-Diagram)
- [Input CML latch ](#Input-CML-latch)
- [CML latch Timing Diagram](#CML-latch-Timing-Diagram)
- [Future Work](#future-work) 
- [Author](#Author)
- [Acknowledgements](#Acknowledgements)  
- [Contact Information](#Contact-information) 

## Serdes Block Diagram:
The below serdes diagram is taken from Maxim Integrated MAX9205 10-bit bus LVDS serializer:

![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/serdes.png)


## Serializer:
The main function of serializer is to convert input parallel data stream into serial data stream which can be transmitted at high speed electrical interface.
The serializer functional block has following internal blocks:

<dl>
    <dd> 1. Input CML latch </dd>
    <dd> 2. PISO shift register </dd>
    <dd> 3. Phase locked loop </dd>
    <dd> 4. LVDS output driver </dd>
</dl>
Below is the Serializer block Diagram for 4-bit parallel data stream:


![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/Serializer_Block_Diagram.png)

## Serializer Timing Diagram:

This timing diagram shows parallel to serial conversion till input of LVDS(excluding LVDS output):

![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/serializer_timing.png)


## Input CML latch 
A CML(Current Mode Logic) latch consists of an input data tracking stage(using MOSFETS M1 and M2) which sense and track data variation and a regenerative cross-coupled pair (using MOSFETS M3amd M4) used to store the data.The track and latch modes are determined by the clock signal inputs to second differential pair(MOSFET M5 and M6).
The sampling/tracking pair works as a CML buffer and when it is activated by the clock "HIGH" signal , it tracks the input data and transfers it to the outputs. This is known as the sampling mode of the latch. The hold pair becomes active when  the clock polarity changes to " LOW" . The cross-coupled transistors in the latch pair form a regenerative positive feedback structure which retains the output data at the current state.
<!-- When CLK is HIGH ,the tail current flows completely through the tracking circuit, thereby allowing Vout to track Vin(Tracking pair works as CML buffer. In the latch-mode, when the signal CLK goes low, the tracking stage is disabled, whereas the latch pair is enabled storing the logic state at the output.The output of latch remains same till CLK is low.-->

Below is the block diagram of conventional CML latch circuit:

![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/Conventional_CML_Latch.png)

## CML latch Timing Diagram:

![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/Latch_timing.jpg)



## Future Work
* To specify CML Latch  and serializer specifications.

## Author
* Deepak verma

## Acknowledgements  
* Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.

## Contact Information  
* Deepak verma ,B.Tech(Electronics and Communication),IIIT Sonepat -deepak074.verma@gmail.com
* Kunal Ghosh, Director, VSD Corp. Pvt. Ltd. - kunalghosh@gmail.com











