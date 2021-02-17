# serdes

Serdes(Serializer/Deserializer) is a functional block  which provide high speed data transmission from one chip to another or within chip. It provides data transmission over single line or differential pair in order to minimize number of input-output pins and interconnects .

Serializer converts low speed parallel stream of data into high speed serial  LVDS(Low volatge Differential Signaling) data stream and transmit the serial stream of data over a high speed connection to the receiver (Deserializer) which converts the serial data stream back to parallel stream of data.Inshort serializer functional block performs PISO(Parallel In Serial Out) and deserializer functional block performs SIPO(Serial In Parallel Out) operation.


# Table of Contents  
- [Serdes Block Diagram](#Serdes-Block-Diagram)  
- [Serializer](#Serializer)  
- [Future Work](#future-work) 
- [Author](#Author)
- [Acknowledgements](#Acknowledgements)  
- [Contact Information](#Contact-information) 

# Serdes Block Diagram:


# Serializer:
The main goal of serializer is to convert input parallel data stream into serial data stream which can be transmitted at high speed electrical interface.
The serializer functional block has following internal blocks:

<dl>
    <dd> 1.Input CML latch </dd>
    <dd> 2.PISO shift register </dd>
    <dd> 3.Phase locked loop </dd>
    <dd> 4.LVDS output driver </dd>
</dl>
Below is the Serializer block Diagram for 4-bit parallel data stream:

![](https://github.com/Deepak42074/serdes/blob/main/Diagrams/Serializer_Block_Diagram.png)

## Input CML latch 
A CML(current mode logic) latch consists of an input data tracking stage(using MOSFETS M1 and M2) which sense and track data variation and a regenerative cross-coupled pair (using MOSFETS M3amd M4) used to store the data.The track and latch modes are determined by the clock signal inputs to second differential pair(MOSFET M5 and M6).
When CLK is HIGH ,the tail current flows completely through the tracking circuit, thereby allowing Vout to track Vin. In the latch-mode, when the signal CLK goes low, the tracking stage is disabled, whereas the latch pair is enabled storing the logic state at the output.The output of latch remains same till CLK is low.

* Block Diagram











## Waveforms:



# Future Work
* 

# Author
* Deepak verma

# Acknowledgements  
* Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.


# Contact Information  
* Deepak verma ,B.Tech(Electronics and Communication),IIIT Sonepat -deepak074.verma@gmail.com
* Kunal Ghosh, Director, VSD Corp. Pvt. Ltd. - kunalghosh@gmail.com











