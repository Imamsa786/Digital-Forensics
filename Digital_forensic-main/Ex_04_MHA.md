# Ex.No.4 MHA (Mail Header Analyzer)
#  Aim
To trace the origin of an email and verify its authenticity by analyzing its header for signs of spoofing using a Mail Header Analyzer (MHA).
#  Description
The Mail Header Analyzer (MHA) is a forensic tool used to examine the metadata of an email by analyzing its header. Every email contains hidden technical details such as sender IP address, routing path, mail server information, and authentication records (SPF, DKIM, DMARC). By analyzing these headers, investigators can trace the true origin of an email, detect spoofing attempts, and verify its authenticity. This process is widely used in cyber forensics, phishing investigations, and email security audits.

#  Tools Required
 Computer System – to perform analysis.
 Web Browser – to access online header analyzer tools.
 Email Account – Gmail, Outlook, or any client.
 

# Procedure
## Step 1: Extract the Email Header

Copy the full, raw email header.

Gmail: Open the email → Click on the three dots (⋮) → Select Show Original.

Select all the header text and copy it.

<br> <img width="1859" height="945" alt="Screenshot 2025-09-01 212142" src="https://github.com/user-attachments/assets/75ec1850-6318-4346-8125-bcac18dddd44" /> <br>
<img width="1505" height="919" alt="Screenshot 2025-09-01 212318" src="https://github.com/user-attachments/assets/28e3b6d8-f667-444a-bb3d-c45f1911d4e5" />
## Step 2: Use a Mail Header Analyzer

Open an online tool such as MXToolbox Email Header Analyzer.

Paste the copied email header into the analysis box.

Click Analyze to generate a structured report.

<br> <img width="1919" height="901" alt="Screenshot 2025-09-01 212349" src="https://github.com/user-attachments/assets/672d3f77-1c2f-413e-964c-ea3b7ce45bb4" /> <br> <img width="1917" height="903" alt="Screenshot 2025-09-01 212430" src="https://github.com/user-attachments/assets/9c73b860-36ab-4c19-9440-4f855fc42056" />
## Step 3: Analyze the Report
Review the Delivery Summary

DMARC Compliance – The email passed DMARC checks.

SPF Status –Both SPF Authentication and Alignment passed (authorized server).

DKIM Status – Alignment passed but Authentication failed, showing an issue with the digital signature.

<br> <img width="1905" height="904" alt="Screenshot 2025-09-01 212502" src="https://github.com/user-attachments/assets/8c992527-f843-48a8-9e17-63e974b8e2d4" />
Investigate SPF Record & Delivery Path

SPF Record: v=spf1 include:mailgun.org ~all → Authorizes Mailgun servers.

Relay Information: The email was sent from m241-136.mailgun.net.

Since Mailgun servers are listed in the SPF record, the SPF check succeeded.

<br> <img width="1900" height="908" alt="Screenshot 2025-09-01 212545" src="https://github.com/user-attachments/assets/e11899c5-4b55-4487-9792-bec3be98f36c" />
Analyze the DKIM Failure

Although alignment was correct, DKIM authentication failed, indicating the message’s digital signature was either missing, invalid, or modified in transit.

<br> <img width="1872" height="555" alt="Screenshot 2025-09-01 212617" src="https://github.com/user-attachments/assets/8e78bfa0-1d0a-48b8-986f-92b42693a6ba" />

# Result
The Mail Header Analyzer successfully examined the raw email header and provided detailed insights into the message routing, authentication, and origin. The analysis showed that SPF and DMARC checks passed, confirming the sender’s server was authorized, while DKIM authentication failed, indicating a possible issue with the email’s digital signature. This demonstrates how MHA can be used in cyber forensics to verify authenticity, detect spoofing attempts, and trace the true origin of an email.
