# Encrypted Shadows

## Category
**Steganography**

## Description
A suspicious image file was intercepted during a covert data exchange between rogue agents. Intelligence suggests it contains a secret message that could reveal critical plans. However, the file appears to be tampered with and encrypted.
## Challenge Overview
We are provided with a `.jpeg` file which contains hidden file.

### Steps to Solve:

1. **Extract the Embedded File**:
   Use steghide to retrieve the hidden text file:
   steghide extract -sf solveit.jpg


   This extracts rsa_challenge.txt containing:
   Public Key (n, e):  
   (69558317158341204148560242087927422932109152453672516532855605832683829728913, 65537)  
   Ciphertext (C): 40244798314242281124641143701203839000105866361160373606476115606546007522857  


2. **Decrypt RSA Using dcode.fr**:

   2.1. Go to the website and select "RSA Cipher".
   -->  Under "Public Key value (Integer)", paste 'n' value from rsa_challenge.txt .
   -->  Under "Public Key E", enter 65537.
   -->  Under "Value of the cipher message (Integer)", paste 'c' value from rsa_challenge.txt .

   2.2. This website will automatically factorize the 'n' value into primes which further used for decryption.

4. **Extract the Flag**:
   After decoding, the flag appears in the format: THM10{........}
