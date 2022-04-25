# File Obfuscation - JPG file

**Tools**
- A Hex Editor
 - Using WinHex for the Walkthrough
 - http://www.winhex.com/winhex/

**Steps**
1. Launch WinHex (run as administrator) and open up flag.JPG
 - Confirm Edit Mode (Options > Edit Mode) is set to 'Default Edit Mode (editable)'

2. Inspect the file header hex signature and compare it to the hex signature of a conventional .jpg file
 -  https://en.wikipedia.org/wiki/List_of_file_signatures

3. Note that the hex signature is different to what is referenced on wikipedia

4. Edit the hex values to match the hex signature for a .jpg file (FF D8 FF E0 00 10 4A 46 49 46 00 01)

5. Once changed, save the file and open the file in a photo viewer, flag should present itself within the image


**Flag**
- flag{N0w_y0u_c_m3}
