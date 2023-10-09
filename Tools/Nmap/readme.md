Intern ID : HPTI-SEP23-155

<img src="https://raw.githubusercontent.com/Naman-Devnani/HPTI-SEP-2023/main/Tools/Nmap/nmap.png">
<h1><a href="https://github.com/nmap/nmap">𝐍𝐦𝐚𝐩 (𝐍𝐞𝐭𝐰𝐨𝐫𝐤 𝐌𝐚𝐩𝐩𝐞𝐫)</a></h1>

𝐍𝐦𝐚𝐩 is a powerful and versatile network scanning and security auditing tool.
It is used to discover and map networks, identify open ports, services, and potential vulnerabilities on remote systems.
Nmap operates by sending specially crafted packets to target hosts and analyzing their responses.

Here's a more detailed explanation of how Nmap works:

𝐇𝐨𝐬𝐭 𝐃𝐢𝐬𝐜𝐨𝐯𝐞𝐫𝐲: Nmap begins by determining which hosts are active on the network. 
It does this using various techniques, including ICMP echo requests (ping), TCP and UDP probes, and ARP requests. 
This initial step helps Nmap identify the IP addresses of hosts that are online.

𝐏𝐨𝐫𝐭 𝐒𝐜𝐚𝐧𝐧𝐢𝐧𝐠: Once active hosts are identified, 
Nmap conducts port scanning to determine which ports are open and listening on these hosts. 

Nmap offers multiple 𝐬𝐜𝐚𝐧𝐧𝐢𝐧𝐠 methods, including:

  𝐓𝐂𝐏 𝐂𝐨𝐧𝐧𝐞𝐜𝐭 𝐒𝐜𝐚𝐧: Nmap attempts to establish a full TCP connection to each specified port. 
  This is the most accurate but also the most easily detectable scanning method.

  𝐒𝐘𝐍/𝐒𝐭𝐞𝐚𝐥𝐭𝐡 𝐒𝐜𝐚𝐧 (𝐓𝐂𝐏 𝐒𝐘𝐍 𝐒𝐜𝐚𝐧): Nmap sends SYN packets to the target ports and analyzes the responses. 
  It's a stealthy scan that doesn't complete the full TCP handshake, making it harder to detect.

  𝐔𝐃𝐏 𝐒𝐜𝐚𝐧: Nmap sends UDP packets to UDP ports to check for open services. 
  UDP scanning is often more time-consuming and less reliable than TCP scanning due to the connectionless nature of UDP.

  𝐂𝐨𝐦𝐩𝐫𝐞𝐡𝐞𝐧𝐬𝐢𝐯𝐞 𝐒𝐜𝐚𝐧𝐧𝐢𝐧𝐠: Nmap can combine various scanning techniques to provide a more complete picture of the network, 
  such as SYN-ACK, NULL, FIN, and XMAS scans.

𝐒𝐞𝐫𝐯𝐢𝐜𝐞 𝐚𝐧𝐝 𝐕𝐞𝐫𝐬𝐢𝐨𝐧 𝐃𝐞𝐭𝐞𝐜𝐭𝐢𝐨𝐧: Nmap identifies the services running on open ports by examining the responses from those services. 
It analyzes response banners and behavior to determine the type and version of services. 
This information is crucial for understanding the potential vulnerabilities associated with each service.

𝐎𝐒 𝐅𝐢𝐧𝐠𝐞𝐫𝐩𝐫𝐢𝐧𝐭𝐢𝐧𝐠: Nmap can attempt to guess the operating system of the target host by sending specific probes and analyzing the responses. 
OS fingerprinting helps in tailoring subsequent scans and attacks to the target's specific environment.

𝐍𝐒𝐄 (𝐍𝐦𝐚𝐩 𝐒𝐜𝐫𝐢𝐩𝐭𝐢𝐧𝐠 𝐄𝐧𝐠𝐢𝐧𝐞): Nmap includes a scripting engine that allows users to run custom scripts against target hosts. 
These scripts can perform tasks like vulnerability scanning, service enumeration, or additional information gathering. 
Users can write their own scripts or use existing ones from the NSE library.

𝐎𝐮𝐭𝐩𝐮𝐭 𝐚𝐧𝐝 𝐑𝐞𝐩𝐨𝐫𝐭𝐢𝐧𝐠: Nmap provides various output formats, including plain text, XML, and grepable formats, 
to present the scan results. These reports can be analyzed manually or processed by other tools for further analysis or automation.

<h1>Installation</h1>

