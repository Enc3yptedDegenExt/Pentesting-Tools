# Contributer 
**Intern ID : HPTI-SEP23-187**

| Tool Name | Usage | Link |
| -------- | -------- | -------- |
| httpx | a fast and multi-purpose HTTP toolkit that allows running multiple probers using retriable library | [Link](https://github.com/projectdiscovery/httpx) |
# Installation Process

`httpx` requires **go1.20** to install successfully. Run the below command to get the repo:

```sh
go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest
```

# Usages

```sh
httpx -h
```

httpx is a fast and multi-purpose HTTP toolkit that allows running multiple probes using the retryablehttp library.


```console                                
Usage:
  httpx [flags]

Flags:
INPUT:
   -l, -list string      input file containing list of hosts to process
   -rr, -request string  file containing raw request
   -u, -target string[]  input target host(s) to probe

PROBES:
   -sc, -status-code     display response status-code
   -cl, -content-length  display response content-length
   -ct, -content-type    display response content-type
   -location             display response redirect location
   -favicon              display mmh3 hash for '/favicon.ico' file
   -hash string          display response body hash (supported: md5,mmh3,simhash,sha1,sha256,sha512)
   -jarm                 display jarm fingerprint hash
   -rt, -response-time   display response time
   -lc, -line-count      display response body line count
   -wc, -word-count      display response body word count
   -title                display page title
   -server, -web-server  display server name
   -td, -tech-detect     display technology in use based on wappalyzer dataset
   -method               display http request method
   -websocket            display server using websocket
   -ip                   display host ip
   -cname                display host cname
   -asn                  display host asn information
   -cdn                  display cdn in use
   -probe                display probe status

MATCHERS:
   -mc, -match-code string            match response with specified status code (-mc 200,302)
   -ml, -match-length string          match response with specified content length (-ml 100,102)
   -mlc, -match-line-count string     match response body with specified line count (-mlc 423,532)
   -mwc, -match-word-count string     match response body with specified word count (-mwc 43,55)
   -mfc, -match-favicon string[]      match response with specified favicon hash (-mfc 1494302000)
   -ms, -match-string string          match response with specified string (-ms admin)
   -mr, -match-regex string           match response with specified regex (-mr admin)
   -mcdn, -match-cdn string[]         match host with specified cdn provider (oracle, google, azure, cloudflare, cloudfront, fastly, incapsula, sucuri, leaseweb, akamai)
   -mrt, -match-response-time string  match response with specified response time in seconds (-mrt '< 1')
   -mdc, -match-condition string      match response with dsl expression condition

EXTRACTOR:
   -er, -extract-regex string[]   display response content with matched regex
   -ep, -extract-preset string[]  display response content matched by a pre-defined regex (url,ipv4,mail)

FILTERS:
   -fc, -filter-code string            filter response with specified status code (-fc 403,401)
   -fl, -filter-length string          filter response with specified content length (-fl 23,33)
   -flc, -filter-line-count string     filter response body with specified line count (-flc 423,532)
   -fwc, -filter-word-count string     filter response body with specified word count (-fwc 423,532)
   -ffc, -filter-favicon string[]      filter response with specified favicon hash (-mfc 1494302000)
   -fs, -filter-string string          filter response with specified string (-fs admin)
   -fe, -filter-regex string           filter response with specified regex (-fe admin)
   -fcdn, -filter-cdn string[]         filter host with specified cdn provider (oracle, google, azure, cloudflare, cloudfront, fastly, incapsula, sucuri, leaseweb, akamai)
   -frt, -filter-response-time string  filter response with specified response time in seconds (-frt '> 1')
   -fdc, -filter-condition string      filter response with dsl expression condition

RATE-LIMIT:
   -t, -threads int              number of threads to use (default 50)
   -rl, -rate-limit int          maximum requests to send per second (default 150)
   -rlm, -rate-limit-minute int  maximum number of requests to send per minute

MISCELLANEOUS:
   -pa, -probe-all-ips        probe all the ips associated with same host
   -p, -ports string[]        ports to probe (nmap syntax: eg http:1,2-10,11,https:80)
   -path string               path or list of paths to probe (comma-separated, file)
   -tls-probe                 send http probes on the extracted TLS domains (dns_name)
   -csp-probe                 send http probes on the extracted CSP domains
   -tls-grab                  perform TLS(SSL) data grabbing
   -pipeline                  probe and display server supporting HTTP1.1 pipeline
   -http2                     probe and display server supporting HTTP2
   -vhost                     probe and display server supporting VHOST
   -ldv, -list-dsl-variables  list json output field keys name that support dsl matcher/filter

UPDATE:
   -up, -update                 update httpx to latest version
   -duc, -disable-update-check  disable automatic httpx update check

OUTPUT:
   -o, -output string                  file to write output results
   -sr, -store-response                store http response to output directory
   -srd, -store-response-dir string    store http response to custom directory
   -csv                                store output in csv format
   -csvo, -csv-output-encoding string  define output encoding
   -json                               store output in JSONL(ines) format
   -irr, -include-response             include http request/response in JSON output (-json only)
   -irrb, -include-response-base64     include base64 encoded http request/response in JSON output (-json only)
   -include-chain                      include redirect http chain in JSON output (-json only)
   -store-chain                        include http redirect chain in responses (-sr only)

CONFIGURATIONS:
   -r, -resolvers string[]       list of custom resolver (file or comma separated)
   -allow string[]               allowed list of IP/CIDR's to process (file or comma separated)
   -deny string[]                denied list of IP/CIDR's to process (file or comma separated)
   -sni, -sni-name string        custom TLS SNI name
   -random-agent                 enable Random User-Agent to use (default true)
   -H, -header string[]          custom http headers to send with request
   -http-proxy, -proxy string    http proxy to use (eg http://127.0.0.1:8080)
   -unsafe                       send raw requests skipping golang normalization
   -resume                       resume scan using resume.cfg
   -fr, -follow-redirects        follow http redirects
   -maxr, -max-redirects int     max number of redirects to follow per host (default 10)
   -fhr, -follow-host-redirects  follow redirects on the same host
   -vhost-input                  get a list of vhosts as input
   -x string                     request methods to probe, use 'all' to probe all HTTP methods
   -body string                  post body to include in http request
   -s, -stream                   stream mode - start elaborating input targets without sorting
   -sd, -skip-dedupe             disable dedupe input items (only used with stream mode)
   -ldp, -leave-default-ports    leave default http/https ports in host header (eg. http://host:80 - https//host:443
   -ztls                         use ztls library with autofallback to standard one for tls13

DEBUG:
   -health-check, -hc        run diagnostic check up
   -debug                    display request/response content in cli
   -debug-req                display request content in cli
   -debug-resp               display response content in cli
   -version                  display httpx version
   -stats                    display scan statistic
   -profile-mem string       optional httpx memory profile dump file
   -silent                   silent mode
   -v, -verbose              verbose mode
   -si, -stats-interval int  number of seconds to wait between showing a statistics update (default: 5)
   -nc, -no-color            disable colors in cli output

OPTIMIZATIONS:
   -nf, -no-fallback                  display both probed protocol (HTTPS and HTTP)
   -nfs, -no-fallback-scheme          probe with protocol scheme specified in input 
   -maxhr, -max-host-error int        max error count per host before skipping remaining path/s (default 30)
   -ec, -exclude-cdn                  skip full port scans for CDNs (only checks for 80,443)
   -retries int                       number of retries
   -timeout int                       timeout in seconds (default 5)
   -delay duration                    duration between each http request (eg: 200ms, 1s) (default -1ns)
   -rsts, -response-size-to-save int  max response size to save in bytes (default 2147483647)
   -rstr, -response-size-to-read int  max response size to read in bytes (default 2147483647)
```

# Running httpX tool

### URL Probe

This command will run the tool for all the subdomains in `subdomains.txt` file and returns URLs running HTTP webserver. 

```console
cat subdomains.txt | httpx

    __    __  __       _  __
   / /_  / /_/ /_____ | |/ /
  / __ \/ __/ __/ __ \|   /
 / / / / /_/ /_/ /_/ /   |
/_/ /_/\__/\__/ .___/_/|_|
             /_/

                projectdiscovery.io

[INF] Current httpx version v1.2.9 (outdated)
https://aloyoga.com
https://shipping-estimates.apps.aloyoga.com
https://trk.bc.aloyoga.com
https://view.email.aloyoga.com
https://click.email.aloyoga.com
https://www.aloyoga.com

```

### File Input

This will run the tool with the `-probe` flag against all the subdomains in **subdomains.txt** and return URLs with probed status.

```console
httpx -list subdomains.txt -silent -probe
https://aloyoga.com [SUCCESS]
https://shipping-estimates.apps.aloyoga.com [SUCCESS]
https://www.aloyoga.com [SUCCESS]
https://trk.bc.aloyoga.com [SUCCESS]
https://view.email.aloyoga.com [SUCCESS]
http://self-service.id.aloyoga.com [FAILED]
http://admin.kratos.id.aloyoga.com [FAILED]
https://click.email.aloyoga.com [SUCCESS]
```


### Tool Chain


```console
subfinder -d aloyoga.com -silent | httpx -title -tech-detect -status-code

    __    __  __       _  __
   / /_  / /_/ /_____ | |/ /
  / __ \/ __/ __/ __ \|   /
 / / / / /_/ /_/ /_/ /   |
/_/ /_/\__/\__/ .___/_/|_|
             /_/

                projectdiscovery.io

https://share.aloyoga.com [302] [] [HSTS,Nginx]
https://id.dev.aloyoga.com [404] [404 Not Found] [HSTS]
https://shipping-estimates.apps.aloyoga.com [200] [Powered by CapRover] [Nginx]
https://wiz-dev.apps.aloyoga.com [200] [Powered by CapRover] [Nginx]
https://deeplink.apps.aloyoga.com [200] [] [Nginx]
https://apps.aloyoga.com [200] [Powered by CapRover] [Nginx]
https://shipping-us.apps.aloyoga.com [200] [Powered by CapRover] [Nginx]
https://geo-test.apps.aloyoga.com [200] [Powered by CapRover] [Nginx]
https://captain.apps.aloyoga.com [200] [CapRover | Server Dashboard] [Express,Nginx,Node.js]
https://swatches-backup.apps.aloyoga.com [200] [Welcome to nginx!] [Nginx]
https://wiz-empl-001.apps.aloyoga.com [200] [Powered by CapRover] [Nginx]
https://view.email.aloyoga.com [302] [Object moved] [HSTS]
https://wiz.apps.aloyoga.com [200] [] [Nginx]
https://returns.aloyoga.com [200] [Returns] [Nginx,OpenResty:1.21.4.1]
https://click.email.aloyoga.com [403] [403 - Forbidden: Access is denied.] [HSTS]
https://trk.bc.aloyoga.com [404] [404 Not Found] [Nginx]
https://image.email.aloyoga.com [403] [Access Denied]
https://dev.aloyoga.com [200] [Alo Yoga | Yoga leggings, clothes, and accessories for studio to street] [Cloudflare,Google Tag Manager,HSTS,HTTP/3,Shopify,Typekit]
https://www.aloyoga.com [200] [Alo Yoga | Yoga leggings, clothes, and accessories for studio to street] [Cloudflare,Google Tag Manager,HSTS,HTTP/3,Shopify,Typekit]
https://qa.aloyoga.com [200] [Alo Yoga | Yoga leggings, clothes, and accessories for studio to street] [Cloudflare,Google Tag Manager,HSTS,HTTP/3,Shopify,Typekit]
```



### Favicon Hash


```console
subfinder -d aloyoga.com -silent | httpx -favicon                        

    __    __  __       _  __
   / /_  / /_/ /_____ | |/ /
  / __ \/ __/ __/ __ \|   /
 / / / / /_/ /_/ /_/ /   |
/_/ /_/\__/\__/ .___/_/|_|
             /_/

                projectdiscovery.io

[INF] Current httpx version v1.2.9 (outdated)
https://returns.aloyoga.com
https://dev.aloyoga.com
https://www.aloyoga.com
https://deeplink.apps.aloyoga.com
https://apps.aloyoga.com
https://captain.apps.aloyoga.com [988422585]
https://qa.aloyoga.com
https://shipping-us.apps.aloyoga.com
https://share.aloyoga.com [-1283163711]
https://wiz-empl-001.apps.aloyoga.com
https://shipping-estimates.apps.aloyoga.com
https://swatches-backup.apps.aloyoga.com
https://geo-test.apps.aloyoga.com
https://trk.bc.aloyoga.com
https://id.dev.aloyoga.com
https://wiz.apps.aloyoga.com
https://wiz-dev.apps.aloyoga.com
https://click.email.aloyoga.com
https://view.email.aloyoga.com
https://image.email.aloyoga.com
```

### [JARM Fingerprint](https://github.com/salesforce/jarm)


```console
subfinder -d aloyoga.com -silent | httpx -jarm   

    __    __  __       _  __
   / /_  / /_/ /_____ | |/ /
  / __ \/ __/ __/ __ \|   /
 / / / / /_/ /_/ /_/ /   |
/_/ /_/\__/\__/ .___/_/|_|
             /_/

                projectdiscovery.io

[INF] Current httpx version v1.2.9 (outdated)
https://www.aloyoga.com [29d3dd00029d29d00042d43d00041d5de67cc9954cc85372523050f20b5007]
https://qa.aloyoga.com [29d3dd00029d29d00042d43d00041d5de67cc9954cc85372523050f20b5007]
https://dev.aloyoga.com [29d3dd00029d29d00042d43d00041d5de67cc9954cc85372523050f20b5007]
https://image.email.aloyoga.com [2ad2ad0002ad2ad00042d42d000000d71691dd6844b6fa08f9c5c2b4b882cc]
https://wiz-dev.apps.aloyoga.com [15d3fd16d29d29d00042d43d000000ea552d307cdd65a9a94fec1293390a04]
https://apps.aloyoga.com [15d3fd16d29d29d00042d43d000000ea552d307cdd65a9a94fec1293390a04]
https://geo-test.apps.aloyoga.com [15d3fd16d29d29d00042d43d000000ea552d307cdd65a9a94fec1293390a04]
https://shipping-estimates.apps.aloyoga.com [15d3fd16d29d29d00042d43d000000ea552d307cdd65a9a94fec1293390a04]
https://shipping-us.apps.aloyoga.com [15d3fd16d29d29d00042d43d000000ea552d307cdd65a9a94fec1293390a04]
https://id.dev.aloyoga.com [29d29d00029d29d00042d42d0000000464fb8c6842ac133bede81390a48134]
https://wiz.apps.aloyoga.com [15d3fd16d29d29d00042d43d000000ea552d307cdd65a9a94fec1293390a04]
https://share.aloyoga.com [29d29d00029d29d00029d29d29d29d00efabaa2e194cf5d86dd52d92433bab]
https://captain.apps.aloyoga.com [15d3fd16d29d29d00042d43d000000ea552d307cdd65a9a94fec1293390a04]
https://wiz-empl-001.apps.aloyoga.com [15d3fd16d29d29d00042d43d000000ea552d307cdd65a9a94fec1293390a04]
https://deeplink.apps.aloyoga.com [15d3fd16d29d29d00042d43d000000ea552d307cdd65a9a94fec1293390a04]
https://swatches-backup.apps.aloyoga.com [15d3fd16d29d29d00042d43d000000ea552d307cdd65a9a94fec1293390a04]
https://trk.bc.aloyoga.com [29d29d15d29d29d00029d29d29d29d487dfc3734968073f786f66dcf4de1b2]
https://view.email.aloyoga.com [2ad2ad0002ad2ad0002ad2ad2ad2adcb09dd549309271837f87ac5dad15fa7]
https://returns.aloyoga.com [29d29d15d29d29d00042d42d000000df133019600a83abfb096ff3e86cd79d]
https://click.email.aloyoga.com [2ad2ad0002ad2ad0002ad2ad2ad2adcb09dd549309271837f87ac5dad15fa7]
```

### ASN Fingerprint


```console
subfinder -d aloyoga.com -silent | httpx -asn 

    __    __  __       _  __
   / /_  / /_/ /_____ | |/ /
  / __ \/ __/ __/ __ \|   /
 / / / / /_/ /_/ /_/ /   |
/_/ /_/\__/\__/ .___/_/|_|
             /_/

                projectdiscovery.io

[INF] Current httpx version v1.2.9 (outdated)
https://trk.bc.aloyoga.com [AS11377, SENDGRID, US]
https://wiz-dev.apps.aloyoga.com
https://share.aloyoga.com
https://qa.aloyoga.com [AS13335, CLOUDFLARENET, US]
https://id.dev.aloyoga.com
https://returns.aloyoga.com [AS16509, AMAZON-02, US]
https://view.email.aloyoga.com
https://click.email.aloyoga.com
http://image.email.aloyoga.com
https://www.aloyoga.com [AS13335, CLOUDFLARENET, US]
https://dev.aloyoga.com [AS13335, CLOUDFLARENET, US]
https://shipping-estimates.apps.aloyoga.com
https://wiz-empl-001.apps.aloyoga.com
https://shipping-us.apps.aloyoga.com
https://captain.apps.aloyoga.com
https://apps.aloyoga.com
https://wiz.apps.aloyoga.com
https://swatches-backup.apps.aloyoga.com
https://deeplink.apps.aloyoga.com
https://geo-test.apps.aloyoga.com
```



### Screenshot

Latest addition to the project, the addition of the `-screenshot` option in httpx, a powerful new feature that allows users to take screenshots of target URLs, pages, or endpoints along with the rendered DOM. This functionality enables the **visual content discovery process**, providing a comprehensive view of the target's visual appearance.

Rendered DOM body is also included in json line output when `-screenshot` option is used with `-json` option.

#### 🚩 Usage

To use the screenshot feature, simply add the `-screenshot` flag to your httpx command:

```console
httpx -screenshot -u https://domain.com
```

🎯 Domain, Subdomain, and Path Support
The `-screenshot` option is a versatile and can be used to capture screenshots for domains, subdomains, and even specific paths when used in conjunction with the `-path` option:

```console
httpx -screenshot -u domain.com
httpx -screenshot -u https://domain.com/login
httpx -screenshot -path fuzzing_path.txt -u https://domain.com
```

httpx using with others tools:

```console
subfinder -d aloyoga.com | httpx -screenshot
```
