# Directory-Traversal-Attack
This project demonstrates how a Directory Traversal attack can exploit insecure file path handling in an FTP server to gain unauthorized access to restricted files.  The objective was to simulate an attack scenario, automate it using a Bash script (`attack.sh`), and identify which files were successfully accessed through directory traversal.

Methodology
1. Setup FTP Environment  
   A mock FTP server was created with nested directories containing user files. Permissions were configured to simulate real world folder structures.  
2. Developed Attack Script (`attack.sh`)  
   The attack steps were automated using a Bash script that navigates directories, accesses files above the intended root path, and logs results.
3. Executed the Attack  
   The attack was run to identify which files could be accessed through traversal. Output logs were analyzed to confirm unauthorized access.
Key Script: `attack.sh`
The `attack.sh` file automates:  
- Starting the FTP server  
- Launching the directory traversal attack  
- Navigating directories  
- Logging accessed files  
Using a Bash script makes the process repeatable, consistent, and efficient.

Accessed Files
The attack successfully accessed the following files:
/home/tndukwe/ftp_folder/timmy/fishnames.txt
/home/tndukwe/ftp_folder/timmy/passwords.txt
/home/tndukwe/ftp_folder/timmy/reports_original.txt

Findings
- The server’s input validation was insufficient, allowing traversal sequences (`../`) to reach restricted directories.  
- Multiple sensitive files were exposed that should have been inaccessible through FTP.  
- Recommended fixes include sanitizing file paths, restricting directory permissions, and enforcing chroot jails.

Lessons Learned 
- Directory Traversal attacks exploit weak file path handling.  
- Automation with `.sh` scripts improves reproducibility in penetration testing.  
- Proper FTP configuration and input validation are critical to preventing unauthorized data exposure.

