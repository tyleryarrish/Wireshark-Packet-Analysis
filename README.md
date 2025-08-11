<h1>Wireshark Packet Analysis</h1>

<h2>Description</h2>
Project demonstrates the basics of Wireshark and how to analyze protocols and PCAPs. TryHackMe was utilized for this project and I had to find answers to questions the site provided.
<br />

<h2>Project Walk-Through:</h2>

<h3>Task 1: Tool Overview</h3>
<h4>Read the “capture file comments”. What is the flag?</h4>
- Open up Wireshark, go to File>Open and select the “Exercise.pcapng” to load.
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Open the capture file properties. Statistics > Capture File Properties:
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Scroll down to the comments section:
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: TryHackMe_Wireshark_Demo

<h4>What is the total number of packets?</h4>
- It’s on the bottom right, in the status bar:
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<h4>What is the SHA256 hash value of the capture file?</h4>
- Go BACK to the Capture File Properties (Statistics>Status File Properties) and it’s the third field under the file section:
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: f446de335565fb0b0ee5e5a3266703c778b2f3dfad7efeaeccb2da5641a6d6eb

<h3>Task 2: Packet Dissection</h3>
<h4>View packet number 38. Which markup language is used under the HTTP protocol?</h4>
- Open the requested packet. You can view specific packets by clicking “Go > Go to Packet…” and then the packet input field will pop up on the right. Put in the desired packet number and the packet data will be displayed below:
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
The answer is in near the bottom of the details pane in the bottom left:
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: eXtensible Markup Language

<h4>What is the arrival date of the packet? (Answer format: Month/Day/Year)</h4>
- Expand the frame details and you’ll see the arrival date and time:
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: 05/13/2004

<h4>What is the TTL value?</h4>
- Expand the IPv4 settings and you’ll find the TTL:
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: 47

<h4>What is the TCP payload size?</h4>
- Expand the TCP details:
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: 424

<h4>What is the e-tag value?</h4>
- Expand the HTTP settings:
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: 9a01a-4696–7e354b00

<h3>Task 3: Packet Navigation</h3>
