<h1>Brute Force Attack Project</h1>

<h2>Lab Objective</h2>
Build a network enviorment to produce a brutefrce attack on a victum machine. Will be using Active Directory to create user accounts that will be used as the victum machine, while also using SPLUNK agent to send log events from the Windows server that has Active Dierctiry and Windows 11 VM. Will use Kali Linux as the attacking machine to perform bruteforce attack to see what kind of telemetery it will produce, along with using Atomic Red Team.<br />

<h2>Environments Used </h2>

- <b>VirtialBox</b>
- <b>Windows Server 2022</b>
- <b>Windows 11</b>
- <b>Kali Linux</b>
- <b>Active Directory</b>
- <b>SPLUNK</b>
- <b>Sysmon</b>
- <b>BruteForceAttack Script</b>
- <b>AtomicRedTeam</b>


<h2>Project Walk-Through Overview </h2>

<h1>Part 1: Build out a Diagram</h1>


<img src="https://i.imgur.com/wW6qKId.png"/>

-----------------------------------------------

<h1>Part 2:Install VirtualBox and build Virtual Machines inside VirtualBox.</h1>

<b> A. Download and install VirtualBox.</b>

<img src="https://i.imgur.com/X81fGF7.png"/>

----------------------------------------------

<img src="https://i.imgur.com/cdWK6iO.png"/>

----------------------------------------------
<b> B. Download Windows Server 2022 ISO and build VM in VirtualBox.</b>

<img src="https://i.imgur.com/EprVhQU.png"/>

----------------------------------------------

<img src="https://i.imgur.com/MRfUNoH.png"/>

----------------------------------------------

<img src="https://i.imgur.com/oueT1ta.png"/>

----------------------------------------------

<img src="https://i.imgur.com/hMtdHsW.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/F5ObXSb.png"/>

----------------------------------------------

<img src="https://i.imgur.com/9FLruBx.png"/>

----------------------------------------------

<img src="https://i.imgur.com/nkc2PuF.png"/>

-----------------------------------------------
<b> C. Download Windows 10 ISO and create VM in VirtualBox.</b>

<img src="https://i.imgur.com/FLl0sok.png"/>

----------------------------------------------

<img src="https://i.imgur.com/xxbjsc3.png"/>

----------------------------------------------

<img src="https://i.imgur.com/Oae0Efp.png"/>

----------------------------------------------

<img src="https://i.imgur.com/3ArJJZn.png"/>

-----------------------------------------------

<b> D. Download Ubuntu Server ISO and create VM in VirtualBox.</b>


<img src="https://i.imgur.com/7Uk3Kay.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/gGKzkdo.png"/>

----------------------------------------------

<img src="https://i.imgur.com/TtIIJys.png"/>

----------------------------------------------

<img src="https://i.imgur.com/YBY4nYN.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/GNTFyB4.png"/>

-----------------------------------------------

<b> E. Download Pre-built VM for Kali Linux and install in VirtualBox.</b>

<img src="https://i.imgur.com/elS6J6x.png"/>

----------------------------------------------

<img src="https://i.imgur.com/1MC6JAS.png"/>

----------------------------------------------

<img src="https://i.imgur.com/CYZhSy2.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/IO9A3Xx.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/mKqLD26.png"/>

----------------------------------------------

<img src="https://i.imgur.com/QgU1Ty4.png"/>

----------------------------------------------

<img src="https://i.imgur.com/QVHjgpq.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/6Fb2DL3.png"/>

-----------------------------------------------

<h1>Part 3: Install and configure Sysmon & Splunk on Windows target machine and Windows Server. Both Windows machine will collect telemetry and send logs over to Splunk server.</h1>

1. Set networking setting to NAT to have all VMs on the same network for internet access and communciation between VMs. <br/>

<img src="https://i.imgur.com/5ib2M63.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/JjJPDgK.png"/>

-----------------------------------------------

!!!!--- SAME STEP FOR VMs ---!!!! <br/>

<img src="https://i.imgur.com/6IyArOs.png"/>

----------------------------------------------
2. Set up static IP on Splunk Server. <br/>

<img src="https://i.imgur.com/OtDuWRZ.png"/>

----------------------------------------------

<img src="https://i.imgur.com/edFU7Kz.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/1Ub6zYJ.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/GjnIJki.png"/>

-----------------------------------------------
3. Install Splunk by creating an acoount first and than download Splunk Enterprise on host computer. <br/>

