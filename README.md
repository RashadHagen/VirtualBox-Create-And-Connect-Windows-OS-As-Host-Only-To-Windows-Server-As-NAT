<h1>VirtualBox – How To Create And Connect Windows OS As Host-Only To Windows Server As NAT</h1>


<h2 style="font-family: Arial, sans-serif; font-size: 20px; font-weight: bold; margin-top: 24px; margin-bottom: 12px;">
⏹️ Description</h2>

<p style="font-family: Georgia, serif; font-size: 16px; margin-top: 12px; margin-bottom: 12px;">
This project addresses the need to create a fully functional environment that accurately simulates an enterprise Windows domain network using virtualized infrastructure. The task is to configure Windows Server 2025 and Windows 11 Pro virtual machines in VirtualBox to establish domain services, internal networking, and controlled internet access. In this project, you will configure VirtualBox host-only and NAT networking, assign static IP addressing, and establish internal and external network segmentation, then install and configure Active Directory Domain Services, DNS, DHCP, and Routing and Remote Access Services to enable domain control and NAT-based internet routing for client systems. You will complete server role installations, promote the server to a domain controller, configure DHCP scopes and routing options, and validate connectivity between Windows Server 2025 and Windows 11 Pro within the virtual domain. The completed environment provides a stable, enterprise-style domain network where Windows 11 clients authenticate to a Windows Server 2025 domain controller, resolve DNS internally, receive IP addressing via DHCP, and access the internet through NAT.
</b>



<h2 style="font-family: Arial, sans-serif; font-size: 20px; font-weight: bold; margin-top: 24px; margin-bottom: 12px;">
⏹️ Utilities Used</h2>
  
<p style="font-family: Georgia, serif; font-size: 16px; margin-top: 12px; margin-bottom: 12px;">
 
 - <b>VirtualBox</b>



<h2 style="font-family: Arial, sans-serif; font-size: 20px; font-weight: bold; margin-top: 24px; margin-bottom: 12px;"> 
⏹️ Environments Used </h2>

<p style="font-family: Georgia, serif; font-size: 16px; margin-top: 12px; margin-bottom: 12px;">
 
- <b>VirtualBox 7.0.26 & Windows Server 2025 & Windows 11 Pro & PowerShell</b>



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
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/UWcXRd2.png" height="100%" width="100%" /></td>
  </tr>

<table>
  <tr>
    <td><img src="https://imgur.com/eCT1HGi.png" height="50%" width="50%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/g5Vpgnq.png" height="100%" width="100%" /></td>
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
  <span style="font-family: Arial, sans-serif; font-size: 16px;"><b>TWO OPTIONS BELOW:</b></span>  
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
    <td><img src="https://imgur.com/gT0AutH.png" height="75%" width="75%" /></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="https://imgur.com/gT0AutH.png" height="75%" width="75%" /></td>
  </tr>
</table>

<br /><br />
