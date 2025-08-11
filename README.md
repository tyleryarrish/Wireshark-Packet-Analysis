<h1>Wireshark Packet Analysis</h1>

<h2>Description</h2>
Project demonstrates the basics of Wireshark and how to analyze protocols and PCAPs. TryHackMe was utilized for this project and I had to find answers to questions the site provided.
<br />
<h2>Takeaway</h2>
Gained hands-on experience in network traffic analysis by using Wireshark to inspect protocols and interpret PCAP files. Strengthened my ability to identify key packet details, filter network data, and apply analytical skills to answer real-world scenario questions through TryHackMe exercises.

<h2>Project Walk-Through:</h2>

<h3>Task 1: Tool Overview</h3>
<h4>Read the “capture file comments”. What is the flag?</h4>
- Open up Wireshark, go to File > Open and select the “Exercise.pcapng” to load.
<img src="https://i.imgur.com/Q4CsnUM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Open the capture file properties. Statistics > Capture File Properties:
<img src="https://i.imgur.com/6U6UFQ8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Scroll down to the comments section:
<img src="https://i.imgur.com/eQT5mrA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: TryHackMe_Wireshark_Demo

<h4>What is the total number of packets?</h4>
- It’s on the bottom right, in the status bar:
<img src="https://i.imgur.com/Mg3QbkF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: 58620

<h4>What is the SHA256 hash value of the capture file?</h4>
- Go BACK to the Capture File Properties (Statistics>Status File Properties) and it’s the third field under the file section:
<img src="https://i.imgur.com/OfpOZV9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: f446de335565fb0b0ee5e5a3266703c778b2f3dfad7efeaeccb2da5641a6d6eb

<h3>Task 2: Packet Dissection</h3>
<h4>View packet number 38. Which markup language is used under the HTTP protocol?</h4>
- Open the requested packet. You can view specific packets by clicking “Go > Go to Packet…” and then the packet input field will pop up on the right. Put in the desired packet number and the packet data will be displayed below:
<img src="https://i.imgur.com/ohZz6UM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
The answer is in near the bottom of the details pane in the bottom left:
<img src="https://i.imgur.com/vEUfn6U.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: eXtensible Markup Language

<h4>What is the arrival date of the packet? (Answer format: Month/Day/Year)</h4>
- Expand the frame details and you’ll see the arrival date and time:
<img src="https://i.imgur.com/QDkgW04.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: 05/13/2004

<h4>What is the TTL value?</h4>
- Expand the IPv4 settings and you’ll find the TTL:
<img src="https://i.imgur.com/tUc19fm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: 47

<h4>What is the TCP payload size?</h4>
- Expand the TCP details:
<img src="https://i.imgur.com/oyCfoUp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: 424

<h4>What is the e-tag value?</h4>
- Expand the HTTP settings:
<img src="https://i.imgur.com/Ak5t7rV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: 9a01a-4696–7e354b00

<h3>Task 3: Packet Navigation</h3>
<h4>Search the “r4w” string in packet details. What is the name of artist 1?</h4>
- To search by a string you can do ctrl+f which will bring up the search box, string should be selected by default, type in the string (in this case ‘r4w’) and hit enter. You’ll be taken to the html with the answer in it.
<img src="https://i.imgur.com/sOi6ItC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: r4w8173

<h4>Go to packet 12 and read the comments. What is the answer?</h4>
- Start by using Go > To Packet (or ctrl+G) to pull up packet 12, then right click and packet comment:
<img src="https://i.imgur.com/CQlB1lv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- You’ll first see the text at the top, and after begrudgingly seeing if it is an actual flag, you’ll scroll down or expand the window to find the text below it:
<img src="https://i.imgur.com/6YkwloG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Now go to packet number 39765 as instructed and export the packet bytes by right clicking on the packet:
<img src="https://i.imgur.com/6IYVFtS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Export it as instructed then grab the hash, I did so using md5sum:
<img src="https://i.imgur.com/RfhiZB6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: 911cd574a42865a956ccde2d04495ebf

<h4>There is a “.txt” file inside the capture file. Find the file and read it; what is the alien’s name?</h4>
- We’re tasked with finding out the name of an alien in a text document that’s in one of the packets in this pcap. Per the task we can export files and objects using the file menu, so do that. Click File > Export Objects > HTTP:
<img src="https://i.imgur.com/GDzqPLd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- I then sorted by filename, and the one we want is at the top:
<img src="https://i.imgur.com/doOhFKP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/9FEp4ua.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Now, open or print out the file:
<img src="https://i.imgur.com/OQoHpMm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: PACKETMASTER

<h4>Look at the expert info section. What is the number of warnings?</h4>
- Go to Analyze > Expert Information:
<img src="https://i.imgur.com/yEisUT4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Expand the window or scroll to the right to get the number:
<img src="https://i.imgur.com/uyTImi3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: 1636

<h3>Task 4: Packet Filtering</h3>
<h4>Go to packet number 4. Right-click on the “Hypertext Transfer Protocol” and apply it as a filter. Now, look at the filter pane. What is the filter query?</h4>
- Ctrl+G to Go To Packet, enter number 4, right click and click on apply as selected filter:
<img src="https://i.imgur.com/OW8Nzjx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer will be in the filter bar up top:
<img src="https://i.imgur.com/Tviw0Ff.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Answer: http

<h4>What is the number of displayed packets?</h4>
- Look to the bottom right pane:
<img src="https://i.imgur.com/2OkzUTG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: 1089

<h4>Go to packet number 33790 and follow the stream. What is the total number of artists?</h4>
- Ctrl+G to go to packet 33790, then right click the packet and hit follow stream, http:
<img src="https://i.imgur.com/IjVm3Cf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- I then searched the field for “artist” and found the number that way, there might be a more straightforward way, this is the first way that came to me however:
<img src="https://i.imgur.com/62NrnMy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: 3

<h4>What is the name of the second artist?</h4>
- This was a bit easier, since I saw how the text was formatted from the previous question. I searched for ‘artist=2’ and the answer was right there:
<img src="https://i.imgur.com/pIngrLt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
- Answer: Blad3
