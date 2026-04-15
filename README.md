<h1>E-commerce Consumer Archetyping</h1>

<h2>Tools Used</h2>

- <b>Python, POWER BI :</b> Extract RDP failed logon logs from Windows Event Viewer 


<h2>Dataset and Description</h2>
<b>Source: </b>
<b>Size: </b>
<b>Description: The Powershell script in this repository is responsible for parsing out Windows Event Log information for failed RDP attacks and using a third party API to collect geographic information about the attackers location.
</b>
<br />
<br />
<b>Key Features: </b>
The script is used in this demo where I setup Azure Sentinel (SIEM) and connect it to a live virtual machine acting as a honey pot.
We will observe live attacks (RDP Brute Force) from all around the world. I will use a custom PowerShell script to
look up the attackers Geolocation information and plot it on an Azure Sentinel Map!
<br />
<br />


<h2>Data Cleaning and Pre-Processing</h2>

- <b>ipgeolocation.io:</b> IP Address to Geolocation API

<h2>Exploratory Data Analysis</h2>

<p align="center">
<img src="https://i.imgur.com/LhDCRz4.jpeg" height="85%" width="85%" alt="Image Analysis Dataflow"/>
</p>

<h2>Modelling</h2>

<h2>Results and Insights</h2>

<h2>Recommendations</h2>

<h2>Dashboard</h2>

https://github.com/user-attachments/assets/4f794dc2-9bca-415e-b4f0-d5a42256a516



<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
