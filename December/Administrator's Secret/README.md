## Challenge: **Administrator's Secret**  
**Category**: Cryptography  

### Description  
The Administrator's password hash has been dumped using the `secretsdump` tool. Your goal is to crack the hash using a wordlist to retrieve the hidden flag.

### Solution  
The key lies in the domain logon information:  
`CORP.LOCAL/Administrator:$DCC2$10240#Administrator#852ea417a9eee7f7afa0ef30610b4a7c`  

This is a DCC2 (Domain Cached Credentials v2) hash. Using `hashcat` with a provided wordlist, the following steps were performed:  

1. Save the hash to a file:  
   ```bash
   echo '$DCC2$10240#Administrator#852ea417a9eee7f7afa0ef30610b4a7c' > hash.txt
   ```

2. Crack the hash using `hashcat`:  
   ```bash
   hashcat -m 2100 -a 0 hash.txt wordlist.txt --show
   ```

3. The cracked output revealed the flag:  
   **`THMxSFDC{Th3_Fl@g_W@s_Th3_P@ssw0rd}`**  

### Flag  
`THMxSFDC{Th3_Fl@g_W@s_Th3_P@ssw0rd}`
