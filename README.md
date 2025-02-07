<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this project, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create Virtual Machines
- Observe ICMP Traffic
- Configure NSGs
- Observe Network Traffic

<h2>Actions and Observations</h2>

![Screenshot 2025-02-06 140754](https://github.com/user-attachments/assets/92505c52-815e-4cad-aeee-d096750203a2)

<p>
Using Azure, we create VMs under the same virtual network. We install Wireshark to view the activity.
</p>

![icmp traffic](https://github.com/user-attachments/assets/078a3e7b-04c5-4832-9722-3c100e85b050)


<p>
To observe ICMP traffic, we ping our Linux VM and observe the traffic in Wireshark. We run a test to activate a non-stop ping and observe the effects of denying ICMP traffic through NSG settings.
</p>

![nonstop ping](https://github.com/user-attachments/assets/153fb180-1dc9-43da-a73d-1ef4fc01caea)
![denyicmp](https://github.com/user-attachments/assets/f929e9c4-7fa7-47c6-af3a-8c05acfb8511)
![icmp denied](https://github.com/user-attachments/assets/f5d22441-1054-4848-ab39-424413d52163)


<p>
We SSH into our Linux VM and observe SSH traffic on Wireshark.
</p>

![ssh traffic](https://github.com/user-attachments/assets/4de67a33-5fb0-437d-ac04-d461c0157ba8)


<p>
To observe DHCP traffic, we run a script that runs ipconfic /release & ipconfig /renew. Allowing us to observe the discover, offer, request, acknowledge process.
</p>

![using script to change ip and observe traffic](https://github.com/user-attachments/assets/b8d415ad-9c21-40c4-abf5-65535783c2ce)

<p>
We adjust our Wireshark filter to observe DNS, triggering DNS traffic by using nslookup on google.com.
</p>

![dns](https://github.com/user-attachments/assets/866338b8-1c71-4483-8093-6f31933c524c)


