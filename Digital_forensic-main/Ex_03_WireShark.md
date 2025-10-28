#   Ex.No.3   WIRESHARK
#  Aim:
To analyze and capture network traffic using the Wireshark tool in order to study communication protocols, identify network activities, and detect possible anomalies or security issues.

#  Description

Wireshark is a widely used network protocol analyzer that enables real-time capturing and detailed inspection of network traffic. It allows investigators and network administrators to monitor data packets, analyze communication protocols, troubleshoot network issues, and detect malicious activities. With support for hundreds of protocols, Wireshark provides both live capture and offline analysis, making it an essential tool in networking and cybersecurity.

#  Tools Required
 Computer or Laptop.
 Active Internet connection / Network traffic source.
 Wireshark software installed.
 Administrative privileges to capture live traffic.


## Procedure: Capturing Plaintext Passwords

### Step 1: Start Capturing Packets
- First, open Wireshark. You will see a list of all available network interfaces (e.g., "Wi-Fi," "Ethernet").


- Select the interface your computer is using to connect to the internet (in this case, Wi-Fi).

  <br>
   <br>
<img width="957" height="794" alt="Screenshot 2025-09-01 212943" src="https://github.com/user-attachments/assets/c52e693e-f4d7-4316-864c-3460e891f53d" />


  </p>
  <br>
  <br>

- Click the blue shark fin icon 🦈 in the top-left corner to start the capture. Wireshark will immediately begin capturing all traffic passing through that interface.
 <br>
   <br>
<img width="1919" height="1029" alt="Screenshot 2025-09-01 213050" src="https://github.com/user-attachments/assets/41ee67b4-8ee8-4ed2-9c3b-5d342080fbb5" />
 </p>
  <br>
  <br>

  ### Step 2: Generate Login Traffic
  - Open a web browser and navigate to http://testphp.vulnweb.com/login.php.

- Enter any dummy credentials. For this example, we'll use:

   Username: golddude

   Password: trinity07

- Click the login button. The login will fail, but the data has already been sent across the network.

 <br>
   <br>
<img width="1919" height="935" alt="Screenshot 2025-09-01 214539" src="https://github.com/user-attachments/assets/82fa19f2-fadd-4f43-9719-0f2907714236" />

 </p>
  
  
### step 3: Stop Capture and Filter Traffic

- Return to Wireshark and click the Stop button (the red square).

- In the display filter bar, you need to find the packet containing the login data. Since the form data was sent to the server, we will look for an HTTP POST request.

- Apply the following filter to find the exact packet and press Enter:

 <br>
   <br>
<img width="1919" height="1028" alt="Screenshot 2025-09-01 215119" src="https://github.com/user-attachments/assets/b6c44d65-9721-48e0-b759-a7a3373c70a3" />

 </p>
  <br>
  <br>

### step 4: Inspect the Packet to Find Credentials 

- In the filtered packet list, you should see a packet with information like "POST /userinfo.php". Select this packet.

- In the Packet Details pane below the list, expand the following sections:

Hypertext Transfer Protocol

HTML Form URL Encoded

- Inside the "HTML Form URL Encoded" section, you will see the credentials you entered in plaintext.

 <br>
   <br>
<img width="954" height="257" alt="Screenshot 2025-09-01 215157" src="https://github.com/user-attachments/assets/efeb4fbc-936e-44d5-b5e2-2451c0aaef63" />

 </p>
  <br>
  <br>

---

## Result
By using the Wireshark tool, network traffic was successfully captured and analyzed. Different protocols such as HTTP, TCP, UDP, and ICMP were observed, along with source and destination IP addresses. The packet analysis helped in understanding communication patterns and detecting unusual or suspicious activities, proving Wireshark’s effectiveness in network monitoring and forensic investigation.
