<h1>Implementing DHCP</h1>

<h2>Description</h2>
Project consists of using Active Directory tools to create and maintain Group Policy across the domain. This project assumes that a Windows 7 Client has been installed and added to the domain.
<br />


<h2>Utilities Used</h2>

- <b>VirtualBox</b> 
- <b>Windows Server 2016</b>
- <b>Windows 7</b>

<h2>Environments Used </h2>

- <b>Windows Server 2016</b>

<h2>DHCP:</h2>

Select "Add Roles and Features" from the server manager and click DHCP: <br/>
<img src="https://imagizer.imageshack.com/img924/5536/ogqJu9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click Next: <br/>
<img src="https://imagizer.imageshack.com/img923/5801/lRlbmQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the SERVER1.cyber.local address and click next: <br/>
<img src="https://imagizer.imageshack.com/img922/343/COHYEm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Check the DHCP Server box and proceed: <br/>
<img src="https://imagizer.imageshack.com/img923/7039/l1ihPw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select Add Features: <br/>
<img src="https://imagizer.imageshack.com/img924/9407/x0yohh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Proceed next: <br/>
<img src="https://imagizer.imageshack.com/img924/527/6kCTHX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Proceed next: <br/>
<img src="https://imagizer.imageshack.com/img922/2263/Y88wXY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Proceed next again: <br/>
<img src="https://imagizer.imageshack.com/img923/6014/xEoUyy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Finally, start the installation: <br/>
<img src="https://imagizer.imageshack.com/img923/6785/zPQDDf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
On the next window, click "Complete DHCP Configuration": <br/>
<img src="https://imagizer.imageshack.com/img924/8310/LqqG0k.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click Next and enter the CYBER\Administrator user credentials. Select Commit.: <br/>
<img src="https://imagizer.imageshack.com/img922/3939/aFYyKx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Notice the progress as "Done". Close the window: <br/>
<img src="https://imagizer.imageshack.com/img924/2807/1hZWNz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open the DHCP intervice: <br/>
<img src="https://imagizer.imageshack.com/img923/8791/P3sG1v.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open server1.cyber.local and right click IPv4. Select New Scope: <br/>
<img src="https://imagizer.imageshack.com/img922/4964/mdXkPs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Name the scope "Cyber Scope" and click Next: <br/>
<img src="https://imagizer.imageshack.com/img924/3707/rQ4Akh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Set the IP address rnage to 10.0.0.1-10.0.0.200, with a subnet mask of 255.255.255.0. Proceed next: <br/>
<img src="https://imagizer.imageshack.com/img924/6559/ctSqxA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Exclude the range 10.0.0.1-10.0.0.10 from the DHCP allocation and click Next: <br/>
<img src="https://imagizer.imageshack.com/img924/3849/M5k4Ot.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Set the lease duration to seven days and click Next: <br/>
<img src="https://imagizer.imageshack.com/img922/3291/wpuiUV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select Yes, I want to configure these options now, and click Next: <br/>
<img src="https://imagizer.imageshack.com/img922/62/bvQKFy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Leave the Router fields blank and click Next: <br/>
<img src="https://imagizer.imageshack.com/img922/2038/DvxT4Q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In the DNS config, make sure the parent domain is cyber.local and the address is 10.0.0.1, then click Next: <br/>
<img src="https://imagizer.imageshack.com/img922/3456/xtcTU4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Skip the following configuration window and click Next: <br/>
<img src="https://imagizer.imageshack.com/img924/8897/2Ha26D.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the option to activate the scope and click Next, Finish: <br/>
<img src="https://imagizer.imageshack.com/img923/3424/80R1YA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open the DHCP management tool and verify that the scope was created and is active: <br/>
<img src="https://imagizer.imageshack.com/img924/9112/XW7Pv5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Log into the Windows 7 Client and configure it to obtain the IP address automatically (if configured otherwise): <br/>
<img src="https://imagizer.imageshack.com/img922/7819/ZeGDZX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open the command prompt and run "ipconfig /all". Notice the Primary DNS Suffix, IPv4 Addreess, and Subnet Mask. Take note of the MAC address for the next step: <br/>
<img src="https://imagizer.imageshack.com/img922/2451/iaRzDL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Go to the DHCP server and navigate to the Address Leases folder. View the client's lease settings: <br/>
<img src="https://imagizer.imageshack.com/img923/6826/EQEKdY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click your scope to expand it, and right-click Reservations to create a new reservation: <br/>
<img src="https://imagizer.imageshack.com/img923/405/J1IFk4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Configure the DHCP reservations for the client with the name for Client7, as follows: 
<br/> IP address: 10.0.0.50
<br/> MAC Address: Should be noted from the previous steps
<br/> Description: Optional
<br/> Support types: Select Both
<br/>
<img src="https://imagizer.imageshack.com/img922/9730/MAmDxF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Notice the Reservation for the Windows 7 Client: <br/>
<img src="https://imagizer.imageshack.com/img923/3633/GEuNXF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Go back to the client, open CMD and run the command "ipconfig /renew". Try "ipconfig" if you recieve an error message, as the system may have already assigned the reservation: <br/>
<img src="https://imagizer.imageshack.com/img922/5791/7SHsz4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
