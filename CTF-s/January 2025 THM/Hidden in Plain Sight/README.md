# Hidden in Plain Sight

## Category
**Cryptography**

## Description
Not everything is as it seems. Can you uncover the secret buried within the invisible?

## Challenge Overview
We are provided with a `.txt` file and a reference image (`image.jpg`). The challenge hints at something hidden in plain sight, suggesting the use of an unconventional or exotic technique for encoding the flag.

## Solution

The `.txt` file contains seemingly empty lines or invisible characters. Upon closer inspection, it becomes evident that these characters are encoded in the **Whitespace Language**.

### What is Whitespace Language?
Whitespace is a programming language that uses only invisible characters like:
- **Spaces**
- **Tabs**
- **Newlines (Line Feed)**

These characters represent instructions, making it an intriguing tool for encoding information.

### Steps to Solve:

1. **Analyze the File**:
   Open the provided `.txt` file in a text editor that can display invisible characters (e.g., VSCode, Sublime Text, or a hex editor).

2. **Identify the Encoding**:
   The contents of the file consist of spaces, tabs, and newlines. This matches the structure of the Whitespace language.

3. **Decode the Content**:
   Use a Whitespace decoder or interpreter to extract the encoded message. Tools like the following can help:
   - Online decoders (e.g., [Whitespace Interpreter](https://www.dcode.fr/whitespace-language))
   Simply copy its content into the decoder.

4. **Extract the Flag**:
   After decoding, the flag appears in the format: THM10{........}

![alt text](https://github.com/thm-hyderabad/CTF-s/blob/main/January%202025%20THM/Hidden%20in%20Plain%20Sight/image.png)
