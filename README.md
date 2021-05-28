# Simple EtherCAT Slave Driver Block SFunction for Raspberry Pi
The example Simple EtherCAT Slave Driver Block SFunction for Raspberry Pi shows basic usage of the SOES library by transferring 32 bytes of input and output PDO data.

Uses fork of SOES library that adds support for EtherCAT slave HAT with LAN9252 chip (like EasyCAT or EtherC/EtherBerry) for Raspberry Pi using the BCM2835 library.

Usage instructions:
1. Download the bcm2835 library from https://www.airspayce.com/mikem/bcm2835/ and do following installation substeps.
   - Build the bcm2835 library on the Raspberry Pi hardware using the instructions on https://www.airspayce.com/mikem/bcm2835/.
   - Copy libbcm2825.a from the build folder to the map of this simulink model.
1. Download forked SOES library from  https://github.com/iwoodsawyer/SOES/ and unpack SOES library to the same map of this simulink model. Compiled SOES library for Raspbian is already included, but for other OS than Raspbian the SOEM library should be recompiled with following substeps.
   - (Optional) Build the soes library on the Raspberry Pi hardware using the instructions on https://github.com/iwoodsawyer/SOES/
   - (Optional) Change settings in SOES\applications\raspberry_lan9252demo\ecat_options.h and utypes.h.
   - (Optional) Copy libsoes.a and changed header files from the build folder to the map of this simulink model.
4. Open Simulink model "soes_ethercat_slave.slx".
4. Open the EtherCAT Slave block, and in the "Libraries" tab adjust the INC_PATHs to the correct paths of the SOES include folders and libraries.
5. Build the SOES_raspberrypi Sfunction.
6. Deploy the model to the Raspberry Pi hardware.