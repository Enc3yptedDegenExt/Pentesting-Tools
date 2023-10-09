# RustScan – Faster Nmap Scanning with Rust

## Introduction
RustScan is the tool that assures the fastest result retrieving tool as compares to Nmap. RustScan is a tool that turns a 17 minutes Nmap scan into 19 seconds. RustScan tool is developed in the Rust language and valid on the GitHub platform. RustScan tool is an open-source and free-to-use tool. RustScan tool can scan 65k ports in almost 7-8 seconds which is much faster than other tools. RustScan tool has support to IPv6 Version IP.

## Why RustScan?

RustScan is a modern take on the port scanner. Sleek & fast. All while providing extensive extendability to you.

Not to mention RustScan uses Adaptive Learning to improve itself over time, making it the best port scanner for you.

-----------------

## Installation

### Installation of RustScan Tool on Kali Linux OS

Step 1: Download the .deb file from the below links to your Kali Linux operating system.

[Download](https://github.com/RustScan/RustScan/releases/download/2.0.1/rustscan_2.0.1_amd64.deb)

Step 2: Run the command dpkg -i on the file to install the tool.

```
sudo dpkg -i rustscan_2.0.1_amd64.deb
```
Step 3: Now use the following command to run the tool and check the help section.
```
rustscan -h
```
-----------

## Usage

### Working with RustScan Tool on Kali Linux OS

**Example 1: Host Scanning**

_we will be performing a simple port scan on the domain._

```
rustscan -a testphp.vulnweb.com
```
**Example 2: Individual Port Scanning**

_we will be performing specific single port detection rather than scanning all the ports._

```
rustscan -a testphp.vulnweb.com -p 443
```

**Example 3: Multiple selected port scanning**

_we will be performing multiple port scans or specific lists of ports rather than scanning all the ports._

```
rustscan -a testphp.vulnweb.com -p 443,80,121,65535
```
**Example 4: Ranges of ports**

_we will be performing detection of ports from the range of 1-1000 on the domain._
```
rustscan -a testphp.vulnweb.com --range 1-1000
```
