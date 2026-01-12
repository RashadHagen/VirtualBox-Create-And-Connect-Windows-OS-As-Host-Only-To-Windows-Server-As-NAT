<h1>VirtualBox – How To Create And Connect Windows OS As Host-Only To Windows Server As NAT</h1>


<h2 style="font-family: Arial, sans-serif; font-size: 20px; font-weight: bold; margin-top: 24px; margin-bottom: 12px;">
⏹️ Description</h2>

<p style="font-family: Georgia, serif; font-size: 16px; margin-top: 12px; margin-bottom: 12px;">
This project addresses the need to create a fully functional environment that accurately simulates an enterprise Windows domain network using virtualized infrastructure. The task is to configure Windows Server 2025 and Windows 11 Pro virtual machines in VirtualBox to establish domain services, internal networking, and controlled internet access. In this project, you will configure VirtualBox host-only and NAT networking, assign static IP addressing, and establish internal and external network segmentation, then install and configure Active Directory Domain Services, DNS, DHCP, and Routing and Remote Access Services to enable domain control and NAT-based internet routing for client systems. You will complete server role installations, promote the server to a domain controller, configure DHCP scopes and routing options, and validate connectivity between Windows Server 2025 and Windows 11 Pro within the virtual domain. The completed environment provides a stable, enterprise-style domain network where Windows 11 clients authenticate to a Windows Server 2025 domain controller, resolve DNS internally, receive IP addressing via DHCP, and access the internet through NAT.
</b>



<h2 style="font-family: Arial, sans-serif; font-size: 20px; font-weight: bold; margin-top: 24px; margin-bottom: 12px;">
⏹️ Utilities Used</h2>
  
<p style="font-family: Georgia, serif; font-size: 16px; margin-top: 12px; margin-bottom: 12px;">
 
 - <b>VirtualBox 7.0.26, Server Manager, Command Prompt, PowerShell</b>



<h2 style="font-family: Arial, sans-serif; font-size: 20px; font-weight: bold; margin-top: 24px; margin-bottom: 12px;"> 
⏹️ Environments Used </h2>

<p style="font-family: Georgia, serif; font-size: 16px; margin-top: 12px; margin-bottom: 12px;">
 
- <b>VirtualBox, Windows Server 2025, Windows 11 Pro</b>



<h2 style="font-family: Arial, sans-serif; font-size: 20px; font-weight: bold; margin-top: 24px; margin-bottom: 12px;"> 
<h2>
⏹️ Project Walk-Through:</h2>
 <br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	NOTE: Install Windows Pro edition!  If you install Home, it cannot connect to Windows Server..</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	NOTE: After all this is setup, to get internet to work on your Windows 11 virtual machine, you will have to have your Windows Server 2025 virtual machine open, too.  Since, the internet to Windows 11 is coming from Windows Server 2025.</b></span>  
<br/><br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>VIRTUALBOX – NETWORK SETUP</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Open: VirtualBox.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/SgjlYjH.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Click: File (top-left).  Hover your mouse over: Tools (between: Export Applicance... and Check for Updates).  Click: Expansion Pack Manager.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/2kr2zrm.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/RM2d29t.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/zI1JtVq.png" height="100%" width="100%" /></td>
  </tr>