<img src="https://i.imgur.com/HmnKQ4L.png"/>

----------------------------------------------

<img src="https://i.imgur.com/Zb9Z30b.png"/>

----------------------------------------------
4. Install "VurtialBox GUEST-ADD-ON" on Splunk VM. <br/>

<img src="https://i.imgur.com/DYPtVHB.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/MN6a2yN.png"/>

----------------------------------------------

<img src="https://i.imgur.com/ZoUKJuC.png"/>

----------------------------------------------

<img src="https://i.imgur.com/nnJH63L.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/BAPXCR5.png"/>

-----------------------------------------------

4. Mount share folder create "AD Project" to the "SHARE" directory created. </br>

<img src="https://i.imgur.com/YbvrCcS.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/pCBrnok.png"/>

----------------------------------------------

<img src="https://i.imgur.com/2mNrkZr.png"/>

----------------------------------------------

<br>5. Install Splunk Fowarder on both (Winodows 10) (Windows Server 2022).</br>
 <br>A. Change PC name and IP address to have Win 10 access the internet.</br>
 
<img src="https://i.imgur.com/zscvWhn.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/T8mYC5G.png"/>

----------------------------------------------

<img src="https://i.imgur.com/YSlAqc6.png"/>

----------------------------------------------

<img src="https://i.imgur.com/2muivnc.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/NIpLeD4.png"/>

-----------------------------------------------

 <br>B.Download Universal Forwarder, Sysmon and, Sysmon olaf config from inside Windows 10 VM.</br>

<img src="https://i.imgur.com/XZaTqrG.png"/>

----------------------------------------------

<img src="https://i.imgur.com/F0vy7bX.png"/>

----------------------------------------------

<img src="https://i.imgur.com/zp1Yew5.png"/>

-----------------------------------------------

 <br>C.Download Sysmon from inside Windows 10 VM.</br>

<img src="https://i.imgur.com/6PiYbW7.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/QWqVC0E.png"/>

-----------------------------------------------

 <br>D.Save sysmon olaf config from github sysmon-modular and run sysmon.exe.</br>

<img src="https://i.imgur.com/gSoCoAX.png"/>

----------------------------------------------

<img src="https://i.imgur.com/oFd0zXw.png"/>

----------------------------------------------

<img src="https://i.imgur.com/tEdGzQE.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/hP2XCee.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/H0JCEVe.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/rrLAMKg.png"/>

----------------------------------------------

<img src="https://i.imgur.com/9aH1t8P.png"/>

----------------------------------------------

<br>E.Configgure file "inputs" under local file in Splunk Forwarder file.</br>

<img src="https://i.imgur.com/GdcKCCb.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/g90eO30.png"/>

-----------------------------------------------

<br>F.restart Splunk universal Fowarder.</br>

<img src="https://i.imgur.com/L7CYdZo.png"/>

----------------------------------------------

<img src="https://i.imgur.com/0epU8hA.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/NSDRtjC.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/IMqJY6p.png"/>

----------------------------------------------

<br>G.Create an index in  Splunk Enterprise.</br>


<img src="https://i.imgur.com/Dt8wuHj.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/GvdTc6l.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/J9v7syO.png"/>

----------------------------------------------

<img src="https://i.imgur.com/rVkiuHO.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/aytD6rz.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/pzrETt2.png"/>

----------------------------------------------

<img src="https://i.imgur.com/GzNJaoI.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/1wfrMGq.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/r6wwtxP.png"/>

----------------------------------------------

<h1>Part 4: Insatll & Configure Active Directory on Windows Server by promoting to a domain controller. Add Windows PC VM to join created domain.</h1> 

A. Set up static IP on Windows server.

<img src="https://i.imgur.com/wtXTsbE.png"/>

-----------------------------------------------

B. Create Active Directory Domain Services.

<img src="https://i.imgur.com/sz5Ts5U.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/farHZw7.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/rYVSBrw.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/sEBdGlC.png"/>

----------------------------------------------

<img src="https://i.imgur.com/iTvXXbR.png"/>

-----------------------------------------------

C. Promote Domain Controlle.

<img src="https://i.imgur.com/wZfiFRZ.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/RftG6zN.png"/>

----------------------------------------------

<img src="https://i.imgur.com/EAtn5zQ.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/9L0Ggcj.png"/>

