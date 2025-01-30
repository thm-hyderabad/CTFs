# OSINT - 2

## Description
Where is this "508405" landing at?

## Challenge Overview
This challenge involves using **OSINT** techniques to uncover the destination of a flight. The given clue is the number `508405`, which is related to aviation tracking.

### Flag Format
The flag is in the format: THM10{loactionname}


---

## Solution

1. **Understand the Clue**:
   The number `508405` is a **Mode-S code**, a unique identifier assigned to an aircraft for transponder-based tracking. 

2. **Research Tools**:
   Mode-S codes can be searched on aviation tracking websites like [AirNav RadarBox](https://www.airnavradar.com/data/mode-s/508405)

3. **Perform the Search**:
   Use the Mode-S code `508405` on one of the platforms mentioned above. During the time of the CTF, this Mode-S code corresponded to a flight heading to **Chennai**.

4. **Construct the Flag**:
   Using the provided flag format, the flag becomes: THM10{Chennai}

![alt text](https://github.com/thm-hyderabad/CTF-s/blob/main/January%202025%20THM/OSINT-2/image.png)
