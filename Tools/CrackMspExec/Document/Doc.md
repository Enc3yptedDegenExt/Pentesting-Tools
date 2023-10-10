 
# CrackMapExec Installation on Unix Systems

CrackMapExec (CME) is a powerful post-exploitation framework used by penetration testers and red teamers for automating network vulnerability assessments and exploitation. You can install it on Unix systems using various methods. Below are some recommended installation options:

## Installation from Source with Poetry

1. Ensure you have the necessary dependencies installed on your system:
   ```bash
   sudo apt-get install -y libssl-dev libffi-dev python3-dev build-essential
   ```

2. Clone the CME repository:
   ```bash
   git clone https://github.com/mpgn/CrackMapExec
   ```

3. Navigate to the CME directory:
   ```bash
   cd CrackMapExec
   ```

4. Install dependencies using Poetry:
   ```bash
   poetry install
   ```

5. Run CrackMapExec:
   ```bash
   poetry run crackmapexec
   ```

## Python Package Installation (using pipx)

It's recommended to use pipx for installing CME, which simplifies Python package management:

1. Install pipx:
   ```bash
   python3 -m pip install pipx
   ```

2. Clone the CME repository:
   ```bash
   git clone https://github.com/mpgn/CrackMapExec
   ```

3. Change to the CME directory:
   ```bash
   cd CrackMapExec
   ```

4. Install CME using pipx:
   ```bash
   pipx install .
   ```

## APT Package Installation (Kali Linux)

Please note that this method may not provide the latest version of CME:

1. Install CME using APT on Kali Linux:
   ```bash
   sudo apt install crackmapexec
   ```

## Binaries

In most cases, using pre-compiled binaries is the simplest way to install CME, as it requires no additional installation steps:

1. Go to the "Actions" tab at the top of the CME repository on GitHub.

2. Click on the latest build.

3. Download the appropriate binary for your OS.

4. Binaries are available for Python 3.8, 3.9, 3.10, and 3.11.

5. Please note that you need to be logged into GitHub to download the binaries from the Actions feature.
```

You can copy and paste this Markdown code into a `.md` file for a presentable installation guide.
Certainly! Here are the installation instructions for CrackMapExec (CME) on a Windows system in a presentable Markdown format:

```markdown
# CrackMapExec Installation on Windows

CrackMapExec (CME) is a versatile post-exploitation framework used by penetration testers and red teamers. You can install it on Windows using various methods. Below are two recommended installation options:

## Using CME Binary

