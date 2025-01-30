# The Lost drive of Secrets

## Category
**Digital Forensics (Disk Encryption)**

## Description
While investigating suspicious activity at a high-security cyber facility, agents recovered a misplaced thumb drive. The drive seems to contain random data, noise, and some seemingly ordinary files. However, intelligence suggests that the drive hides a critical piece of sensitive information.

## Challenge Overview
We are provided with a Encrypted volume file and also an `.img` file.

1. **Extract the Password from the Image’s EXIF Data**:
   The password to the VeraCrypt volume is hidden in the EXIF comment of the provided image file (e.g., image.jpg). Use 
   exiftool to extract it:
   
   Look for the Comment field in the output:

   Comment: THMCTF10

2. **Mount the VeraCrypt Volume**:
   
   Install VeraCrypt from VeraCrypt Official Site--> https://veracrypt.fr/en/Home.html
   
   Open VeraCrypt and click Select File.
   
   Choose the .tc file in folder (e.g., encrypted_volume.tc).
   
   Select a drive letter (e.g., Z:).
   
   Click Mount, enter the password (THMCTF10), and click OK.
   
   The mounted drive (e.g., Z:) will appear in your file explorer.

4. **Retrieve the Flag**:

   Navigate to the mounted VeraCrypt volume and open the flag.txt file
   
   You can see the flag appears to be: THM10{ENCRYPTED_VOLUME}

