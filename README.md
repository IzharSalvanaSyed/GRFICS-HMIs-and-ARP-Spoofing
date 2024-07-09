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
If you havent started up yout Kali Linux VM, this would be the time to start it up, the login is "kali" and "kali.". The first thing we are gonna try to do as an attacker is find the IP address of the PLC. We as an attacker expect that the PLC is communicating with an HMI. Since we are already in the same DMZ subnet as the HMI we just need to sniff out the IP address of the PLC. We will be performaing an attack known as ARP spoofing to intercept traffice that is intended for the HMI and then sniff the traffic to try to find the IP address of the PLC.  

Since we already know the IP address of the HMI that we are trying to spoof is "192.168.90.5"

Open a terminal in the Kali VM.  
Type sudo arpspoof "192.168.90.5"  
if prompted to input a password type in "kali"  
We should be now recieving packets that were intended for the HMI  
![image](https://github.com/IzharSalvanaSyed/GRFICS-HMIs-and-ARP-Spoofing/assets/156041933/0b0447b7-524e-462e-a103-8b0854927b68)

To sniff that traffic we will us a program called Wireshark.  
Go to the top right of the KLI vm, click on the Kali icon  
Hover over "Sniffing & Spoofing," find and open Wireshark
Once Open find "eth0" and click it open  
you should now see a running list of network traffic   
we should be seeing running list of network traffic on this network interface  
we should also see a lot of traffic that is too and from to different IP addresses.
"192.168.90.5" and "192.168.95.2"  
We already know the IP address of the HMI so we can presume that the PLC IP address is "192.168.95.2."

![image](https://github.com/IzharSalvanaSyed/GRFICS-HMIs-and-ARP-Spoofing/assets/156041933/8a5d8cba-8789-44cd-a66f-a300c76b8cf0)
