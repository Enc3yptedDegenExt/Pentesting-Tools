# Contributer 
Intern ID : HPTI-SEP23-048

| Name | Usage | Link |
| -------- | -------- | -------- |
| Dirb | Used to find the directories and files fn the website. | [Link](https://www.kali.org/tools/dirb/) |


## Introduction
`dirb` is a powerful tool for discovering directories and files on a website. It's commonly used to identify hidden or sensitive information.

## Installation
To install the `dirb` use the following commands.

***Note:*** Please note that these commands are considered for systems based on Debian Linux.

```bash
sudo apt install dirb
```

## Documentation
Here is the documentation of the `dirb` which provides basic idea of how to use this tool and also provides numbers of options that we can use with the tool to make our search more reliable.

```
-----------------
DIRB v2.22    
By The Dark Raver
-----------------

dirb <url_base> [<wordlist_file(s)>] [options]

========================= NOTES =========================
 <url_base> : Base URL to scan. (Use -resume for session resuming)
 <wordlist_file(s)> : List of wordfiles. (wordfile1,wordfile2,wordfile3...)

======================== HOTKEYS ========================
 'n' -> Go to next directory.
 'q' -> Stop scan. (Saving state for resume)
 'r' -> Remaining scan stats.

======================== OPTIONS ========================
 -a <agent_string> : Specify your custom USER_AGENT.
 -b : Use path as is.
 -c <cookie_string> : Set a cookie for the HTTP request.
 -E <certificate> : path to the client certificate.
 -f : Fine tunning of NOT_FOUND (404) detection.
 -H <header_string> : Add a custom header to the HTTP request.
 -i : Use case-insensitive search.
 -l : Print "Location" header when found.
 -N <nf_code>: Ignore responses with this HTTP code.
 -o <output_file> : Save output to disk.
 -p <proxy[:port]> : Use this proxy. (Default port is 1080)
 -P <proxy_username:proxy_password> : Proxy Authentication.
 -r : Don't search recursively.
 -R : Interactive recursion. (Asks for each directory)
 -S : Silent Mode. Don't show tested words. (For dumb terminals)
 -t : Don't force an ending '/' on URLs.
 -u <username:password> : HTTP Authentication.
 -v : Show also NOT_FOUND pages.
 -w : Don't stop on WARNING messages.
 -X <extensions> / -x <exts_file> : Append each word with this extensions.
 -z <millisecs> : Add a milliseconds delay to not cause excessive Flood.

======================== EXAMPLES =======================
 dirb http://url/directory/ (Simple Test)
 dirb http://url/ -X .html (Test files with '.html' extension)
 dirb http://url/ /usr/share/dirb/wordlists/vulns/apache.txt (Test with apache.txt wordlist)
 dirb https://secure_url/ (Simple Test with SSL)

```

## Basic Usage
To start using `dirb`, follow these simple steps:

1. Open your terminal.

2. Run `dirb` with the following command:
```bash
dirb <target-URL>
```
You cam replace `<target-URL>` with the website URL you want to scan.

![Dirb Basic](Image/1_Dirb_Common.png)

## Common Options
Here are some useful options you can use with `dirb`.

### `-w`
To use a custom wordlist. But in `dirb` it is not necessary to give wordlist, bydefault it use it's own wordlist called `common.txt` wich contains common name of directories or files.
You can use below command to use you custom wordlist:
```bash
dirb <target-URL> -w /path/to/wordlist.txt
```
Also dirb provides bunch of wordlists that you can use, this wordlists are available on `/usr/share/wordlists/dirb/` folder.

#### Example:
![Wordlist](Image/2_Wordlist.png)

### `-o` 
Specify an output file to save the results. 

```bash
dirb <target-URL> -o /path/to/output.txt
```

#### Example:
![Output](Image/3_Output.png)

### `-r`
This option is used to not search recursively, meaning it will only scan the specified target directory and not explore subdirectories.

```bash
dirb <target-URL> -r
```
This can be useful when you want to limit the scope of your scan to a specific directory.

***Note:*** Please note that these commands is different from `-R`.

#### Example:
![Recursive Scan](Image/4_Recursive.png)

### `-X`
This option is used when we have to search files with specific extension. (e.g.: .html, .php)

```bash
dirb <target-URL> -X .jng,.php, .html
```
#### Example:
![Extension](Image/5_Extension.png)

### `-S`
This option used to done silent scan. This can be useful in situations where you have a large wordlist, and you want to perform a quiet, non-interactive scan without displaying each word.

```bash
dirb https://<target-URL> -S
```

#### Example:
![Silent](Image/6_Silent.png)

## Other Useful Options

### `-a`
This command used to specify a custom USER_AGENT for HTTP requests. The USER_AGENT string is a part of the HTTP header that identifies the client making the request to the web server. It helps the web server understand what type of browser or client software is accessing the website.

```bash
dirb https://<target-URL> -a "Mozilla/5.0"
```

#### Example:
![User agent](Image/7_User_Agent.png)

### `-b`
This command is used to specify that the paths being tested should be used as it is without any modifications.

```bash
dirb https://<target-URL>/myfolder -b
```

### `-c`
This option is used when the website has the token based authentication. With this option we can set custom token or session id.


```bash
dirb http://example.com -c "session_id=12345;username=admin"
```

### `-E`
This option is used to specify a client certificate when making HTTPS requests. This option is particularly useful when the target website requires client authentication using an SSL/TLS certificate.


```bash
dirb https://example.com -E client_certificate.pem
```

### `-H`
This option is used to add a custom header to the HTTP request. This can be helpful when you want to send specific headers along with your requests to the target server. Custom headers can be used for various purposes, such as specifying the User-Agent, setting authentication tokens, or any other headers required by the server.


```bash
dirb http://example.com -H "User-Agent: MyCustomUserAgent"
```
### `-i`
This option is used to perform a case-insensitive search, meaning it treats uppercase and lowercase characters in URLs as the same. This can be helpful when you're scanning a website for directories or files, as URLs are not case-sensitive by default in web servers.


```bash
dirb http://example.com -i
```

### `-l`
This option is used to print the "Location" header when found in HTTP responses. This option is useful when you want to see the URL redirections that occur during the scanning process.


```bash
dirb http://example.com -l
```

#### Example:
![Location](Image/8_Location.png)

### `-p` & `-P`
Option `-p` and `-P` options are used to specify proxy settings when conducting directory and file brute-force scans through a proxy server. These options allow dirb to route its HTTP requests through a proxy, which can be useful for various purposes, including anonymity, bypassing network restrictions, or inspecting traffic.


```bash
dirb http://example.com -p proxyserver:8080 -P proxy_user:proxy_pass
```

### `-t`
When we need to do suzz searching on the website this command used for it. `-t` used when we have to find a specific file with their extension and that file name starts with any special characters or just like that. When we use dirb by default it start using adding `/` at the end but by using this option it starts with payload it self.


```bash
dirb http://example.com /directory -t
```

#### Example:
![-t](Image/9_-t.png)
![-t-2](Image/9_2_-t.png)


Here you see directory name starts with ~(tilde) and file name starts with .(dot), so this option used in this scenario.


