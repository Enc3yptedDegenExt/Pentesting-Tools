# Contributors
Ayan Sharma: HPTI-SEP23-049
Smriti Kujur: HPTI-SEP23-235
Taiyab Lokhandwala: HPTI-SEP23-250

# Introduction
Wireshark, an open-source network protocol analyzer, captures and analyzes network traffic in real time. Its core purpose is to offer in-depth insights into computer network traffic flows. Being open-source, it's accessible globally, with compatibility across Windows, macOS, Linux, and UNIX-like systems, catering to a diverse user base.

# Installation and Setup of Wireshark
# Windows:
1.	Download Wireshark:
•	To get Wireshark, go to https://www.wireshark.org/download.html.
•	Choose the Windows installer that corresponds to your system architecture (32-bit or 64-bit).
•	Install the software.
2.	Install Wireshark:
•	Run the installation that you downloaded.
•	Follow the steps of the installation wizard.
•	Unless you have unique preferences, choose standard installation settings.
•	You may be prompted during installation to install WinPcap or Npcap, which are necessary for packet capture. Install at least one of these.
3.	Launch Wireshark:
•	After installation, Wireshark should be in your Start menu. Run it.

# MacOS:
1.  Install Wireshark:
•	To get Wireshark, go to https://www.wireshark.org/download.html.
•	To get the macOS version, click the "macOS" link.
2. Wireshark should be installed:
•	Open the disk image (.dmg) file that you downloaded.
•	Drag the Wireshark icon into the Applications folder.
    3. Install XQuartz (if necessary):
•	Wireshark on macOS 10.13 High Sierra and later may require XQuartz to function. Download and install XQuartz from https://www.xquartz.org/ if requested.
4.	Start Wireshark:
•	Locate Wireshark in the Applications folder.
•	Start Wireshark.
# Linux: 
1.  Install wireshark 
•	Launch a terminal.
•	Update the package list: “sudo apt update”.
•	Install Wireshark: “sudo apt install wireshark”.
•	During installation, you will be asked whether to allow non-superusers to capture packets. Choose "Yes" if required.
 
   2.  Add User to Wireshark Group (Optional):
•	To allow a non-root user to capture packets, add the user to the "wireshark" group: “sudo usermod -aG wireshark $USER”.
 
•	Log out and log back in for the changes to take effect.
   3. Launch Wireshark:
•	Open a terminal and run Wireshark with superuser privileges: “sudo wireshark”.
•	Alternatively, if you added your user to the "wireshark" group, you can run Wireshark without sudo: ‘wireshark’.

# Getting Started with Wireshark
To get started using Wireshark, you'll need to grasp how to launch it and navigate its user interface. Here's a little primer to help you get started:
Overview of the User Interface:
When you run Wireshark, you'll see a user-friendly interface designed to help you collect and analyze network data efficiently. Here's a rundown of the important points:
Menu Bar: The menu bar at the top of the Wireshark window allows you to access many tasks and options. File (for opening and saving capture files), Edit (for changing preferences), View (for customizing the display), Capture (for initiating and stopping packet capture), and other options are available.
 
# Toolbar: A toolbar with quick access buttons to frequently used functionality is located beneath the menu bar. Start and stop capture, open and save capture files, and apply display filters are all common toolbar buttons.
 
# Navigation Panels: Wireshark features several panels to help you navigate and analyze captured data:
•	Packet List Pane: This center pane provides a list of packets that have been collected. Each row represents a packet and contains important information such as time, source, destination, protocol, and length. You can pick a packet by clicking on it and viewing more details in the other panels.
•	Packet Details Pane: This pane, located beneath the packet list, reveals the detailed contents of the selected packet. It decodes and displays data from the packet's header, payload, and protocol-specific data.
•	Capture Options Pane: Before beginning a capture, you can configure several capture options in this pane. Here you can choose the capture interface, set filters, and configure the capture settings.
•	Display Filter Toolbar: A toolbar for applying display filters may be seen below the packet list window. During analysis, display filters allow you to focus on specific types of packets or traffic patterns.
•	The status bar: The status bar is located at the very bottom of the window, displays information about the capture process, the display filter status, and any notifications or messages.
# Capturing and Display Panes:
•	Typically, you begin a packet capture by selecting your network interface and defining capture options in the "Capture Options" box.
•	To begin capturing packets, click the "Start" button in the capture options box.
•	Captured packets will be displayed in real time in the "Packet List" pane.
•	Stopping the capture is as simple as selecting the "Stop" button in the capture options box.
•	Select packets in the "Packet List" pane to examine details in the "Packet Details" window.

