# Walkthrough - Password Protected Zip File

**Tools**
- Kali linux
- Zip2John (built into Kali)

- John the Ripper (built into Kali)
 - https://www.kali.org/tools/john/

**Steps**
1. Open up Kali
2. Copy zip file into a working folder
3. Open up Terminal
4. Confirm rockyou.txt is present
 - Use command "locate rockyou"
 - Standard Kali instance should have rockyou wordlist in location: /usr/share/wordlists/rockyou.txt.gz
5. Unzip the rockyou.txt.gz to extract the rockyou.txt file with the command:
 - sudo gzip -d /usr/share/wordlists/rockyou.txt.gz

6. Use Zip2John to extract the password hash from the zip file
 - zip2John flag.zip > hash.txt

7. Use John, along with wordlist to crack the password hash
 - john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt

8. Upon completion, terminal output will display the cracked password. If already cracked, use the following command to show onscreen.
 - john hash.txt --show

9. Now a case of unzipping the file to retrieve the contents. Using the cracked password when prompted.
- unzip flag.zip

10. Flag answer located upon opening the text file within.

**Password**
- asdfghjkl

**Flag**
- flag{NoneShallPassword}
