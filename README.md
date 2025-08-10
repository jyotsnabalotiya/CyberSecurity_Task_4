# CyberSecurity_Task_4

## Objective
The objective of this task was to configure and test basic firewall rules to allow or block specific traffic. By performing these steps, I learned how firewall rules filter network connections and protect a system.

## Tools Used
- Operating System: Linux
- Firewall Tool:
           Linux: UFW (Uncomplicated Firewall)

## Commands/ Procedure
  ### Step 1
  ''' sudo apt install ufw '''
  This command installs the UFW (Uncomplicated Firewall) package on a Linux system. UFW is a user-friendly command-line tool for managing firewall rules, making it easier to configure          iptables without complex syntax.
  - image1.jpg
  - 
  ### Step 2
  ''' sudo ufw enable
      sudo ufw status '''
  This step activates the UFW firewall and then verifies its status.
  sudo ufw enable turns on the firewall and ensures it starts automatically at boot.
  sudo ufw status confirms whether the firewall is active and lists any existing rules. If no rules are configured yet, it will show “Status: active” with no entries.
  - image2.jpg
    
 ### Step 3
 ''' sudo ufw allow 22/tcp
     sudo ufw deny 23/tcp '''
 sudo ufw allow 22/tcp opens port 22 to allow SSH traffic, enabling secure remote connections.
 sudo ufw deny 23/tcp blocks inbound traffic on port 23, which is commonly used by the insecure Telnet protocol, enhancing system security by preventing Telnet access.    
 - image3.jpg

 ### Step 4
 ''' sudo ufw status verbose '''
 This command displays detailed information about the firewall’s current status, including all active rules with their specific ports, protocols, and whether they are allowed or denied. It    helps confirm that the rules to allow SSH (port 22) and block Telnet (port 23) are correctly applied.
 - image4.jpg

 ### Step 5
 ''' telnet localhost 23 '''
 Attempted to connect to port 23 on the local machine using Telnet to verify if the block rule is effective. Since port 23 was blocked by the firewall, the connection failed, confirming that  the firewall rule is working correctly to prevent Telnet access.
 - image5.jpg

 ### Step 6
 ''' sudo ufw delete 2 '''
 Deleted the firewall rule numbered 2, which was blocking inbound traffic on port 23 (Telnet). This step restores the firewall to its original state by removing the test rule.
 - image6.jpg
   
 ### Step 7
 ''' sudo ufw delete 3 '''
 Deleted the firewall rule numbered 3, which was allowing inbound SSH traffic on port 22. This step was performed to fully restore the firewall to its initial configuration.
 - image7.jpg
   
 ### Step 8
 ''' sudo ufw status verbose '''
 Checked the detailed firewall status again to ensure all test rules (blocking port 23 and allowing port 22) were removed and that the firewall returned to its original state.
 - image8.jpg


## Conclusion
In this task, I successfully set up and configured basic firewall rules on my Linux system using UFW. I learned how a firewall controls inbound traffic by allowing or blocking specific ports, such as permitting SSH (port 22) and blocking Telnet (port 23). Through testing, I verified that the firewall rules were applied correctly. Finally, I removed the test rules to restore the firewall to its original state. This exercise enhanced my understanding of firewall functionality and the importance of network security.