1. **Download the Latest Windows Binary**

   - Go to the [CME release page](https://github.com/byt3bl33d3r/CrackMapExec/releases).
   - Download the latest Windows binary.
   - Unzip the downloaded folder.

2. **Run the Binary**

   - After unzipping the folder, locate the CME binary.
   - Run the binary to start using CrackMapExec.

## From Python Standalone Version

Please note that not all functionalities have been tested with this method.

1. **Install Python3.8**

   - Download and install the standalone version of Python 3.8 for Windows from the [official Python website](https://www.python.org/downloads/release).

2. **Add Python to the PATH Environment Variable**

   - After installing Python 3.8, add the path of the folder containing the `python.exe` file to the PATH environment variable for your user account. You can do this by following these steps:
   
     - Open the Windows Start menu.
     - Search for "Environment Variables" and select "Edit the system environment variables."
     - In the System Properties window, click the "Environment Variables" button.
     - In the User Variables section, select the "Path" variable and click "Edit."
     - Click "New" and add the path to the folder containing `python.exe`, e.g., `C:\Python38`.
     - Click "OK" to save your changes.

3. **Run the CME Binary**

   - Open a Command Prompt or PowerShell window.
   - Run the CME binary using Python 3.8. For example, if the CME binary is in the current directory, you can run it as follows:

     ```bash
     python3.8.exe .\cme
     ```

## Troubleshooting

If you encounter the following error:

```
FileNotFoundError: [Errno 2] No such file or directory: 'C:\Users\Admin.shiv\cme_51b7721208fc3d0af7e301aa9a56e1da0a38e9ec5bc08bfe8cc9ba14853ac5d1.tmp\site-packages\cme\data\powersploit\CodeExecution\Invoke-ReflectivePEInjection_Resources\DemoDLL_RemoteProcess\DemoDLL_RemoteProcess\DemoDLL_RemoteProcess.vcxproj.filters
```

You can resolve it by adding the following registry key:

```bash
REG ADD "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem" /v LongPathsEnabled /t REG_DWORD /d 1 /f
```

These instructions should help you install CrackMapExec on your Windows system.

Certainly! Here's the information on selecting and using a protocol in CrackMapExec (CME) in a presentable Markdown format:

```markdown
# Selecting & Using a Protocol in CrackMapExec

CrackMapExec (CME) allows you to interact with different protocols for performing various network tasks. You can select and use a specific protocol by running the following command:

```bash
cme <protocol> <protocol options>
```

## Viewing Available Protocols

To view the available protocols and general options, you can run the following command:

```bash
cme --help
```

This command will list the available protocols under the 'protocols' section, along with other general options. You can choose the appropriate protocol and specify any additional options as needed for your specific network task.
```

You can save this Markdown text to a `.md` file for a presentable document.
Certainly! Here's the information on target formats for CrackMapExec (CME) in a presentable Markdown format:

```markdown
# CrackMapExec Target Formats

CrackMapExec (CME) supports various target formats that allow you to specify the targets for your network tasks. You can use the following target formats:

- **CIDR Notation:** Specify targets using CIDR notation. For example:
  ```bash
  crackmapexec <protocol> poudlard.wizard
  ```

- **Single IP Addresses:** You can specify single IP addresses as targets. For example:
  ```bash
  crackmapexec <protocol> 192.168.1.0 192.168.0.2
  ```

- **IP Ranges:** Specify IP ranges using the following format. For example:
  ```bash
  crackmapexec <protocol> 192.168.1.0/24
  crackmapexec <protocol> 192.168.1.0-28 10.0.0.1-67
  ```

- **Hostnames:** Use hostnames as targets. For example:
  ```bash
  crackmapexec <protocol> poudlard.wizard
  ```

- **File Containing Targets:** You can also specify targets by providing a file containing a list of targets. For example, if you have a file named `targets.txt` with a list of IP addresses or hostnames, you can use it as follows:
  ```bash
  crackmapexec <protocol> ~/targets.txt
  ```

These various target formats provide flexibility in specifying your targets when using CrackMapExec for network tasks.
```

You can save this Markdown text to a `.md` file for a presentable document.

Sure, here are the provided examples converted into Markdown format:

### Using Kerberos Authentication with CrackMapExec

CrackMapExec (CME) supports Kerberos authentication in two ways: using a password/hash or using a ticket and specifying the KRB5CCNAME environment variable. Here are examples of both methods:

#### Using Password/Hash

You can use the `-k` or `--use-kcache` option with a specified password to authenticate with Kerberos:

```bash
$ sudo cme smb zoro.gold.local -k -u bonclay -p Ocotober2022
```

#### Using Ticket and KRB5CCNAME

Alternatively, you can use the `--use-kcache` option with a specified ticket in the KRB5CCNAME environment variable:

```bash
$ export KRB5CCNAME=/home/bonclay/impacket/administrator.ccache 
$ cme smb zoro.gold.local --use-kcache
```

#### Executing Commands

You can also execute commands after authenticating with Kerberos:

```bash
$ sudo cme smb zoro.gold.local --use-kcache -x whoami
```

#### Switching Tickets

If you want to switch Kerberos tickets, set a different KRB5CCNAME and use it with CME:

```bash
$ export KRB5CCNAME=/home/bonclay/impacket/bonclay.ccache
$ sudo cme smb zoro.gold.local --use-kcache -x whoami
```

### Example with LDAP and KDC Host

You can use Kerberos authentication with LDAP and specify the KDC host using the `--kdcHost` option:

```bash
poetry run crackmapexec ldap poudlard.wizard -k --kdcHost dc01.poudlard.wizard
```

These examples demonstrate how to use Kerberos authentication with CrackMapExec for various scenarios.

Certainly, here's the information presented in Markdown format:

### Scan for Vulnerabilities and Check DC Vulnerabilities

When starting your internal penetration test, it's crucial to check for vulnerabilities, especially on the Domain Controller (DC). Here are some recommended modules you can use with CrackMapExec (CME) to perform vulnerability checks:

#### Zerologon Vulnerability Check

Zerologon is a critical vulnerability that you should check for. Use the following command with CME:

```bash
crackmapexec smb <ip> -u '' -p '' -M zerologon
```

#### PetitPotam Vulnerability Check

PetitPotam is another important vulnerability to investigate. You can check it with CME using:

```bash
crackmapexec smb <ip> -u '' -p '' -M petitpotam
```

#### noPAC Vulnerability Check

To check for the noPAC vulnerability, use the following CME command:

```bash
crackmapexec smb <ip> -u 'user' -p 'pass' -M nopac
```

These commands will help you assess the security of your internal network, identify potential vulnerabilities, and prioritize your penetration testing efforts. Remember to replace `<ip>`, `user`, and `pass` with the appropriate values for your specific environment.

Certainly, here's your information presented in Markdown format:

```markdown
# Enumerate and Map Network Hosts with CrackMapExec

If you need to discover live hosts on your network and gather information about them, you can use CrackMapExec (CME). Here's an example command to enumerate hosts on a specific IP range (192.168.1.0/24):

```bash
cme smb 192.168.1.0/24
```

Expected Results:

```markdown
- SMB         192.168.1.101    445    DC2012A          [*] Windows Server 2012 R2 Standard 9600 x64 (name:DC2012A) (domain:OCEAN) (signing:True) (SMBv1:True)
- SMB         192.168.1.102    445    DC2012B          [*] Windows Server 2012 R2 Standard 9600 x64 (name:DC2012B) (domain:EARTH) (signing:True) (SMBv1:True)
- SMB         192.168.1.110    445    DC2016A          [*] Windows Server 2016 Standard Evaluation 14393 x64 (name:DC2016A) (domain:OCEAN) (signing:True) (SMBv1:True)
- SMB         192.168.1.117    445    WIN10DESK1       [*] WIN10DESK1 x64 (name:WIN10DESK1)
```

This command will help you discover live hosts on the specified IP range and provide valuable information about their operating systems, domains, and more. Make sure to replace the IP range with the one relevant to your network.
```

Feel free to adjust the formatting as needed.
Of course, here's your command presented in a Markdown format:

```markdown
# Enumerate Active Sessions on Remote Targets with CrackMapExec (CME)

If you want to enumerate active sessions on remote targets using CrackMapExec (CME), you can use the following command:

```bash
cme smb 192.168.1.0/24 -u UserNAme -p 'PASSWORDHERE' --sessions
```

This command will scan the IP range `192.168.1.0/24` while specifying a username and password, and it will list the active sessions on the remote targets.

Make sure to replace `UserNAme` and `'PASSWORDHERE'` with the appropriate credentials for your target network.

Feel free to adjust the IP range and authentication details as needed for your specific use case.
```

You can modify the Markdown content further to match your documentation style or requirements.
Certainly, here's your command for enumerating shares and access permissions on all shares using CrackMapExec (CME) presented in Markdown format:

```markdown
# Enumerate Shares and Access Permissions with CrackMapExec (CME)

To enumerate shares and access permissions on remote targets using CrackMapExec (CME), you can use the following command:

```bash
cme smb 192.168.1.0/24 -u UserNAme -p 'PASSWORDHERE' --shares
```

This command will scan the IP range `192.168.1.0/24`, authenticate with the specified username and password, and list all the available shares on the remote targets along with their permissions.

Additionally, if you are a sponsor or have access to the following option, you can filter the results to display only readable or writable shares:

```bash
cme smb 192.168.1.0/24 -u UserNAme -p 'PASSWORDHERE' --shares --filter-shares READ WRITE
```

This feature can be particularly useful for assessing and managing share permissions during a penetration test or network assessment.

Please replace `UserNAme` and `'PASSWORDHERE'` with the appropriate credentials for your target network.

Feel free to adjust the IP range and authentication details as needed for your specific use case.
```

You can modify the Markdown content further to match your documentation style or requirements.
Certainly, here's your command for enumerating domain groups on remote targets using CrackMapExec (CME) presented in Markdown format:

```markdown
# Enumerate Domain Groups with CrackMapExec (CME)

To enumerate domain groups on remote targets using CrackMapExec (CME), you can use the following command:

```bash
cme smb 192.168.1.0/24 -u UserNAme -p 'PASSWORDHERE' --groups
```

This command will scan the IP range `192.168.1.0/24`, authenticate with the specified username and password, and list all the domain groups on the remote targets.

Make sure to replace `UserNAme` and `'PASSWORDHERE'` with the appropriate credentials for your target network.

Feel free to adjust the IP range and authentication details as needed for your specific use case.

You can modify the Markdown content further to match your documentation style or requirements.
```

This command is useful for gathering information about domain groups during network assessments or penetration tests.
# Enumerate Hosts with SMB Signing Not Required

To enumerate the network of live hosts and save a list of only the hosts that don't require SMB signing, you can use the following command:

```shell
cme smb 192.168.1.0/24 --gen-relay-list relaylistOutputFilename.txt

Certainly! Here's the information you provided in a more presentable Markdown format:

### Password Spraying with CrackMapExec (CME) for SMB

Password spraying is a technique where an attacker attempts to gain unauthorized access to a system by trying a few common usernames with multiple passwords, rather than attempting many usernames with one or a few passwords. CrackMapExec (CME) is a tool that can be used for password spraying attacks against SMB services. Below are various examples and options for using CME for password spraying:

#### Using Username/Password Lists

You can use multiple usernames or passwords by separating them with a space.

```bash
# Example: Using multiple usernames with a single password
cme smb 192.168.1.101 -u user1 user2 user3 -p Summer18

# Example: Using a single username with multiple passwords
cme smb 192.168.1.101 -u user1 -p password1 password2 password3
```

CME accepts text files of usernames and passwords, one per line. Be cautious of account lockout.

```bash
# Example: Using a file for usernames and a single password
cme smb 192.168.1.101 -u /path/to/users.txt -p Summer18

# Example: Using a single username and a file for passwords
cme smb 192.168.1.101 -u Administrator -p /path/to/passwords.txt
```

#### Continuing After Success

By default, CME will exit after a successful login is found. You can use the `--continue-on-success` flag to continue spraying even after a valid password is found. This is useful for spraying a single password against a large user list.

```bash
# Example: Continue spraying after a valid password is found
cme smb 192.168.1.101 -u /path/to/users.txt -p Summer18 --continue-on-success
```

#### Checking Login == Password Using Wordlists

You can check if the login is equal to the password using wordlists.

```bash
# Example: Check using user.txt for both usernames and passwords
cme smb 192.168.1.101 -u user.txt -p user.txt
```

#### Checking Multiple Usernames/Passwords Using Wordlists

Check multiple usernames against multiple passwords using wordlists.

```bash
# Example: Check using user.txt for usernames and password.txt for passwords
cme smb 192.168.1.101 -u user.txt -p password.txt
```

The result will display the combinations of usernames and passwords that succeed.

#### No Bruteforce with One Login Equal One Password

In some cases, you may want to check if one login is equal to one password using wordlists. The `--no-bruteforce` flag is used in such cases.

```bash
# Example: Check if one username equals one password
cme smb 192.168.1.101 -u user.txt -p password.txt --no-bruteforce --continue-on-success
```

The result will display successful combinations of usernames and passwords.

#### Caution

Be cautious when using these techniques to avoid locking accounts. Additionally, avoid specifying IP ranges or lists of IPs when using the `--no-bruteforce` option.

Remember that ethical hacking and penetration testing should only be performed on systems and networks you have explicit permission to test. Unauthorized hacking is illegal and unethical.