<h2>Using apt (Debian/Ubuntu):</h2>

    sudo apt install nmap

<h2>Using dnf (Fedora):</h2>

    sudo dnf install nmap
  
<h2>Using yum (Older versions of Fedora and CentOS):</h2>

    sudo yum install nmap

<h2>Using pacman (Arch Linux):</h2>

    sudo pacman -S nmap

<h2>Building from Source (Generic Installation):</h2>

    ./configure
  
    make

    make install

<h1>Usage</h1>

<h2>Syntax & Example</h2>

  nmap [flag] [Target ip / domain]

    nmap -sV 127.0.0.1

<h2>Common Flags</h2>

  -𝐬𝐒 (𝐓𝐂𝐏 𝐒𝐘𝐍 𝐒𝐜𝐚𝐧):

  A stealthy scan that sends TCP SYN packets to target ports and analyzes responses.
  Commonly used for quick port scanning to identify open ports.

  -𝐬𝐔 (𝐔𝐃𝐏 𝐒𝐜𝐚𝐧):

  Scans UDP ports to find services that might not respond to TCP requests.
  Useful for discovering services like DNS, SNMP, and others running on UDP.
  
  -𝐬𝐓 (𝐓𝐂𝐏 𝐂𝐨𝐧𝐧𝐞𝐜𝐭 𝐒𝐜𝐚𝐧):

  Connects to target ports using a full TCP handshake.
  Useful when you have the necessary permissions and want to avoid stealthiness.

  -𝐬𝐕 (𝐒𝐞𝐫𝐯𝐢𝐜𝐞 𝐚𝐧𝐝 𝐕𝐞𝐫𝐬𝐢𝐨𝐧 𝐃𝐞𝐭𝐞𝐜𝐭𝐢𝐨𝐧):

  Detects and reports the versions of services running on open ports.
  Provides insights into the software and potential vulnerabilities.

  -𝐎 (𝐎𝐩𝐞𝐫𝐚𝐭𝐢𝐧𝐠 𝐒𝐲𝐬𝐭𝐞𝐦 𝐃𝐞𝐭𝐞𝐜𝐭𝐢𝐨𝐧):

  Attempts to identify the target's operating system based on network stack and responses.
  Useful for profiling target hosts.

  -𝐀 (𝐀𝐠𝐠𝐫𝐞𝐬𝐬𝐢𝐯𝐞 𝐒𝐜𝐚𝐧):

  A comprehensive scan that includes OS detection, version detection, script scanning, and traceroute.
  Useful for thorough network analysis and vulnerability assessment.

  -𝐩 (𝐏𝐨𝐫𝐭 𝐒𝐩𝐞𝐜𝐢𝐟𝐢𝐜𝐚𝐭𝐢𝐨𝐧):

  Specifies which ports to scan. You can provide a single port, a range of ports (e.g., 80-100),
  or a comma-separated list of ports (e.g., 22,80,443).

  -𝐨𝐗, -𝐨𝐍, -𝐨𝐆 (𝐎𝐮𝐭𝐩𝐮𝐭 𝐅𝐨𝐫𝐦𝐚𝐭𝐬):

  -oX saves scan results in XML format.
  -oN saves results in a normal format for human-readable output.

  -𝐯 (𝐕𝐞𝐫𝐛𝐨𝐬𝐞 𝐎𝐮𝐭𝐩𝐮𝐭):

  Increases verbosity, providing more detailed information about the scan.
  Useful for debugging and understanding the scan process.

  -𝐓 (𝐓𝐢𝐦𝐢𝐧𝐠 𝐓𝐞𝐦𝐩𝐥𝐚𝐭𝐞𝐬):

  Adjusts the scan timing and aggressiveness. Options include T0 (paranoid) to T5 (insane).
  T4 is commonly used for faster scans, balancing speed and reliability.

  -𝐬𝐜𝐫𝐢𝐩𝐭 (𝐍𝐦𝐚𝐩 𝐒𝐜𝐫𝐢𝐩𝐭𝐢𝐧𝐠 𝐄𝐧𝐠𝐢𝐧𝐞):

  Executes Nmap scripts to perform various tasks, such as vulnerability scanning, service enumeration, and more.
  Enables customization and automation of the scanning process.

  -𝐩- (𝐒𝐜𝐚𝐧 𝐀𝐥𝐥 𝟔𝟓𝟓𝟑𝟓 𝐏𝐨𝐫𝐭𝐬):

  Scans all 65,535 TCP ports on a target host. Useful for thorough port enumeration.

  
  
