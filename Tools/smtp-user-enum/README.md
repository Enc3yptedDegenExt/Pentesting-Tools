
# Contributor
Intern ID : HPTI-SEP23-0106


# smtp-user-enum
SMTP servers accept connection requests on port `25`. Once connected to this port, communication takes place by special commands that cause the SMTP server to do what user requires.

Out of all the special commands, one command is `VRFY` which is used to check if a mailbox is available for message transfer. Taking advantage of which we can enumerate possible usernmaes that exist on the machine/server.

## Usage Example

Use the VRFY method (-M VRFY) to search for the specified user (-u root) on the target server (-t 10.10.10.4):
```bash
root@kali:~# smtp-user-enum -M VRFY -u root -t 10.10.10.4
Starting smtp-user-enum v1.2 ( http://pentestmonkey.net/tools/smtp-user-enum )

 ----------------------------------------------------------
|                   Scan Information                       |
 ----------------------------------------------------------

Mode ..................... VRFY
Worker Processes ......... 5
Target count ............. 1
Username count ........... 1
Target TCP port .......... 25
Query timeout ............ 5 secs
Target domain ............

######## Scan started at Tue May 13 16:06:28 2014 #########
10.10.10.4: root exists
######## Scan completed at Tue May 13 16:06:29 2014 #########
1 results.

1 queries in 1 seconds (1.0 queries / sec)
```

Following result tells us that `root` mailbox exists on the server. This often times mean that `root` user exists on the system. Using multiple wordlists of potential usernames may give out usernames that exist on the machine/server.

## Installation

This tool comes pre-installed in Kali machines. For other systems, following command can be used to install the tool:
```
$ sudo apt install smtp-user-enum
```
You are ready to enumerate SMPT usernames!

```
root@kali:~# smtp-user-enum -h
smtp-user-enum v1.2 ( http://pentestmonkey.net/tools/smtp-user-enum )

Usage: smtp-user-enum [options] ( -u username | -U file-of-usernames ) ( -t host | -T file-of-targets )

options are:
        -m n     Maximum number of processes (default: 5)
	-M mode  Method to use for username guessing EXPN, VRFY or RCPT (default: VRFY)
	-u user  Check if user exists on remote system
	-f addr  MAIL FROM email address.  Used only in "RCPT TO" mode (default: user@example.com)
        -D dom   Domain to append to supplied user list to make email addresses (Default: none)
                 Use this option when you want to guess valid email addresses instead of just usernames
                 e.g. "-D example.com" would guess foo@example.com, bar@example.com, etc.  Instead of 
                      simply the usernames foo and bar.
	-U file  File of usernames to check via smtp service
	-t host  Server host running smtp service
	-T file  File of hostnames running the smtp service
	-p port  TCP port on which smtp service runs (default: 25)
	-d       Debugging output
	-w n     Wait a maximum of n seconds for reply (default: 5)
	-v       Verbose
	-h       This help message

Also see smtp-user-enum-user-docs.pdf from the smtp-user-enum tar ball.

Examples:

$ smtp-user-enum -M VRFY -U users.txt -t 10.0.0.1
$ smtp-user-enum -M EXPN -u admin1 -t 10.0.0.1
$ smtp-user-enum -M RCPT -U users.txt -T mail-server-ips.txt
$ smtp-user-enum -M EXPN -D example.com -U users.txt -t 10.0.0.1
```


