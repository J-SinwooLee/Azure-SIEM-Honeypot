# Microsoft Sentinel SIEM Wrold Map Project

<hr>
<h3>Overview</h3>
In this project, I'll illustrate the process of configuring Azure services and demonstrate their application in setting up a honeypot. By creating this environment, we can observe and analyze attacker activity as they attempt to access our virtual machine. At the end of the project, we will create a map using Microsft Sentinel to overview where the attackers were coming from as well as how many attacks were attempted. Additionally, we'll utilize Microsoft Sentinel to generate a map, providing insights into the origins of the attacks and the frequency of attempted breaches. This project was inspired by Josh Madakor's SIEM guide, and all credit goes to him.
<hr>

<h4>Cloud Tools and Evnironment</h3>
AZURE VM, VNET, Log Ananlytic Workspace, Microsoft Sentinel, Windonw ver: win10-22h2-pro-g2
<h4>Languauge and Unitlites</h3>
PowerShell

<h2>Project walk-through</h2>
<hr>

<h4>Step 1: How to set up Azure honeypotVM</h4>
<b2>
  
  1. Click "Virtual Machine" as the screen below
  2. If you cannot find the icon, then you can search it on the search bar
</b2>
<img src="1.png">

<b2>
On the next screen you will click "Create".
</b2>
<img src="2.png">

<b2>
Create a new resource group by clicking "Create new".

For this instance, I will create a resource group name: FirstProject.
<img src="3.png">
</b2>

<b2>
Now we are going to name our VM as HoneypotVM. Choose West US 3 for region. For the image, you will choose either Windows 10 or 11.
<img src="4.png">
</b2>

<b2>
"IMPORTANT"

Username and password will be used for RDP to remotely login in to VM. If the password is too easy then attackers can possiblly brute force themselves in. Be adivsed to create password with this in mind.
Once, everything is setup. Click "Next" and get to "Networking" tab.

<img src="5.png">

<b2>
We are going to name our virtual network as HoneypotVM-net. Then click on "Advance" next to Configure Network security group then "Create new".

<img src="6.png">

Click the trash can icone to delete the default setting

<img src="7.png">
Then click "Add an inbound rule"

<img src="8.png">
</b2>

<b2>
Change "Destination port range" to * for Any
"Action" to "Allow"
Priority: 100
We'll name this "ANY_ALLOWED_DANGER", but feel free to choose any other name you prefer.
When everything is set correctly click "Add" then "Ok".
At last click "Review + Create"

<img src="9.png">
</br2>

<h4>Step 2: How to set up Log in Azure</h4>
<br2>
Now VM is going to be created and it will take a moment.

Meanwhile we should work on creating Log.

1. Click Log Analytic Workspace
2. If you do not see the icon, you can search it on the search bar

Then click "Create"
<img src="10.png">

<br2>
Resource group is going to be the same as the VM and we are going to name this log as LAW-HoneypotVM. It will have the same region as the VM as well. Then click "Review + Create"
<img src="11.png">
</br2>

<h4>Step 3: How to set up Microsoft Defender for Cloud</h4>
<br2>
Again we can either search for the service or click on the icon.
<img src="12.png">
Then click on "Environment settings" > Subscription name > LAW-HoneypotVM
<img src="13.png">
<img src="14.png">

On Defender plans page

Foundational CSPM - ON/ Servers - ON/ SQL servers on machine - OFF then click "save"
<img src="15.png">

Then move to "Data collection" on the left side. Click "All Events" then click "save"
<img src="16.png">

<h4>Step 4: Connecting services</h4>
<br2>
Now that we've set up all the necessary services, the next step is to establish connections between them to enable communication.
</br2>

<br2>
Let's go backto Log Analaytic Workspace then click "Virtual Machine" on the list then click on the VM that you created. Then click on "Connect".
<img src="17.png">







