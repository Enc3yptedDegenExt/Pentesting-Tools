# Aircrack-ng

## Contribution

###HPTI-SEP23-071  
###HPTI-SEP23-213
###HPTI-SEP23-051

## Description

Aircrack-ng is a complete suite of tools to assess WiFi network security.

It focuses on different areas of WiFi security:
 * Monitoring: Packet capture and export of data to text files for further processing by third party tools.
 * Attacking: Replay attacks, deauthentication, fake access points and others via packet injection.
 * Testing: Checking WiFi cards and driver capabilities (capture and injection).
 * Cracking: WEP and WPA PSK (WPA 1 and 2).

All tools are command line which allows for heavy scripting. A lot of GUIs have taken advantage of this feature. It works primarily on Linux but also Windows, macOS, FreeBSD, OpenBSD, NetBSD, as well as Solaris and even eComStation 2. 

# Building

## Requirements

 * Autoconf
 * Automake
 * Libtool
 * shtool
 * OpenSSL development package or libgcrypt development package.
 * Airmon-ng (Linux) requires ethtool, usbutils, and often pciutils.
 * On Windows, cygwin has to be used and it also requires w32api package.
 * On Windows, if using clang, libiconv and libiconv-devel
 * Linux: LibNetlink 1 or 3. It can be disabled by passing --disable-libnl to configure.
 * pkg-config (pkgconf on FreeBSD, DragonFlyBSD, OpenBSD and NetBSD)
 * FreeBSD, DragonFlyBSD, OpenBSD, NetBSD, Solaris and OS X with Macports: gmake
 * Linux/Cygwin: make and Standard C++ Library development package (Debian: libstdc++-dev)

Note: Airmon-ng only requires pciutils if the system has a PCI/PCIe bus and it is populated.
      Such bus can be present even if not physically visible. For example, it is present,
      and populated on the Raspberry Pi 4, therefore pciutils is required on that device.


## Installing required and optional dependencies

Below are instructions for installing the basic requirements to build
`aircrack-ng` for a number of operating systems.

**Note**: CMocka, tcpdump, screen, HostAPd and WPA Supplicant should not be dependencies when packaging Aircrack-ng.

### Linux

#### Arch Linux

    sudo pacman -Sy base-devel libnl openssl ethtool util-linux zlib libpcap sqlite pcre2 hwloc cmocka hostapd wpa_supplicant tcpdump screen iw usbutils pciutils expect

#### Debian/Ubuntu

    sudo apt-get install build-essential autoconf automake libtool pkg-config libnl-3-dev libnl-genl-3-dev libssl-dev ethtool shtool rfkill zlib1g-dev libpcap-dev libsqlite3-dev libpcre2-dev libhwloc-dev libcmocka-dev hostapd wpasupplicant tcpdump screen iw usbutils expect

### macOS

XCode, Xcode command line tools and HomeBrew are required.

    brew install autoconf automake libtool openssl shtool pkg-config hwloc pcre2 sqlite3 libpcap cmocka


## Docker containers

We have two repositories on DockerHub:
- [aircrackng/release](https://hub.docker.com/r/aircrackng/release): Each release
- [aircrackng/git](https://hub.docker.com/r/aircrackng/git): every commit in the git repository

Base command for the `git` version:

`sudo docker run --rm -it aircrackng/git`


## Compiling

To build `aircrack-ng`, the Autotools build system is utilized. Autotools replaces
the older method of compilation.

**NOTE**: If utilizing a developer version, eg: one checked out from source control,
you will need to run a pre-`configure` script. The script to use is one of the
following: `autoreconf -i` or `env NOCONFIGURE=1 ./autogen.sh`.

First, `./configure` the project for building with the appropriate options specified
for your environment:

    ./configure <options>

**TIP**: If the above fails, please see above about developer source control versions.

Next, compile the project (respecting if `make` or `gmake` is needed):

 * Compilation:

    `make`

 * Compilation on *BSD or Solaris:

    `gmake`

Finally, the additional targets listed below may be of use in your environment:

 * Execute all unit testing:

    `make check`

 * Execute all integration testing (requires root):
 
    `make integration`

 * Installing:

    `make install`

 * Uninstall:

    `make uninstall`


#   Installing:

   ```bash
  git clone https://github.com/aircrack-ng/
  aircrack-ng
  cd aircrack-ng
  autoreconf -i
  ./configure --with-experimental
  make
  make install
  ldconfig
```

  * Installing (strip binaries):
  
    `make install-strip`

  * Installing, with external scripts:

    ```
    ./configure --with-experimental --with-ext-scripts
    make
    make install
    ```

  * Testing (with sqlite, experimental and pcre2)

    ```
    ./configure --with-experimental
    make
    make check
    ```

  * Compiling on OS X with macports (and all options):

    ```
    ./configure --with-experimental
    gmake
    ```


.

# Packaging

Automatic detection of CPU optimization is done at run time. This behavior
**is** desirable when packaging Aircrack-ng (for a Linux or other distribution.)

Also, in some cases it may be desired to provide your own flags completely and
not having the suite auto-detect a number of optimizations. To do this, add
the additional flag `--without-opt` to the `./configure` line:

`./configure --without-opt`

# Using pre-compiled binaries

## Linux/BSD

Aircrack-ng is available in most distributions repositories. However, it is not always up-to-date.

## Windows
 * Install the appropriate "monitor" driver for your card; standard drivers don't work for capturing data.
 * Aircrack-ng suite is command line tools. So, you have to open a command-line
   `Start menu -> Run... -> cmd.exe` then use them
 * Run the executables without any parameters to have help



Documentation, tutorials, ... can be found on https://aircrack-ng.org

Every tool has its own manpage. For aircrack-ng, `man aircrack-ng`
