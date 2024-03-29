# A 4-week Research Internship on VSDSquadron Mini RISC-V Dev Board



BOARD SPECIFICATIONS:

| Tech specs   |   |    |
|------------|------------|------------|
| *Board* | Name     | VSDSquadron Mini    |
|      | SKU    | VSDSQM    |
| *Microcontroller*    | CH32V003F4U6 chip with 32-bit RISC-V core based on RV32EC instruction set    |     |
| *USB connector* | USB 2.0 Type-C    |     |
| *Pins*     | Built-in LED Pin     | 1X onboard user led (PD6)     |
|      | Digital I/O pins     | 15     |
|      | Analog I/O pins     | 10-bit ADC, PD0-PD7, PA1, PA2, PC4     |
|      | PWM pins     | 14X     |
|      | External interrupts     | 	8 external interrupt edge detectors, but it only maps one external interrupt to 18 I/O ports     |
| *Communication*     | USART     | 	1x, PD6(RX), PD5(TX)     |
|      | I2C     | 1x, PC1(SDA), PC2(SCL)    |
|      | SPI     | 1x, PC5(SCK), PC1(NSS), PC6(MOSI), PC7(MISO)     |
|      | Programmer/debugger     | Onboard RISC-V programmer/debugger, USB to TTL serial port support     |
| *Power*     | I/O voltage     | 3.3 V    |
|      | Input voltage (nominal)     | 5 V    |
|      | Source Current per I/O Pin    | 8 mA     |
|      | Sink Current per I/O Pin     | 8 mA     |
| *Clock speed*     | Processor    | 24 MHz     |
| *Memory*     | SRAM     | 2kb onchip volatile sram,16kb external program memory     |
   

This repo is intended to document the weekly progress.

### The first online meet was held on 16th of Feb 2024 @6PM

<details>
    <summary> TASK 1 </summary>
 
1) install Yosys 

2) install iverilog 

3) install gtkwave

### CLONING RISC-V GNU TOOLCHAIN

# To install git 
sudo apt install git-all   

 make sure to install the dependencies
