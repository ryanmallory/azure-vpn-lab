<p align="center">
<img src="https://i.imgur.com/CSMdbQl.jpg" height="50%" width="50%"/>
</p>

<h1>Experimenting with VPNs and Azure Virtual Machine Regions</h1>
In this lab, I observe the effects of Azure virtual machine region and consumer VPN usage (Proton VPN) on IP address, location, and web browsing. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machine)
-  Remote Desktop
-  Proton VPN (Free Version)

<h2>Operating System Used </h2>

- Windows 10 Pro

<h2>High-Level Steps</h2>

- Go to www.Whatismyipaddress.com on your home computer, write down the IP address and city listed
-  Create a Windows 10 virtual machine in Azure. When selecting the region, choose a different country or geographic location
-  Connect to the virtual machine using Remote Desktop. Go to www.Whatismyipaddress.com and write down the IP address and city listed
-  Open a few popular websites, observe any differences (is the text a different language? Does the UI look different?)
-  From within the virtual machine, download the free version of Proton VPN (free user account required)
-  Open Proton VPN and connect to a server in a third geographic location (different from your home computer or VM)
-  Go to www.Whatismyipaddress.com. Write down the IP address and city, and compare these to your home computer and VM
-  Open a few popular websites and see if you notice any differences
-  Delete Resource Groups in Azure

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/JLGkWqx.jpg" height="75%" width="75%"/>
</p>
<p>
I began by opening www.whatismyipaddress.com and noting the IP address and city associated with my local machine. As you can see, the IP address is 97.113.18.186 and the city is Tukwila, WA.
</p>
<br />

<p>
<img src="https://i.imgur.com/DVwvH6e.jpg" height="75%" width="75%"/>
</p>
<p>
Next, I created a virtual machine in Azure (named "vpn-vm") and set its location to Norway East. This means that the server which hosts the virtual machine is physically located in a Microsoft datacenter in Norway. From inside the Azure portal, I copied vpn-vm's public IP address and connected to it via Remote Desktop Connection.
</p>
<br />

<p>
<img src="https://i.imgur.com/fyz3jzU.jpg" height="75%" width="75%"/>
</p>
<p>
Once I logged in to vm-vpn, I opened Microsoft Edge and once again went to www.whatismyipaddress.com. As you can see, the IP address is different than my local machine, and the location is listed as Oslo, Norway. To reiterate, this is because vpn-vm is running on physical hardware located in a Microsoft datacenter in Norway!
</p>
<br />

<p>
<img src="https://i.imgur.com/QLsH0tF.jpg" height="75%" width="75%"/>
</p>
<p>
Because the virtual machine is located in Norway, websites display Norwegian text and may have graphical/functional differences. Here's what the Norwegian version of Disney Plus looks like.
</p>
<br />

<p>
<img src="https://i.imgur.com/dz6iqLz.jpg" height="75%" width="75%"/>
</p>
<p>
From within vpn-vm, I downloaded and installed a free consumer VPN (virtual private network) client called Proton VPN. A VPN client allows you to connect to a network in a different location via a secure, encrypted tunnel. In an enterprise environment, you could use a VPN client to safely access your office's network from home or another remote location over the internet.
<br />

<p>
<img src="https://i.imgur.com/5XsEqNi.jpg" height="75%" width="75%"/>
</p>
<p>
After the installation was complete, I opened Proton VPN and connected to a VPN server in Japan. As a result, my computer will behave as if it were in that geographic location.
</p>
<br />

<p>
<img src="https://i.imgur.com/Iwi5Zdv.jpg" height="75%" width="75%"/>
</p>
<p>
Once again, I open www.whatismyipaddress.com. The location is listed as Tokyo, and the IP address has changed again.
</p>
<br />

<p>
<img src="https://i.imgur.com/VMH6WWs.jpg" height="75%" width="75%"/>
</p>
<p>
Even though vm-vpn is still running on physical hardware in Norway, the machine behaves as if it shares the same location as the VPN server (a.k.a. Tokyo). As a result, searching www.Netflix.com takes you to their Japanese site. 
</p>
<br />
