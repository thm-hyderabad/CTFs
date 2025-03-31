# The Misleading Memo

## Category
**Forensics / Email Header Analysis**

## Description
A suspicious email was sent to the CEO of SecureCorp, claiming to contain confidential information. However, the sender's identity and intent are questionable. IT suspects foul play and intercepted the email's headers for forensic analysis.

## Challenge Overview
We are provided with a `.eml` file which consists of Fake email from user to victim.


1. **Analyze the File**:
   Open the provided `.eml` file in a text editor that can display email headers.

2. **Extract the Hidden Flag**:
   The contents of the file consist of X-Flag header with a Base64-encoded string.
   X-Flag: VEhNMTB7M300aWxfaDM0ZDNyXzRuNGx5czFzfQo=  

3. **Decode the Base64**:
   In terminal, we can use below command to decode the Base64 string or we can use any of the online base64 decoder.
   echo "VEhNMTB7M300aWxfaDM0ZDNyXzRuNGx5czFzfQo=" | base64 -d  

4. **Extract the Flag**:
   After decoding, the flag appears to be: THM10{3m4il_h34d3r_4n4lys1s}


