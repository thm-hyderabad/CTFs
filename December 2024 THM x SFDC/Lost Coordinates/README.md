## Challenge: **Lost Coordinates**  
**Category**: OSINT  

### Description  
"An image holds a hidden clue. Find the coordinates and uncover the flag!"  
"Every picture tells a story, and some stories are hidden in metadata."

### Solution  

1. **Extract Metadata**  
   Use a metadata extraction tool like `exiftool` to analyze the image:  
   ```bash
   exiftool Archives.jpeg
   ```  

   Key metadata details found:  
   - **GPS Latitude**: 17 deg 25' 26.15" N  
   - **GPS Longitude**: 78 deg 32' 10.76" E  

2. **Convert GPS Coordinates**  
   Convert the DMS format to decimal degrees (DD):  
   - Latitude: `17 + (25 / 60) + (26.15 / 3600) = 17.4239304`  
   - Longitude: `78 + (32 / 60) + (10.76 / 3600) = 78.536322`  

3. **Construct the Flag**  
   Using the format provided in the challenge:  
   **`THMxSFDC{17.42393,78.53632}`**  

### Flag  
`THMxSFDC{17.42393,78.53632}`
