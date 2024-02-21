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

<details>
    <summary> TASK 2 </summary>
  1.To create a block diagram of the project  

  2.Identifying input ports,output ports and input waveform,output waveform
   
</details>
