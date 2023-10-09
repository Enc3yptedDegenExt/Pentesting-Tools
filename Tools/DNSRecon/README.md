Contributor
                
                Intern ID: HPTI-SEP23-229
                Name: Shreyash Rajesh Joshi
                Github_username: 1-roNy-1

DNSRecon
      DNSRecon, as it is known today, is the Python equivalent of a Ruby script originally written by Carlos Perez toward the end of 2006. In his own words, this tool largely emerged from his personal need to reflect DNS-related data collection in an intuitive manner while the Python version allowed him to practice his newly acquired skills with the programming language.

DNSRecon can perform a variety of functions ranging from security assessments to basic network troubleshooting by allowing users to:

- Check DNS server cache records for A, AAAA, and CNAME records given a list of host records in a text file
- Enumerate general DNS records for a given domain (MX, SOA, NS, A, AAAA, SPF, and TXT)
- Check all NS records for zone transfers
- Check for wildcard resolution
- Perform common SRV record enumeration and top-level domain (TLD) expansion
- Check brute force subdomain and host A and AAAA records given a domain and a wordlist
- Perform a PTR record lookup for a given IP range or CIDR
- Perform subdomain and host enumeration via Google Dorks
- Present findings in text file format for easy manipulation

    
Installation

Step 1: Install the git package if not available (e.g., sudo apt install git) and python3-pip to handle package management requirements for Python.

Step 2: Clone the source archive to your preferred location on disk:
        
        git clone https://github.com/darkoperator/dnsrecon.git

![image](https://github.com/1-roNy-1/HPTI-SEP-2023/assets/105656315/1ecfb390-abbe-4608-b044-c0297122edfe)


Step 3: Once inside the dnsrecon directory, install the library requirements like so:
        
        python3-pip install -r requirements.txt --no-warn-script-location

![image](https://github.com/1-roNy-1/HPTI-SEP-2023/assets/105656315/f962c7d8-87c9-432a-9ffc-c0876c46e3ce)




Step 4: 
      
        Run python3 dnsrecon.py -h

![image](https://github.com/1-roNy-1/HPTI-SEP-2023/assets/105656315/87cb7aab-916e-481b-b16a-8c7a5915010e)



Usages:
        
Use dnsrecon for Base domain enumeration.
                
        python3 dnsrecon.py -d <domain>

![image](https://github.com/1-roNy-1/HPTI-SEP-2023/assets/105656315/eec8bcde-3883-444c-9dea-b4de4367e0b1)


Use dnsrecon for zonewalk.

        python3 dnsrecon.py -d <domain> -t zonewalk

![image](https://github.com/1-roNy-1/HPTI-SEP-2023/assets/105656315/20ac9ac0-d384-4338-95e6-58f60d669704)




        