----------------------------------------------
<img src="https://i.imgur.com/SVf46YH.png"/>

-----------------------------------------------

D. Create organizational unit and users creating users.

<img src="https://i.imgur.com/VDYgTNt.png"/>

----------------------------------------------

<img src="https://i.imgur.com/veLZgqr.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/V3yXLFG.png"/>

----------------------------------------------
<img src="https://i.imgur.com/KtWcJtm.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/jumfypP.png"/>

----------------------------------------------
C. Join Windows 10 pc VM to DOMAIN "Labproject.local".

<img src="https://i.imgur.com/Hh68Pup.png"/>

----------------------------------------------
<img src="https://i.imgur.com/HUm4rZV.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/ezqsp2W.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/jQz3h9G.png"/>

----------------------------------------------
<img src="https://i.imgur.com/57p0fEd.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/Hb7nWIv.png"/>

----------------------------------------------

<h1>Part 5:Use Kali Linux to perform brute force attack on traget machine and use Atomic Red Team on target machine while also viewing all telemeetry via SPLUNK.</h1>

<b/>1. Set up static IP address in Kali Linux and check network connectivity.</b>

<img src="https://i.imgur.com/FtHljLk.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/tygjst8.png"/>

----------------------------------------------
<img src="https://i.imgur.com/A5icd29.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/L8IYXqC.png"/>

----------------------------------------------

<b> 2. Install "Crowbar" and move "rockyou.txt" file to ad-project directory.</b>

<img src="https://i.imgur.com/EXlEJLw.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/JQz3fMj.png"/>

----------------------------------------------

<b> 3. Edit txt file "rockyou" and add password for Windows PC VM.<b>

<img src="https://i.imgur.com/ZZ0Cnh9.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/uKjtv8X.png"/>

----------------------------------------------

<b>4. Enable remoete desktop in Windows PC VM.</b>

<img src="https://i.imgur.com/oTAJkxU.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/kbbxGPt.png"/>

----------------------------------------------

<img src="https://i.imgur.com/jeLU3tQ.png"/>

-----------------------------------------------

<b>5. Run crowbar BRUTE FORCE ATTACK.</b>

<img src="https://i.imgur.com/eN7qIfB.png"/>

----------------------------------------------

<b>6. Access SPLUNK to see what telemetry it created after brute force attack.<b>

<img src="https://i.imgur.com/dZQ2bBY.png"/>

----------------------------------------------

<img src="https://i.imgur.com/54QF2ZY.png"/>

-----------------------------------------------
<b>7. Search event code.</b>

<img src="https://i.imgur.com/93QkvfC.png"/>

----------------------------------------------
<img src="https://i.imgur.com/sskteJF.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/2aOArBL.png"/>

----------------------------------------------
<img src="https://i.imgur.com/JCImsNJ.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/cpqkNkL.png"/>

----------------------------------------------

<b>8. Set up excution Policy and add exclusion to avoid defender scans.</b>

<img src="https://i.imgur.com/0Xl0wL3.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/1vXLwLI.png"/>

----------------------------------------------

<img src="https://i.imgur.com/WaO28Gt.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/1VW2wTE.png"/>

----------------------------------------------
<img src="https://i.imgur.com/MJKop5F.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/DyuaWbX.png"/>

----------------------------------------------

<b>9. Install Atomic Red Team.</b>

<img src="https://i.imgur.com/xKcaLNw.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/4h3uHFg.png"/>

----------------------------------------------

<img src="https://i.imgur.com/IXiGkiD.png"/>

----------------------------------------------

<b>10. Use ATT&CK Matrix to correlate with the list of attomic red team attacks and run attack.</b>

<img src="https://i.imgur.com/cO7NLqv.png"/>

----------------------------------------------

<img src="https://i.imgur.com/uodFXtz.png"/>

----------------------------------------------

<img src="https://i.imgur.com/bHJAerF.png"/>

----------------------------------------------

<img src="https://i.imgur.com/9DGDRxd.png"/>

----------------------------------------------

<img src="https://i.imgur.com/Bn7MwcO.png"/>

----------------------------------------------

<b>11. Use SPLUNK to analyze logs with "newlocaluser" created after machine was attacked by creating admin account.</b>

<img src="https://i.imgur.com/NeJ77fr.png"/>

----------------------------------------------

<img src="https://i.imgur.com/TkvQLIj.png"/>