# Analyzing Captured Data in Wireshark:
After you've captured network packets with Wireshark, you'll want to examine the data to learn more about network behavior. Here's how to go through the collected packets, inspect packet data, and use display filters to narrow down on specific traffic:
# Viewing Packet Details:
1.	Choose a Packet:
•	To choose a packet, click on it in the "Packet List" tab.
 
2.	Decoding of packets:
•	The "Packet Details" pane displays the contents of the packet in an organized way.
•	You can expand areas of the packet details to get information about various protocol layers, such as Ethernet, IP, TCP, HTTP, and so on.
•	Investigate the decoded data to learn about the packet's origin, destination, headers, and payload.
Using Display Filters to Focus on Specific Traffic:
# Wireshark includes strong display filters for narrowing down and focusing on specific packets or traffic patterns. Here's how to put them to use:
1.	Show the Filter Toolbar: 
•	The "Display Filter" toolbar is located below the packet list window. You may enter and apply display filters here.
 
2.	Basic Filtering:
•	Enter your filter expression in the show filter field and click Enter to filter packets based on specified criteria (e.g., protocol, source, destination).
•	To view only HTTP traffic, for example, type "http" in the filter field.
3.	Complex Filtering:
•	To refine your search, you can use logical operators (AND, OR, NOT) and parentheses to create complicated filters. "http and ip.src == 192.168.1.2" blocks HTTP packets having a source IP address of 192.168.1.2.
4.	Predefined Filters:
•	Wireshark's "Display Filter" drop-down menu includes predefined filters, making it simple to select typical filters for specific protocols or circumstances.

# Working with Captured Data:
After you've captured and examined network packets, you might wish to store the capture data, bookmark relevant packets for later reference, and apply Coloring rules and packet marking to improve your analysis. Here's how to do these things in Wireshark:
Saving Capture Files and Exporting Data:
1.	Capture File Save:
•	To save the full capture as a file, navigate to the "File" menu and choose "Save" or "Save As."
•	Choose a location, a file name, and a format (for example, Wireshark pcap or pcapng format).
•	To save the capture file, click the "Save" button.
2.	Packets for Export:
•	Select the packet(s) of interest in the "Packet List" pane if you wish to export specific packets or packet data.
•	Right-click and select "Export Packet Dissections" or "Export Selected Packet Bytes" to save the data from the selected packets in a variety of formats, including plain text and CSV.
# Bookmarking Interesting Packets:
1.	Make a Bookmark:
•	Select a packet in the "Packet List" tab to bookmark it for future reference.
•	Right-click the packet, then select "Apply as Filter" > "Selected."
•	This will generate a display filter that only shows the selected packet.
2.	Name the Bookmark:
•	To make it easier to find the bookmark, navigate to the "View" menu and pick "Bookmark."
•	You can give the bookmark a name and add comments to provide context.
3.	Access Bookmarked Packets:
•	To view bookmarked packets later, go to the "View" menu and choose "Bookmark."
•	Select the bookmarked packet you want to view again, and Wireshark will apply the appropriate filter to display only that packet and associated packets.

# Protocol Analysis in Wireshark:
When using Wireshark to analyze network traffic, it is critical to understand protocol analysis. Here's a quick rundown on how to examine protocols, decode common ones, and parse packet fields:
Understanding the Protocol Hierarchy:
1.	Protocol Hierarchy:
•	Wireshark organizes collected packets into a protocol hierarchy, which displays the protocol layers used in each packet.
•	The hierarchy allows you to observe how different protocols interact within a single packet and identify the important protocols at work.
 
# Interpreting Fields within Packets:
1.	Source and Destination Addresses:
•	Origin and destination IP addresses (in the IP header) and source and destination port numbers (in the transport layer header) are critical for determining network traffic origin and destination.
2.	Sequence and Acknowledgment Numbers (TCP):
•	Sequence numbers in TCP packets show the position of data inside a stream, while acknowledgment numbers acknowledge received data.
3.	Flags (TCP and other protocols):
•	Header flags indicate various control information. TCP flags such as SYN, ACK, and FIN, for example, govern connection establishment and termination.
4.	Payload Data:
•	The real content being transmitted is included in the payload data in packets. HTTP packets, for example, contain web page data; DNS packets contain queries and responses.
5.	Response Codes and Status (HTTP, DNS, etc.):
•	Pay attention to response codes (e.g., HTTP status codes, DNS response codes) when evaluating application-layer protocols such as HTTP and DNS to understand the success or failure of queries.
