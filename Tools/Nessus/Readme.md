## CONTRIBUTORS


                                   ****** NETWORK PENTESTING TOOL ********
                                         
                                      INTERN ID:- HPTI-SEP23-029
                                          BY ANSHU ANAND
                                      GITHUB USERNAME :- SAMAR911                
                                        TOOL NAME:- ""NESSUS""








# INTRODUCTION TO NESSUS


  
  Nessus is a vulnerability scanner that assists in finding and analysing security flaws in a computer system. It identifies and prioritises potential threats by utilising a database of known vulnerabilities and exploits.

   Security experts rely on Nessus to perform vulnerability assessments, compliance audits, and malware detection. It is capable of scanning a wide range of devices, including servers, routers, firewalls, and virtual computers.

To use Nessus, you need to first install it on your system. Once installed, you can start it by running the Nessus start executable in Kali.









## INSTALLATION


   ![1  nessus](https://github.com/gurusakharwade/HPTI-SEP-2023/assets/95374454/32c96106-7b46-4822-876d-232ef981dd3e)


Unlike many security tools, Nessus is not included with Kali Linux. However, it is quite simple to download and install. To install Nessus on your Kali, follow these steps:

  Download the Nessus package for Debian from the Nessus website https://www.tenable.com/downloads/nessus , making sure to select Linux-Debian-amd64 as the Platform.

Once the download is complete, open your Linux terminal and navigate to the directory where you saved the Nessus file.

Run the following command to install Nessus:

     dpkg -i Nessus-10.4.1-debian9_amd64.deb 

Start the Nessus service with this command:

     systemctl start nessusd
     
   ![2 nessus](https://github.com/Samar911/HPTI-SEP-2023/assets/95374454/6175616d-ce1b-43df-ad25-c7ecd860e525)

     

On your browser, go to https://kali:8834/. It would show a warning page

Click on Advanced. Then, click on Accept Risk and Continue.

Choose the Nessus Product you prefer. If you want the free version of Nessus, click on Nessus Essentials.

Enter your name and email address to receive an activation code by email. Paste the activation code into the space provided and choose a username and password.

Allow Nessus to download the necessary plugins.

   ![3  nessus downloading plugins](https://github.com/Samar911/HPTI-SEP-2023/assets/95374454/cad8e6ae-e5a4-4f9c-9ee5-57df0695a7f4)








## HOW TO USE NESSUS 


To initiate the Nessus service, run the following command in your terminal:

    systemctl start nessus

Next, enter the following URL in your browser: https://kali:8834/

To access Nessus, you need to go to https://localhost:8834/# and login using the username and password you set during installation.

   ![4  nessus login](https://github.com/Samar911/HPTI-SEP-2023/assets/95374454/759651d0-a62a-49df-82c6-9a523bafe38b)


    
After logging into Nessus, you can begin by creating a scan. In Nessus, there are other types of scans accessible, but let's start with a basic network scan. 




To create a new scan, click "New Scan" under the "Scans" tab. In the "New Scan" window, give the scan a name in the "Scan Name" area and 
provide the target domains or IP addresses in the "Targets" field. Multiple targets can be added by separating them with commas or spaces. 
We used Open Bug Bounty domains in this example.

   ![5  create a new scan](https://github.com/Samar911/HPTI-SEP-2023/assets/95374454/525e5b6e-164e-436a-9d05-d0916f249f74)

   ![6  basic network scan](https://github.com/Samar911/HPTI-SEP-2023/assets/95374454/7857b37c-c6ad-4fce-b239-a5b7dbf47b2d)


Select "All ports" from the "Port scanning" dropdown menu under the "Discovery" section. This guarantees that all ports on the target systems are examined. 

   ![7  setting target](https://github.com/Samar911/HPTI-SEP-2023/assets/95374454/6efb216c-12c8-491f-913e-ab4af2cf91e8)

 Entering ports to scan

   ![8  ports](https://github.com/Samar911/HPTI-SEP-2023/assets/95374454/ce65da4b-f18b-44db-8075-182f290469ef)


Other options include configuring the maximum number of hosts to scan concurrently, the scan policy, and the credentials to use for authenticated scans. 

When you've finished configuring all of the options, click "Save" to save the scan setup.

Finally, press the "Launch" button to begin the scan. The scan may take some time to complete depending on the number of hosts and ports being examined.
                       
   ![9  launch](https://github.com/Samar911/HPTI-SEP-2023/assets/95374454/25141107-0ddc-475c-b5a1-8a63a3f287a4)

   

The "Scans" tab allows you to track the scan's progress. When the scan is finished, click on the scan name in the "Scans" page to view the findings.  

   ![10  vuln](https://github.com/Samar911/HPTI-SEP-2023/assets/95374454/f2cbd21b-446b-45ca-8ec6-1ad5dabcfe93)
 

The results will show you all of the vulnerabilities and issues discovered during the scan, as well as their severity level and recommended repair methods.

     
After customising the scan, save it and run it like you would a standard network scan. The network vulnerability scan results will be shown in the same manner as the basic network scan results. Nessus will provide you with thorough information on any vulnerabilities discovered in the web application, as well as recommendations on how to resolve them.

   ![11  remidiation](https://github.com/Samar911/HPTI-SEP-2023/assets/95374454/e21a5c49-d1ea-4f83-9751-980cedb37d39)



Nessus have many fields to explore in network pentesting but here, i have mentioned only basic usage. 





## CONTACT 🔗 

[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/anshu-anand-64a721156/)
