hdmilight
=========

[2016-03-23] This repo has been obsolete for a long time.

Go to http://hacks.esar.org.uk/hdmi-light-v2/ and https://github.com/esar
*************************


Papilio FPGA HDMI Ambilight project forked from http://hacks.esar.org.uk/hg/hdmilight/file/tip/

For latest version, go to http://hacks.esar.org.uk/hdmi-light/

How to use:

1) Manufacture the HDMI receiver board that can be found in the 'board' directory (CADSoft Eagle format)

2) Open the 'fpga/hdmilight.xise' project in Xilinx ISE

2a) Regenerate the IP cores: in the Hierarchy panel, expand the tree and select the conf, line_buffer and resultBuffer entries one by one and run the "Regenerate Core" process in the panel below

2b) Generate the bit file

3) Edit 'firmware/config_lights.h' to set light definitions

4) Edit 'Makefile' in the top level directory and set the DATA2MEM path for the Xilinx data2mem tooli location on your system

5) Run 'make' in the top level directory, which will build 'tools/makemem', then the firmware image, then merge the firware image into the fpga bitfile. The final result should be hdmilight.bit in the top level directory

6) Upload hdmilight.bit to a Papilio One 250K FPGA board

7) Install the HDMI receiver board on to the Papilio board

8) Connect LED strips to output pins

9) Open a serial terminal to the Papilio

10) Give the command to initialise I2C: I I
   
11) Give the command to configure the light definitions and the ADV611 chip: I C

12) Connect HDMI source to receiver board

13) It should now be working
