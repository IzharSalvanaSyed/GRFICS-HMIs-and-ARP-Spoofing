# GRFICS-HMIs-and-ARP-Spoofing
Learn about Human Machine Interface (HMI) in ICS networks and how to sniff ICS traffic from them using ARP spoofing attacks.

### Table of contents

1. [Introduction](#introduction)
2. [Getting Started](#starting)
3. [Software Installation](#software)
4. [VirtualBox networking](#network)
5. [Human Machine Interface](#hmi)
6. [placeholder](#summary)

## Introduction <a name="introduction">


## Getting Started <a name="starting">   

## Software installation <a name="software">

## VirtualBox networking <a name="network">

![Screenshot 2024-07-08 174357](https://github.com/IzharSalvanaSyed/GRFICS-HMIs-and-ARP-Spoofing/assets/156041933/abc62498-9fdb-42c0-8102-adb12de71d83)

## Human Machine Interface <a name="hmi">
After everything is installed and set up Start up all the VM's. For the best Boot order PfSense, PLC, WorkStation (optional for this Exercise), ScadaBR, ChemicalPlant, and Kali Linux (this doesnt matter where in the boot order). The reason for this boot order is Pfsense sets up the network the virutal environment will need, PLC (Programmable Logic Controller) sends the information for ScadaBR (HMI) to work, and ChemicalPlant  is the Virtual Plant that shows the HMI working in the inudstrial environment.  

Open a web browser and navigate to the the web address that ScadaBR is pointing to "192.168.90.5." The password and login will be "admin" and "admin." Once you are logged in you will see a human machine interface or HMI. An HMI allow an operator to monitor and or control an industrial process through a graphical user interface. What we see on ScadaBR is valve positions, flow rates, tank pressure, and etc. ScadaBR also serves as a historian. A historian is a device that records values of data points in the process. To view historical data from ScadaBR, click on the eye located on the top right of the webapage. On the bottom of right of the webpage click to check mark "Inception" and then click on the triangle pointing to the right next to it, over time it will generate a graphical chart show those data points.  

While the HMI provides a way for operators to interface with an ICS process, but it does not control the process. The acuators and sensors in the process are read and controlled by the programmable logic controller (PLC). The PLC communicates information back and forth with the HMI. Image below shows, the ScadaBR VM (HMI) talking the web browser and the PLC is talking to the ScadaBR and the PLC is talking to the ICS process emulated in the ChemicalPlant VM.
![Capture](https://github.com/IzharSalvanaSyed/GRFICS-HMIs-and-ARP-Spoofing/assets/156041933/247eafd9-b66a-4eef-9083-22b45804283d)

## ARP spoogfing <a name="spoofing">
