# BruteForceAttackProject (!!IN PROCESS!!)



<h1>EDR (Endpoint Detection Response) with LimaCharlie</h1>

<h2>Lab Objective</h2>
Build a victim machine by disabling Microsoft Defender to make the system vulnerable. Then compromised the victim machine with a C2 exploitation framework “SLIVER”. Set up LimaCharlie, an EDR (Endpoint Detection Response) and configure Sysmon on the victim machine. See victim get compromised in LimaCharlie and then write a detection & response rule to detect and BLOCK attack.<br />

<h2>Environments Used </h2>

- <b>VMWare Workstation</b>
- <b>Windows VM</b>
- <b>Linux (Ubuntu Server)</b>
- <b>LimaCharlie</b>
- <b>Create detections rule</b>
- <b>Trigger YARA scans with a detection rule</b>
- <b>Block attack</b>

<h2>Project Overview </h2>

- <b>Setting Up Virtual Environment</b>

1. Download and installed VMWare workstation ISO.<br/>
2. Downloaded Windows VM and Ubuntu Server ISO.<br/>
3. Deploy Windows VM and Ubuntu Server on VMWare workstation.<br/>
 
<img src="https://i.imgur.com/RL488LP.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/UU0fo2L.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/fUzrk4j.png"/>

-----------------------------------------------

A. Set up static IP for VM Workstation so that it doesn’t change throughout the lab or beyond it by copying down Subnet IP and Gateway IP.<br/>
 
<img src="https://i.imgur.com/MS9u42c.png"/>

-----------------------------------------------

4. In the Ubuntu installer change the interface from DHCPv4 to Manual and paste subnet IP and Gateway IP.<br/>

<img src="https://i.imgur.com/3qmrxHh.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/UJI8rMh.png"/>

-----------------------------------------------


<img src="https://i.imgur.com/BZXR2GI.png"/>

-----------------------------------------------

5. Confirm connection after installation is complete.<br/>

<img src="https://i.imgur.com/hpQPz8b.png"/>

----------------------------------------------

<img src="https://i.imgur.com/xXYvEVR.png"/>

----------------------------------------------


- <b>SetUp Windows VM</b>

1. Turn on Windows VM and disable Microsoft Defender in “Manager Settings” Under “Virus & threat protection settings” (this will avoid interference from defender during scans).<br/>
2. Permanently Disable Defender via Group Policy Editor in cmd prompt as administrator.<br>
3. Disable some services via the “Registry Editor”.<br/>

<img src="https://i.imgur.com/aAw83rZ.png"/>

----------------------------------------------