![WhatsApp Image 2024-02-20 at 10 52 03_392684c3](https://github.com/NithishaBR/VSD/assets/160307537/97f02e74-b224-426a-8013-386414062ffe)



### INSTALLING YOSYS, IVERILOG & GTKWAVE.

### 1.YOSYS


git clone https://github.com/YosysHQ/yosys.git
![WhatsApp Image 2024-02-20 at 10 52 03_392684c3](https://github.com/NithishaBR/VSD/assets/160307537/771fa1cd-c730-4668-b2b2-96c4dc07c1dc)

cd yosys 

sudo apt install make
![WhatsApp Image 2024-02-20 at 10 52 29_d9ffbd87](https://github.com/NithishaBR/VSD/assets/160307537/2a0b0c00-f8c7-4e0b-a105-f8ad683be71c)
sudo apt-get install build-essential clang bison flex \libreadline-dev gawk tcl-dev libffi-dev git \ graphviz xdot pkg-config python3 libboost-system-dev\libboost-python-dev libboost-filesystem-dev zlib1g-dev

make config-gcc
![gg](https://github.com/NithishaBR/VSD/assets/160307537/36cf9eaa-67a0-40f3-8377-6694ec4d8264)

make 
![12gy](https://github.com/NithishaBR/VSD/assets/160307537/10e20f33-5f4c-489d-b75e-537954cc61ac)

sudo make install
![fyfytfyt](https://github.com/NithishaBR/VSD/assets/160307537/2d09f018-1b0c-49cc-a515-b2fc4c0f1f10)


### 2.iVerilog
installing iVerilog

sudo apt update

sudo apt-get install iverilog
![dydyfytf](https://github.com/NithishaBR/VSD/assets/160307537/9d332c43-6e39-400c-8627-3868f22247e2)


### 3.GTkWave
installing GTkWave

 sudo apt-get install gtkwave 

![WhatsApp Image 2024-02-20 at 10 54 09_968b4260](https://github.com/NithishaBR/VSD/assets/160307537/ae8e253f-59ff-4281-b0f5-1285f021a426)

</details>

### The second online meet was held on 20th of Feb 2024 @6PM
<details>
    <summary> TASK 2 </summary>
  1.To create a block diagram of the project  

  2.Identifying input ports,output ports and input waveform,output waveform

   # Block diagram

   ![im](https://github.com/NithishaBR/VSD/assets/160307537/57ec67dd-8a99-4c6a-be94-9597e2051a15)

</details>

### The Third online meet was held on 22th of Feb 2024 @6PM
<details>
    <summary> TASK 3 </summary>

*Simulating iverilog*

 ```iverilog piso_shift_register.v testbench.v``` 

```./a.out``` 

![n7](https://github.com/NithishaBR/VSD/assets/160307537/d47efd41-105c-40b4-94e8-55768a71d5bc)


*Generating dump_file*

 ```gtkwave dump.vcd```
 
![n8](https://github.com/NithishaBR/VSD/assets/160307537/d8601610-f297-41e9-96cd-78ee1192d66c)



   # Waveform

   ![im1](https://github.com/NithishaBR/VSD/assets/160307537/a99649e3-3eae-4500-b22e-d631a0d2aadd)


   ![wave](https://github.com/NithishaBR/VSD/assets/160307537/c39258c9-a461-4559-8765-2e14f79d1c48)



</details>

### The Fourth online meet was held on 27th of Feb 2024 @6PM

<details>
    <summary> TASK 4 </summary>

*Invoking yosys inside verilog_code file:* 

```yosys```

*Reading the Library:*    

```read_liberty -lib ../../sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.lib```

*Reading the Design:*    

```read_verilog piso_shift_register.v```


*Specifying the module that we are synthesizing:*    

```synth -top piso_shift_register```

![n1](https://github.com/NithishaBR/VSD/assets/160307537/ecb986ad-ae99-481d-9bee-9bff70a92096)

*To generate the netlist:*    

```abc -liberty ../../sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.lib```

*To see the graphical version of the logic:*    

```show```

![n2](https://github.com/NithishaBR/VSD/assets/160307537/03cdad11-b66e-4ac8-92ac-315bde559d05)



*To write the netlist:*    

```write_verilog piso_shift_register_netlist.v```


*Using the switch '-noattr' to get the simplified version of netlist file:*    

```write_verilog -noattr piso_shift_register_netlist.v```

![n3](https://github.com/NithishaBR/VSD/assets/160307537/91d97302-8cfd-4220-9fab-b1078ed5cadf)


*To open the netlist:*    

```!gvim piso_shift_register_netlist.v```

![final netlist](<open netlist.jpg>)

*Opening the netlist file:*

![netlist file](netlist1.jpg)

![netlist file](netlist2.jpg)

*To check whether the netlist will match with the Design:*

 ```iverilog piso_shift_register_netlist.v testbench.v``` 

```./a.out``` 

 ```gtkwave dump.vcd```

 *Netlist waveform*

 
![n4](https://github.com/NithishaBR/VSD/assets/160307537/8eccf282-ee50-473b-a4d8-6f29d1a87a44)

![n6](https://github.com/NithishaBR/VSD/assets/160307537/b33c38ff-e5f4-4fc3-9a41-ad90a0a58170)




</details> 

### The Fifth  online meet was held on First of march 2024 @6PM

<details>
  <summary> TASK 5 </summary>

```iverilog iiitb_pipo.v iiitb_pipo_tb.v``` 

```gtkwave iiitb dump.vcd``` 

![111](https://github.com/NithishaBR/VSD/assets/160307537/93bf8c38-51c1-45d7-add2-df59bda78bb2)

![112](https://github.com/NithishaBR/VSD/assets/160307537/5109489f-4909-45be-9ced-d1b508f48977)



*To generate netlist*

```yosys``` 

![113](https://github.com/NithishaBR/VSD/assets/160307537/0a3f2622-804d-435a-bfe9-d1b20f5ec5bd)



*Reading the library*

![115](https://github.com/NithishaBR/VSD/assets/160307537/f4e98cae-b342-4df0-b333-e77951d179fc)


*Reading the design*

```read_verilog iiitb_pipo.v``` 

*Synthesizing the module*

```synth -top iiitb_pipo``` 

![116](https://github.com/NithishaBR/VSD/assets/160307537/df253ec7-5c70-4b96-8f04-f79dbca5f749)

![117](https://github.com/NithishaBR/VSD/assets/160307537/d3a8f2f0-4d04-45c2-9116-e8bcbb481869)

*To generate the nestlist*

``` abc -liberty /home/nithishabr/vsd/iiitb_pipo1/lib/sky130_fd_sc_hd_tt_025c_1v80.lib``` 

![118](https://github.com/NithishaBR/VSD/assets/160307537/16dc7bb2-4b69-4531-afb7-4cdb73608c7b)

*To write the netlist*


```write_verilog netlist1.v``` 

```write_verilog -noattr netlist1.v``` 


*where -noattr is used to get simplified netlist file*

```flatten``` 

```show``` 


![333](https://github.com/NithishaBR/VSD/assets/160307537/16decd50-544a-426f-84f6-75f878cac0da)

![t76t](https://github.com/NithishaBR/VSD/assets/160307537/bb3198f0-593f-4916-981d-f61ca2220a67)

*To open netlist*

```!gvim netlist.v```

![777](https://github.com/NithishaBR/VSD/assets/160307537/29e16e32-ff1b-4b87-9fdc-6d6888d0f7b7)

*Opening the netlist file*

![999](https://github.com/NithishaBR/VSD/assets/160307537/1cee06f1-b6f3-4636-a65a-1378abf319c1)


*To verify whether netlist will match with the design*

```iverilog ../iiitb_pipo/verilog_model/primitives.v ../iiitb_pipo/verilog_model/sky130_fd_sc_hd.v netlist1.v iiitb_pipo_tb.v```

```./a.out``` 

![000](https://github.com/NithishaBR/VSD/assets/160307537/b82f933e-c9d9-46d0-9b5b-331df065b123)


```gtkwave dump.vcd```

![8989](https://github.com/NithishaBR/VSD/assets/160307537/d9b25360-d8aa-483d-921e-b9c151748c44)

![9900](https://github.com/NithishaBR/VSD/assets/160307537/61d94873-25cd-452d-ae96-05f8a9b3ec7d)


</details>
