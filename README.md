# GRFICS-HMIs-and-ARP-Spoofing
Learn about Human Machine Interface (HMI) in ICS networks and how to sniff ICS traffic from them using ARP spoofing attacks.

### Table of contents

1. [Introduction](#introduction)
2. [Getting Started](#starting)
3. [Software Installation](#software)
4. [Breadboarding](#breadboard)
5. [Programming with OpenPLC Editor](#openplc)
6. [placeholder](#summary)

## Introduction <a name="introduction">
In this Project, I will use a Raspberry Pi running OpenPLC to create a switch to turn on and off an LED. I will then use Modbus to control the PLC (Raspberry Pi) over the network. I will also use (insert program) to monitor the activity between Modbus and the PLC.

## Getting Started <a name="starting">
We will need a Raspberry Pi, a project breadboard, an LED, a couple of jump wires, a 220 ohm resistor, two push buttons, and a computer. I bought this from Amazon as it had all the necessary items.   

## Software installation <a name="software">

## VirtualBox networking <a name="network">

## HMI and ARP Spoofing <a name="software">
After everything is installed and set up Start up all the VM's. For the best Boot order PfSense, PLC, WorkStation (optional for this Exercise), ScadaBR, ChemicalPlant, and Kali Linux (this doesnt matter where in the boot order). The reason for this boot order is Pfsense sets up the network the virutal environment will need, PLC (Programmable Logic Controller) sends the information for ScadaBR (HMI) to work, and ChemicalPlant  is the Virtual Plant that shows the HMI working in the inudstrial environment.  
Open a web browser and navigate to the the web address that ScadaBR is 