<table>
  <tr>
    <td><img src="https://imgur.com/jf2c4hf.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Click: Oracle VM VirtualBox Extension Pack.  Click: Install.  It will open the File Explorer box for your computer, Select: The VirtualBox Extension Pack file.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/dLmoell.png" height="50%" width="50%" /></td>
    <td><img src="https://imgur.com/UWcXRd2.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/eCT1HGi.png" height="50%" width="50%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/g5Vpgnq.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Open VirtualBox.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/s8mnoBs.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>TWO OPTIONS BELOW TO GET TO TOOLS NETWORK MANAGER IN VIRTUALBOX:</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>1. Click: File (top-left, next to: Machne).  Hover your mouse over: Tools (between: Export Applicance... and Check for Updates).  Click: Network Manager (between: Virtual Media Manager and Cloud Profile Manager).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/5Vn9mRj.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/NWk0BRO.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/S1ceQqv.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br />

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>OR</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>2. Click: Tools (above your virtual machines.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/mI3GZ29.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/bICjGd8.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Make sure you are in the Host-only Networks tab (top-middle, next to: NAT Networks, below: Create, Remove, and Properties).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/fm6ib8X.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/G0yJVlU.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/WNoUWAb.png" height="50%" width="50%" /></td>
    <td><img src="https://imgur.com/UluebBO.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Click: Adapter tab (bottom-middle, next to: DHCP Server tab), Click and Select: Configure Adapter Manually, Type: IPv4 Address: 10.0.0.1, and IPv4 Network Mask: 255.255.255.0.  Click: DHCP Server tab (bottom-middle, next to: Adapter tab), Uncheck: Enable Server box.  Click: Apply (very bottom-right).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/Kojp4U6.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/TNEHtGB.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/T2w6hP2.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/4CGxyGQ.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>WINDOWS SERVER 2025 – NETWORK SETUP VIA VIRTUALBOX</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In VirtualBox, Click: Your Windows Server 2025 virtual machine.  Click: Network (a new Settings window will open up).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/OXGAzI5.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/7MfJMXb.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/zGcd0HS.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/PNCJqBH.png" height="500%" width="500%" /></td>
    <td><img src="https://imgur.com/XOdMhaF.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/d0k6TQ0.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Under Adaptor 1 tab, Make sure that this box is Checked: Enable Network Adapter.  Make sure that in the Attached to row, Select: NAT.  Make sure this box is Checked: Cable Connected.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/CI661mr.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/72GDTPP.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Under Adapter 2 tab, Check Box: Enable Network Adapter.  In the Attached to row, Select: Host-only Adapter.  In the Promiscuous Mode box, Select: Allow All.  Make sure this box is Checked: Cable Connected.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/nfSdXN7.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/A3fcRvW.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Click: OK (very bottom-right).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/rMysPU3.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You will now see two Network Adapters for the Windows Server 2025 virtual machine.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/gT0AutH.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/ErK8AxW.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>WINDOWS 11 – NETWORK SETUP VIA VIRTUALBOX</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In VirtualBox, Click: Your Windows 11 virtual machine.  Click: Network (a new Settings window will open up).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/QqgrXFZ.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/1qwIxEg.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/onHMEJ1.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/SJVcrsQ.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/fp2DhFU.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/dRda8lu.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Under Adaptor 1 tab, Make sure that this box is Checked: Enable Network Adapter.  In the Attached to row, Select: Host-only Adapter.  In the Promiscuous Mode box, Select: Allow All.  Make sure this box is Checked: Cable Connected.  Click: OK (very bottom-right).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/haa7mzM.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/hTgWSaH.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/SMNUU7H.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>WINDOWS SERVER 2025 – NETWORK SETUP VIA WINDOWS SERVER 2025 VIRTUAL MACHINE</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In VirtualBox, Double-Click and Open: Windows Server 2025 Virtual Machine. Sign-In and Startup: Windows Server 2025.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/x4idycX.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/NL6OEIV.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Right-Click: The network icon (bottom-right). A box will appear, Click: Network and Internet settings.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/GokIBtc.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/bPjVv6x.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/k31NJx0.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Click: Advanced Settings.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/7el86oB.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/TPSz6Jy.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	NOTE: In Advanced network settings, I will rename Adapter 1 (Ethernet) and Network Adapter 2 (Ethernet 2). Adapter 1 will be renamed: External (NAT) and Adapter 2 will be renamed: Internal (Host-Only).</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Click: The Ethernet box (it will dropdown with more options) (under section: Network adapters). In the Rename this adapter row, Click: Rename (far-right).  A new box will appear called: Rename your hardware, Type: The name you want for the Ethernet adapter, then Click: Save (bottom-left). Do the same for Ethernet 2. You will now see both your network adapters are renamed: External (NAT) and Internal (Host-Only).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/HuDotQz.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/XBE4AFu.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/jdWG7Oe.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/kEKnrCH.png" height="50%" width="50%" /></td>
    <td><img src="https://imgur.com/xv9er0g.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/g8rC5lD.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>On the Internal (Host-Only) network adapter, in the: More adapter options row, Click: Edit (far-right).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/d8PN2ob.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/rpSNySR.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/WShXrDe.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A box will pop-up called: (your network adapter name, ie: Internal Host-Only) Properties.  Click: Internet Protocol Version 4 (TCP/IPv4).  Click: Properties (middle-right).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/BtyaXyF.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/OtO52es.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A new box will appear called: Internet Protocol Version 4 (TCP/IPv4) Properties.  Select: Use the following IP address (it will automatically select: Use the following DNS server address).  Type: IP address: 10.0.0.4. Type: Subnet mask: 255.255.255.0. Leave blank: Default gateway: (blank). Type: Preferred DNS: 10.0.0.4.  Click: OK (bottom-right). </b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/2vHFJ5P.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/y7UsOoD.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/bKn11ZH.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You will be taken back to the: (your network adapter name, ie: Internal Host-Only) Properties box.  Click: Close (bottom-right).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/aIgP5Qw.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/fBLMfYu.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You can double-check / verify both adaptors are setup correctly by opening Command Prompt and using command: ipconfig.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/OJVcLsh.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>WINDOWS 11 – NETWORK SETUP VIA WINDOWS 11 VIRTUAL MACHINE</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In VirtualBox, Double-Click and Open: Windows 11 Virtual Machine. Sign-In and Startup: Windows 11.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/QHnpTPN.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/Zvv9WQL.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Right-Click: The no internet connection network icon (bottom-right). A box will appear, Click: Network and Internet settings.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/C71LGWA.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/rSfasAa.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/BPI07Jb.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/lx6pkIo.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A box will pop-up called: Settings, you will be in the tab: Network & internet.  Click: Advanced network settings (very bottom-middle).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/249gecy.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/m4PXqoQ.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Click dropdown box: Ethernet (very top-middle) (under section: Network adapters).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/pvW7PGW.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/WC4FOUX.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the row: Rename this adapter, Click: Rename (far right).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/mdxKtYR.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/50W86qY.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/dTbvNph.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A new box will appear called: Rename your hardware, Type: The new name for the network adapter (ex: Internal (Host-Only).  Click: Save (bottom-left).</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	NOTE: Make sure to name this the exact same name you did for the “Internal” network adapter in Windows Server 2025 (ex: Internal (Host-Only).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/XeYmXQB.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/ooXayDg.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You will go back to the Advanced network settings box, under the section: Network adapters, you will see the new network adapter name: (ex: Internal (Host-Only)).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/DISrfuz.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Open: Control Panel.  Click: Network and Internet.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/xV0Pkwy.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/OrV1QHs.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/DlrXA4k.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Click: Network and Sharing Center.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/McsYI5k.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/8qB6iZA.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Click: Change adapter settings (far-left column, between: Control Panel Home and Change advanced sharing settings).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/47IZkkQ.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/MS3BGO7.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/StHcn6U.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A new box will open called: Network Connections.  Right-Click: The network adapter (ex: Internet (Host-Only)).  Click: Properties (very bottom).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/0YKGzMx.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/pDYPzQD.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/fqRE4BF.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A new box will open called: The name of your network adapter Properties (ex: ex: Internet (Host-Only) Properties).  Click & Highlight: Internet Protocol Version 4 (TCP/IPv4).  Click: Properties.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/tiWk5mD.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/S2fnbop.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/GHPKT8h.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A new box will open called: Internet Protocol Version 4 (TCP/IPv4) Properties.  Select: Use the following IP Address (top) (it will automatically also select: Use the following DNS server addresses).  Type: IP address: 10.0.0.5, Subnet mask: 255.255.255.0, Default gateway: 10.0.0.4, Preferred DNS: 10.0.0.4.  Click: OK (very bottom-right).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/JwCiCWl.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/5OuY6mY.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/qLbN1NL.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/zTGej1X.png" height="100%" width="100%" /></td>
  </tr>
</table>


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You will be taken back to the box: The name of your network adapter Properties (ex: ex: Internet (Host-Only) Properties).  Click: Close (very bottom-right).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/pz1dIJI.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/p811qks.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>WINDOWS SERVER 2025 – INSTALLING ACTIVE DIRECTORY DOMAIN SERVICES (AD DS)</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	NOTE: AD DS – Active Directory Domain Services = manages and stores information about network resources, users, and computers, enabling centralized administration and security.</b></span>  
<br/><br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Open: Server Manager.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/sQ2i9jy.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Click: Add roles and features (via Homescreen or Manage).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/ebPut8O.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A box will popup called: Add Roles and Features Wizard.  In the Installation Type tab, make sure this is Selected: Role-based on feature-based installation.  Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/AoGhpwJ.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/sv2SAuj.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/VZAiRXx.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Server Selection tab, make sure this is Selected: Select a server from the server pool & The Windows Server you want to use.  Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/2RuyM65.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/M3g41hW.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/1vLYgvV.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You will be taken to a window called: Add Roles and Features Wizard, Server Roles tab.  In the Server Roles tab, Select: Active Directory Domain Services.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/JW5rvUN.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/s9leR6d.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A box will pop-up called: Add Roles and Features Wizard.  Click: Add Features.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/8FkXNpb.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/POWcVJU.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You will be taken back to the window called: Add Roles and Features Wizard, Server Roles tab. You will see a checkmark in the box to the left of: Active Directory Domain Services (second picture).  Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/pfmYiYB.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/crjGwv3.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/BxUsJ2L.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Features tab, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/L7NXjqu.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/1VDdSRD.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the AD DS tab, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/D2XsnkF.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/pvCmYZ6.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Confirmation tab, Click: Install.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/h6SYOuY.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/CpHQDAK.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Results tab, you can Click: Close OR Keep the Add Roles and Features Wizard box open, because you can Click: The flag icon in Server Manager (top-right) at any time.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/KzjhBRS.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/cp6gUA4.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/AG9CxVT.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/UDUZlLV.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/NbZxeyZ.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/qY15tqk.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>WINDOWS SERVER 2025 – CONFIGURING ACTIVE DIRECTORY DOMAIN SERVICES (AD DS) AFTER INSTALLING</b></span>  
<br/><br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	DC - Domain Controller = a server that responds to security authentication requests within a computer network domain. It is a network server that is responsible for allowing host access to domain resources. It authenticates users, stores user account information and enforces security policy for a domain.</b></span>  
<br/><br/>

</div>
    <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	Computer Network Domain = a group of computers and network resources that share a common set of rules and can be centrally managed, often using a domain controller to manage user accounts, security policies, and network resources.</b></span>
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	Forest (AD DS) =the highest-level organizational unit in an Active Directory environment.</b></span>  
<br/><br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>After Active Directory Domain Services (AD DS) is installed, you will need to configure it.   Click: The flag icon in Server Manager (top-right) with the yellow triangle with an exclamation point in it.  In the section called: Configuration required for Active Domain Services at (Windows Server name, ex: WIN-K2BF9E7VTHV), Click: Promote this server to a domain controller (below: Configuration required…).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/17ZVcfC.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/8aq5kVM.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A box will pop-up called: Active Directory Domain Services Configuration Wizard.  In the Deployment Configuration tab, Select: Add a new forest.  Type: Root domain name.  Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/rL3wQHf.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/5xSQuPz.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/Kuer4so.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>It will take about 1-2 minutes for the Domain Controller Options tab to be usable (will see a blue streak going across the top of the Active Directory Domain Services Configuration Wizard box). Type: Password.  Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/Kln5mET.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/Kjo4HUJ.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/JvRNIVF.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the DNS Options tab, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/k10N0tk.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/VQRkq5k.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Additional Options tab, make sure the name is what you want it to be.  Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/txeJBpw.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/fHFZOlM.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/Pa1aWQv.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Paths tab, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/GgR2Hni.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/NPiRbiB.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>It will take about 1-2 minutes for the Prerequisites Check tab to be usable (will see a blue streak going across the top of the Active Directory Domain Services Configuration Wizard box).  Click: Install – When done: Windows Server will automatically restart your computer.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/CVSJUTz.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/960UBKD.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Installation tab, you will be able to see the installation progress.  Also, you will see a blue streak going across the top of the Active Directory Domain Services Configuration Wizard box.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/8HmDrWJ.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>WINDOWS SERVER 2025 – INSTALLING ROUTING AND REMOTE ACCESS SERVICE (RRAS) FOR NAT</b></span>  
<br/><br/><br/>


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Open: Windows Server 2025.  Open: Server Manager.  Click: Add Roles and Features (middle-top, under: Configure this local server).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/z4KN4Xq.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/sYL7WdO.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/tdbUFKt.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Your first time, In: Before You Begin tab, Click & Checkmark: Skip this page by default, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/5Bnb8wN.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/I9QwWjr.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In: Installation Type tab, make sure this is Selected: Role based or feature based installation, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/vhncm2J.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/Ur4FBmr.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In: Server Selection tab, make sure this is Selected: Select a server from the server pool AND Select: Your Windows Server, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/KNHDpuM.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/YP1wclf.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In Server Roles tab, Click and Check: Remote Access, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/PZGqaeE.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/8lGZeNh.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In: Features tab, Click: Next.  In: Remote Access, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/4PDFzNb.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/0Ni1Jjw.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In: Remote Access tab, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/1RkGgCW.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/3TDehWS.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In: Role Services tab, Click the box to the left of: DirectAccess and VPN (RAS), a new box will open, Click: Add Features, now you will see a checkmark in the box of: DirectAccess and VPN (RAS).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/aNAi60Q.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/xiyCTvl.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/V4wJspP.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Click the box to the left of: Routing, you will see a checkmark in the box of: Routing.  Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/BIbyNT7.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/oSJwOMI.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In Web Server Role (NS) tab, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/tg6sHee.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/1j2fbuP.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In Role Services tab, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/8dnbzC1.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/dNBWlkl.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In Confirmation tab, Click: Install (no reboot needed).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/em1Rjkl.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/YoEBL6f.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You will see installation progress, wait OR Click: Close.  When installation is done, you will see: if you still have the installation progress box open, under the blue progress bar: Configuration required.  Installation succeeded on (computer name) (ex: WIN-4P6FFCNL4UJ), Click: Close (bottom-right) AND/OR you will see: an exclamation inside a yellow triangle by a flag in the top-right corner of Server Manager (next to: Manage).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/undefined.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/oEIhLKs.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/1CZSimF.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/e3kwgMR.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/LQmphXl.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>WINDOWS SERVER 2025 – CONFIGURE ROUTING AND REMOTE ACCESS SERVICE (RRAS) FOR NAT</b></span>  
<br/><br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In Server Manager, Click: The flag with the yellow triangle that has an exclamation inside it (very top, next to: Manage).  Click: Open the Getting Started Wizard (blue link) OR The method I will use, Click: Tools (very top, between: Manage and View).  Click: Routing and Remote Access.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/4YwQDHO.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/uQfZjdL.png" height="100%" width="100%" /></td>
  </tr>
</table>
<br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>OR</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/WOeDFOH.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/NLYw6Ng.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/XYqUUZj.png" height="50%" width="50%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/YCucPSX.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A box will pop-up called: Routing and Remote Access.  Right-Click: The server you want to configure (ex: WIN-K2BF9E7VTHV).  Click: Configure and Enable Routing and Remote Access (very top of list).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/Cgx7eej.png" height="75%" width="75%" /></td>
  </tr>
</table>
<br/>

<table>
  <tr>
    <td><img src="https://imgur.com/rCll4aZ.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/0tLzN1u.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A box will pop-up called: Routing and Remote Access Server Setup Wizard, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/jUCxrMI.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/uloDnFK.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Configuration window, Select:</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/xlW117E.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/J2aOBSQ.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/zpXG4wg.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the NAT Internet Connection window, Select: The WAN (ex: External (NAT)), Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/6b48gVW.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/ruVgXkf.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Click: Finish.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/0nKOjOS.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/LkgRrCX.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>IF YOU GET AN ERROR MESSAGE AFTER CLICKING: FINISH – CONFIGURE ROUTING AND REMOTE ACCESS SERVICE (RRAS) FOR NAT</b></span>  
<br/><br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You may get this error after clicking finish, Click: OK.  Give Windows Server about 5-10 seconds to complete the configuration, you will see small boxes pop-up called: Completing Initialization.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/CqLgEJw.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/0XF04lr.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/Swpgnyg.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You will be taken back to the box called: Routing and Remote Access when configuration is complete.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/XfJJZvE.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>To solve the error box that popped-up when you clicked finish, Open: PowerShell (Run as administrator) (right-click: Windows PowerShell: then, click: Run as administrator).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/F8fmLD1.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/vunlX1X.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/pnZhgcF.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>To stop the Routing and Remote Access service, Type and then Press: Enter:</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>net stop remoteaccess</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/DeZy9Fc.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>To make sure all RRAS (Routing and Remote Access Service) related ports are open in Windows Firewall, Type and then Press: Enter (you will not get any visible response except a new line to enter a new command):</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b># Allow RRAS core service (TCP/UDP 1701, 1723, 47, 500, 4500)</b></span>  
<br/><br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Then, Type and then Press: Enter:</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>New-NetFirewallRule -DisplayName "Allow RRAS Core Services" -Direction Inbound -Protocol TCP -LocalPort 1701,1723 -Action Allow</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/KVy1tIl.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/QP2J4qP.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Then, Type and then Press: Enter:</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>New-NetFirewallRule -DisplayName "Allow RRAS GRE" -Direction Inbound -Protocol 47 -Action Allow</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/9TGACQF.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Then, Type and then Press: Enter:</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>New-NetFirewallRule -DisplayName "Allow RRAS IPSec" -Direction Inbound -Protocol UDP -LocalPort 500,4500 -Action Allow</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/9GMyn7Z.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Then, Type and then Press: Enter (you will not get any visible response except a new line to enter a new command):</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b># Allow RRAS management console (RPC/DCOM)</b></span>  
<br/><br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Then, Type and then Press: Enter:</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>New-NetFirewallRule -DisplayName "Allow RRAS Management RPC" -Direction Inbound -Protocol TCP -LocalPort 135 -Action Allow</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/BwmY3dW.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Then, Type and then Press: Enter:</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>New-NetFirewallRule -DisplayName "Allow RRAS Management DCOM" -Direction Inbound -Protocol TCP -LocalPort 445 -Action Allow</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/DfJvM2z.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Re-enable the Routing and Remote Access Service (RRAS), Type and then Press: Enter (you will not get any visible response except a new line to enter a new command):</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Set-Service RemoteAccess -StartupType Automatic</b></span>  
<br/><br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Then, Type and then Press: Enter:</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>net start remoteaccess/b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/TlLA0o2.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>WINDOWS SERVER 2025 – INSTALLING DNS SERVER</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>On Windows Server 2025, Open: Server Manager.  Click: Add Roles and Features (middle-top, under: Configure this local server).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/GWYgBtk.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/FHmtmrJ.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In: Installation Type tab, make sure this is Selected: Role based or feature based installation, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/nPdZJWo.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/4zn5Q76.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In: Server Selection tab, make sure this is Selected: Select a server from the server pool AND Select: Your Windows Server, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/Pk6Fc8a.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/I3RjU1n.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In Server Roles tab, Click: DNS Server.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/bdNVUQg.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A box will pop-up called: Add Roles and Features Wizard.  Click: Add Features.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/h1gCSiI.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/Xl97TxV.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In Server Roles tab, The box to the left of DNS Server will now be checked.  Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/BafUqA5.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/UfUkZFF.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/BDerpBk.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In Features tab, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/E7ePeS3.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/goorgKL.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In DNS Server tab, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/3lcbFd2.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/XRL9ayI.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In Confirmation tab, Click: Install.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/6eJJVfa.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/6WxVXUl.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You will see installation progress, wait OR Click: Close.  When installation is done, you will see: if you still have the installation progress box open, under the blue progress bar: Configuration required.  Installation succeeded on (computer name) (ex: WIN-4P6FFCNL4UJ), Click: Close (bottom-right) AND/OR you will see: an exclamation inside a yellow triangle by a flag in the top-right corner of Server Manager (next to: Manage).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/MyECORa.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/NNQujjK.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/NaULURV.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You can now click: Tools (top-right corner) on Server Manager and will see: DNS.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/LMBaq2F.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/ILj3Xhz.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>WINDOWS SERVER 2025 – INSTALL A DHCP SERVER ON A DOMAIN CONTROLLER WITH RAS AND NAT</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	NOTE: This will allow Windows clients to get an IP Address that will let them browse the Internet on our Private Internal Network</b></span>  
<br/><br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Open: Windows Server 2025.  Open: Server Manager.  Click: Add Roles and Features (middle-top, under: Configure this local server).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/868PiCS.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/0dcqBCi.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/IhfUxem.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In: Installation Type tab, make sure this is Selected: Role based or feature based installation, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/E6t80gV.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/y2tZGqW.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In: Server Selection tab, make sure this is Selected: Select a server from the server pool AND Select: Your Windows Server, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/KlJWChB.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/WERtj5w.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In Server Roles tab, Click and Check: DHCP Server.  A box will pop-up called: Add Roles and Features Wizard, Click: Add Features.  You will be taken back to the: Add Roles and Features Wizard box, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/TKXhn3m.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/2InGRFF.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/7XuIroU.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/n9Pd0l1.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/gepStQ8.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/2UVJijO.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Features tab, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/SSybMiB.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/4pdq6NT.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the DHCP Server tab, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/UgqXYh1.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/o59YloC.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Confirmation tab, Click: Install.  When done, Click: Close (bottom-right) AND/OR you will see: an exclamation inside a yellow triangle by a flag in the top-right corner of Server Manager (next to: Manage).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/EtJKVWw.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src=https://imgur.com/Uzs9Hbo.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/BSJqAkb.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/UFk03wT.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/evR8K8s.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/G0RqJ0o.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>WINDOWS SERVER 2025 – CONFIGURE A DHCP SERVER ON A DOMAIN CONTROLLER WITH RAS AND NAT</b></span>  
<br/><br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In Server Manager, Click: The flag with the yellow triangle that has an exclamation inside it (very top, next to: Manage).  Click: Complete DHCP configuration (blue link) OR The method I will use, Click: Tools (very top, between: Manage and View).  Click: DHCP .</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/bgVDR0n.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/OHy1hx6.png" height="100%" width="100%" /></td>
  </tr>
</table>
<br/>

<table>
  <tr>OR</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/MWeZ2jE.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/UFzbro1.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/h0vaFqq.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A new box will pop-up called: DHCP.  Double-Click: The (windows server name).(domain name).com.  Then, Click: IPv4.  Right-Click: IPv4.  Click:  New Scope.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/Azkb0Ou.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/6q6DcsY.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/IzyZqHk.png" height="50%" width="50%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/aTZkm1R.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />



</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A new box will pop-up called: New Scope Wizard.  Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/HR9SVmy.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/tRtFM5e.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Scope Name window, Type: The name for the scope (the IP Address range: EX: 172.16.0.100-200).  Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/ubLRSzL.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/RjNFnAX.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the IP Address Range window, Type: Start & End IP address.  Type: Length: 24 (makes the Subnet Mask: 255.255.255.0).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/gtfqMPu.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/jHoObG5.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Add Exclusions and Delay window, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/wAdvqMy.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/aKGuqD9.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Lease Duration window, in the Days box, Type: 365 (so that our lap IP Addresses will not expire for one year).  Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/J82Vz5J.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/hNrj8OH.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Configure DHCP Options window, Select: Yes, I want to configure these options now.  Click; Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/aVK1Oi3.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/qwt7Srl.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Router (Default Gateway) window, Type:  The Domain Controller’s IP Address from the NAT configuration (ex: 10.0.0.1).  Click: Add.  Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/dkHJtBz.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/mZWczDc.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/MKweYtC.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/FQQl0xw.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Domain Name and DNS Servers window, Server Manager will already have the Domain Controller and its DNS info filled in.  Click: Next.</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	NOTE: When you install Active Directory on the Domain Controller, it automatically installs DNS.  Because of that, we are going to use the Domain Controller as the DNS.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/9SCkx3e.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/S6an3cw.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the WINS Server window, Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/oBhUsVB.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/g5WlhmM.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>In the Activate Scope window, Select: Yes, I want to activate this scope now.  Click: Next.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/LW8LMv4.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/4qUpH4t.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Click: Finish.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/yHMJxiD.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/EaCxeB3.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You will be taken back to the: DHCP box.  We need to get rid of the red down-arrows next to IPv4 and IPv6.</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	NOTE: A red-down arrow on IPv4 AND/OR IPv6 = it is not configured and usable.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/8UwmZRE.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/cn7Qhx6.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Right-click: The Domain Controller above IPv4 you just configured.  Click: Authorize.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/o6XdJ6k.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/aVcr2Rs.png" height="100%" width="100%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Right-click: The Domain Controller above IPv4 you just right-clicked, Click: Refresh (you will see the little circles next to IPv4 and IPv6 turn green).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/9iZZqYp.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/rG2XPXu.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/ykuZFjs.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>WINDOWS SERVER 2025 – INSTALL A ROUTER ON THE DHCP SERVER</b></span>  
<br/><br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	NOTE: DHCP Configure Options = we tell the clients which server to use for DNS and which server to use for the Default Gateway (Default Gateway = Router)</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	Use the Domain Controller’s IP Address from the NAT configuration</b></span>  
<br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	NAT = Network Address Translation = allows internal clients to connect to the Internet using one public IP address</b></span>  
<br/><br/><br/>

</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>Open: Server Manager, Click: Tools.  Click: DHCP.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/kBvGmgW.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/9LDoJgC.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/Ksc9T0E.png" height="75%" width="75%" /></td>
  </tr>
</table>


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A new window will pop-up called: DHCP.  Double-Click: The (windows server name).(domain name).com.  Double-Click: IPv4 (under the computer.domain name).  Double-Click: Server Options.  Then, Click: Action (very top, between: File and View).  Click: Configure Options.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/lOO1Hz7.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/33kMgEV.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/Kl1mgYp.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/4cJeM5B.png" height="75%" width="75%" /></td>
    <td><img src="https://imgur.com/pHEWEXG.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/CPg1bHa.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/VTnUAjI.png" height="100%" width="100%" /></td>
  </tr>
</table>


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>A new window will pop-up called: Server Options.  Click the box to the left of: 003 Router.  Type: The Domain Controller’s IP Address (ex: 10.0.0.4) so client computers connected to the domain controller can get Internet.  Click: Add.  Click: Apply.  Click: OK.</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/Ya4FWUR.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/5diVDZk.png" height="100%" width="100%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/4KvDXof.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/5XKw6Tw.png" height="100%" width="100%" /></td>
    <td><img src="https://imgur.com/gxSGmXk.png" height="100%" width="100%" /></td>
  </tr>
</table>


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>You will be taken back to the window called: DHCP.  Under: IPv4, Double-Click: Server Options.  You will now have a 003 Router (it has the IP Address that all client computers use to connect to the Internet).</b></span>  
<br/><br/>

<table>
  <tr>
    <td><img src="https://imgur.com/bAtKXZJ.png" height="75%" width="75%" /></td>
  </tr>
</table>
<br/><br/>


</div>
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>•	NOTE: AFTER ALL THIS IS SETUP: TO GET INTERNET TO WORK ON YOUR WINDOWS 11 VIRTUAL MACHINE, YOU WILL HAVE TO HAVE YOUR WINDOWS SERVER 2025 VIRTUAL MACHINE OPEN, TOO.  SINCE, THE INTERNET TO WINDOWS 11 IS COMING FROM YOUR WINDOWS SERVER 2025.</b></span>  
<br/><br/><br/>
