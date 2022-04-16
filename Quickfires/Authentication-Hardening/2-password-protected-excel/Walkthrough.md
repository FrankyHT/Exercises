Walkthrough

Tools
- Kali linux
- Python (built into Kali)
- office2john python script
 - https://github.com/openwall/john/blob/bleeding-jumbo/run/office2john.py

- John the Ripper (built into Kali)
 - https://www.kali.org/tools/john/



Steps
1. Open up Kali and copy/download the xlsx file to local machine
2. Open up Terminal
3. use wget to download the office2john script
 - wget https://raw.githubusercontent.com/openwall/john/bleeding-jumbo/run/office2john.py
4. Confirm rockyou.txt is present
 - Use command "locate rockyou"
 - Standard Kali instance should have rockyou wordlist in location: /usr/share/wordlists/rockyou.txt.gz
5. Unzip the rockyou.txt.gz to extract the rockyou.txt file with the command:
 - sudo gzip -d /usr/share/wordlists/rockyou.txt.gz

6. Using python, run the office2john.py script with the password protected xlsx and output a hash file, so it can be run with John the Ripper.
 - python3 office2john.py flag.xlsx > hash.txt

7. Use John, along with wordlist to crack the password hash
 - john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt

8. Upon completion, terminal output will display the cracked password. If already cracked, use the following command to show onscreen.
 - john hash.txt --show

9. With credientals received, should be able to open up the xlsx file. Flag answer located within.

Password for zip file:
- peanut

Flag:
- flag{Excel--lentWork!}
