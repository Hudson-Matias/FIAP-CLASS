Abrindo o terminal referente ao seu sistema operacional. #hashteg
É interessante efetuar os seguintes comandos no mesmo.
```shell
sudo apt update
sudo apt upgrade
```

O comando whois procura informações sobre o domínio citado no comando.
```shell
sudo whois devsemfronteiras.tech
```

```txt
Domain Name: devsemfronteiras.tech
Registry Domain ID: D244955277-CNIC
Registrar WHOIS Server: whois.godaddy.com
Registrar URL: https://godaddy.com
Updated Date: 2026-03-18T18:40:53.583Z
Creation Date: 2021-08-05T17:50:59.000Z
Registry Expiry Date: 2026-08-05T23:59:59.000Z
Registrar: GoDaddy.com, LLC
Registrar IANA ID: 146
Registrar Abuse Contact Email: abuse@godaddy.com
Registrar Abuse Contact Phone: 
Domain Status: clientDeleteProhibited https://icann.org/epp#clientDeleteProhibited
Domain Status: clientRenewProhibited https://icann.org/epp#clientRenewProhibited
Domain Status: clientUpdateProhibited https://icann.org/epp#clientUpdateProhibited
Domain Status: clientTransferProhibited https://icann.org/epp#clientTransferProhibited
Name Server: gina.ns.cloudflare.com
Name Server: matt.ns.cloudflare.com
DNSSEC: unsigned
URL of the ICANN RDDS Inaccuracy Complaint Form: https://icann.org/wicf

>>> Last update of WHOIS database: 2026-03-21T18:48:13.342Z <<<

For more information on domain status codes, please visit https://icann.org/epp

The WHOIS information provided in this page has been redacted
in compliance with ICANN's Temporary Specification for gTLD
Registration Data.

The data in this record is provided by Tucows Registry for informational
purposes only, and it does not guarantee its accuracy. Tucows Registry is
authoritative for whois information in top-level domains it operates
under contract with the Internet Corporation for Assigned Names and
Numbers. Whois information from other top-level domains is provided by
a third-party under license to Tucows Registry.

This service is intended only for query-based access. By using this
service, you agree that you will use any data presented only for lawful
purposes and that, under no circumstances will you use (a) data
acquired for the purpose of allowing, enabling, or otherwise supporting
the transmission by e-mail, telephone, facsimile or other
communications mechanism of mass  unsolicited, commercial advertising
or solicitations to entities other than your existing  customers; or
(b) this service to enable high volume, automated, electronic processes
that send queries or data to the systems of any Registrar or any
Registry except as reasonably necessary to register domain names or
modify existing domain name registrations.

Tucows Registry reserves the right to modify these terms at any time. By
submitting this query, you agree to abide by this policy. All rights
reserved.
```

---

O comando **nslookup** é uma ferramenta comum do windows e do linux usada para buscar informações sobre registros de DNS de um determinado domínio, host ou ip.
```shell
nslookup devsemfronteiras.tech
```

```txt
Server:         192.168.1.254
Address:        192.168.1.254#53

Non-authoritative answer:
Name:   devsemfronteiras.tech
Address: 172.67.194.239
Name:   devsemfronteiras.tech
Address: 104.21.90.42
Name:   devsemfronteiras.tech
Address: 2606:4700:3034::ac43:c2ef
Name:   devsemfronteiras.tech
Address: 2606:4700:3035::6815:5a2a
```


---

O comando host é utilizado para fazer uma busca no serviço de resolução de nomes DNS.
```shell
host devsemfronteiras.tech
```

```txt
devsemfronteiras.tech has address 172.67.194.239
devsemfronteiras.tech has address 104.21.90.42
devsemfronteiras.tech has IPv6 address 2606:4700:3034::ac43:c2ef
devsemfronteiras.tech has IPv6 address 2606:4700:3035::6815:5a2a
devsemfronteiras.tech has HTTP service bindings 1 . alpn="h3,h2" ipv4hint=104.21.90.42,172.67.194.239 ech=AEX+DQBBWQAgACCqIyBV8WdV+BdK87FyldkCGGxYvAfWpveMTG7kdg5BbQAEAAEAAQASY2xvdWRmbGFyZS1lY2guY29tAAA= ipv6hint=2606:4700:3034::ac43:c2ef,2606:4700:3035::6815:5a2a
```

---

O comando traceroute faz um rastreio de pacotes que utilizam protocolos IP e ICMP.
```shell
traceroute devsemfronteiras.tech
```

```txt
traceroute to devsemfronteiras.tech (2606:4700:3034::ac43:c2ef), 30 hops max, 80 byte packets
 1  2804:d55:479b:bf00::1 (2804:d55:479b:bf00::1)  1.415 ms  1.500 ms  1.658 ms
 2  2804:d50:2:4000:: (2804:d50:2:4000::)  4.106 ms  4.179 ms  4.087 ms
 3  * * *
 4  as13335.curitiba.pr.ix.br (2001:12f8:0:4::240)  11.860 ms  12.792 ms  14.722 ms
 5  2400:cb00:718:1024::ac45:c94c (2400:cb00:718:1024::ac45:c94c)  13.674 ms  11.215 ms  11.155 ms
```

---

Whatweb -> Reconhece toda a tecnologia que está sendo utilizada naquele servidor.
Onde ele me trás http conteúdo, biblioteca, qualquer tipo de informação que está sendo utilizada naquele site.
Ele varre o site e pega tudo que é trazido para mim.
```shell
whatweb -v -a 1 devsemfronteiras.tech
```

```txt
WhatWeb report for http://devsemfronteiras.tech
Status    : 301 Moved Permanently
Title     : <None>
IP        : 172.67.194.239
Country   : RESERVED, ZZ

Summary   : HTTPServer[cloudflare], RedirectLocation[https://carreirasemfronteiras.com.br/], UncommonHeaders[report-to,nel,cf-ray]

Detected Plugins:
[ HTTPServer ]
        HTTP server header string. This plugin also attempts to 
        identify the operating system from the server header. 

        String       : cloudflare (from server string)

[ RedirectLocation ]
        HTTP Server string location. used with http-status 301 and 
        302 

        String       : https://carreirasemfronteiras.com.br/ (from location)

[ UncommonHeaders ]
        Uncommon HTTP server headers. The blacklist includes all 
        the standard headers and many non standard but common ones. 
        Interesting but fairly common headers should have their own 
        plugins, eg. x-powered-by, server and x-aspnet-version. 
        Info about headers can be found at www.http-stats.com 

        String       : report-to,nel,cf-ray (from headers)

HTTP Headers:
        HTTP/1.1 301 Moved Permanently
        Date: Sat, 21 Mar 2026 18:57:49 GMT
        Content-Length: 0
        Connection: close
        Location: https://carreirasemfronteiras.com.br/
        Report-To: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=m5%2BosKIo96PskVGWbnrwm%2FZNSZHOT8zTp7lxkSdy2A%2FWPuTh0%2FfTU00ZdsOsdkvYFshJ9%2B6nv%2FcXysxmFUMhspgnFtqUOEOq7qXHcZxgooqBB7P4Qg%3D%3D"}]}
        Nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
        Server: cloudflare
        CF-RAY: 9dff2f3dbaa8f307-CWB

WhatWeb report for https://devsemfronteiras.tech
Status    : 301 Moved Permanently
Title     : <None>
IP        : 104.21.90.42
Country   : UNITED STATES, US

Summary   : HTTPServer[cloudflare], RedirectLocation[https://carreirasemfronteiras.com.br/], UncommonHeaders[report-to,nel,cf-ray]

Detected Plugins:
[ HTTPServer ]
        HTTP server header string. This plugin also attempts to 
        identify the operating system from the server header. 

        String       : cloudflare (from server string)

[ RedirectLocation ]
        HTTP Server string location. used with http-status 301 and 
        302 

        String       : https://carreirasemfronteiras.com.br/ (from location)

[ UncommonHeaders ]
        Uncommon HTTP server headers. The blacklist includes all 
        the standard headers and many non standard but common ones. 
        Interesting but fairly common headers should have their own 
        plugins, eg. x-powered-by, server and x-aspnet-version. 
        Info about headers can be found at www.http-stats.com 

        String       : report-to,nel,cf-ray (from headers)

HTTP Headers:
        HTTP/1.1 301 Moved Permanently
        Date: Sat, 21 Mar 2026 18:57:50 GMT
        Content-Length: 0
        Connection: close
        Location: https://carreirasemfronteiras.com.br/
        Report-To: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=wwC7UZEYV260nDigpXFwY1nrrVEjMwqidGwzrGQmq7lrcB8pIU4Fu7p63qHzXBVwmszdTVyIcmPDyyzWux%2FqOWRmYHgpGlj%2F5Ax5NaQXBbFkAHLAtw%3D%3D"}]}
        Nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
        Server: cloudflare
        CF-RAY: 9dff2f410f537b0f-CWB

WhatWeb report for https://carreirasemfronteiras.com.br/
Status    : 301 Moved Permanently
Title     : <None>
IP        : 173.236.159.170
Country   : UNITED STATES, US

Summary   : HTTPServer[nginx], nginx, RedirectLocation[https://www.carreirasemfronteiras.com.br/], Strict-Transport-Security[max-age=31536000;], UncommonHeaders[x-redirect-by,x-cache-status,x-rocket-nginx-serving-static,x-content-type-options,referrer-policy,content-security-policy], X-Frame-Options[SAMEORIGIN], X-XSS-Protection[1; mode=block]

Detected Plugins:
[ HTTPServer ]
        HTTP server header string. This plugin also attempts to 
        identify the operating system from the server header. 

        String       : nginx (from server string)

[ RedirectLocation ]
        HTTP Server string location. used with http-status 301 and 
        302 

        String       : https://www.carreirasemfronteiras.com.br/ (from location)

[ Strict-Transport-Security ]
        Strict-Transport-Security is an HTTP header that restricts 
        a web browser from accessing a website without the security 
        of the HTTPS protocol. 

        String       : max-age=31536000;

[ UncommonHeaders ]
        Uncommon HTTP server headers. The blacklist includes all 
        the standard headers and many non standard but common ones. 
        Interesting but fairly common headers should have their own 
        plugins, eg. x-powered-by, server and x-aspnet-version. 
        Info about headers can be found at www.http-stats.com 

        String       : x-redirect-by,x-cache-status,x-rocket-nginx-serving-static,x-content-type-options,referrer-policy,content-security-policy (from headers)

[ X-Frame-Options ]
        This plugin retrieves the X-Frame-Options value from the 
        HTTP header. - More Info: 
        http://msdn.microsoft.com/en-us/library/cc288472%28VS.85%29.
        aspx

        String       : SAMEORIGIN

[ X-XSS-Protection ]
        This plugin retrieves the X-XSS-Protection value from the 
        HTTP header. - More Info: 
        http://msdn.microsoft.com/en-us/library/cc288472%28VS.85%29.
        aspx

        String       : 1; mode=block

[ nginx ]
        Nginx (Engine-X) is a free, open-source, high-performance 
        HTTP server and reverse proxy, as well as an IMAP/POP3 
        proxy server. 

        Website     : http://nginx.net/

HTTP Headers:
        HTTP/1.1 301 Moved Permanently
        Server: nginx
        Date: Sat, 21 Mar 2026 18:57:55 GMT
        Content-Type: text/html; charset=UTF-8
        Transfer-Encoding: chunked
        Connection: close
        Expires: Sat, 21 Mar 2026 18:57:55 GMT
        Cache-Control: max-age=0
        X-Redirect-By: WordPress
        Location: https://www.carreirasemfronteiras.com.br/
        X-Cache-Status: HIT
        X-Rocket-Nginx-Serving-Static: MISS
        Strict-Transport-Security: max-age=31536000;
        X-XSS-Protection: 1; mode=block
        X-Content-Type-Options: nosniff
        X-Frame-Options: SAMEORIGIN
        Referrer-Policy: no-referrer-when-downgrade
        Content-Security-Policy: default-src * 'unsafe-inline' 'unsafe-eval' data: blob:;

WhatWeb report for https://www.carreirasemfronteiras.com.br/
Status    : 200 OK
Title     : Podcast Carreira Sem Fronteiras – Duplicate – [#444] - Carreira Sem Fronteiras
IP        : 173.236.159.170
Country   : UNITED STATES, US

Summary   : Bootstrap[6.9.4], HTML5, HTTPServer[nginx], JQuery[3.7.1], MetaGenerator[All in One SEO (AIOSEO) 4.6.7.1,Elementor 3.23.2; features: additional_custom_breakpoints, e_lazyload; settings: css_print_method-external, google_font-enabled, font_display-auto,Powered by Slider Revolution 6.5.2 - responsive, Mobile-Friendly Slider Plugin for WordPress with comfortable drag and drop interface.,WooCommerce 10.4.4,WordPress 6.9.4], nginx, PoweredBy[Slider], Script[application/json,application/ld+json,module,speculationrules,text/javascript], Strict-Transport-Security[max-age=31536000;], UncommonHeaders[link,x-cache-status,x-rocket-nginx-serving-static,x-content-type-options,referrer-policy,content-security-policy], WordPress[6.9.4], X-Frame-Options[SAMEORIGIN], X-XSS-Protection[1; mode=block]

Detected Plugins:
[ Bootstrap ]
        Bootstrap is an open source toolkit for developing with 
        HTML, CSS, and JS. 

        Version      : 6.9.4
        Website     : https://getbootstrap.com/

[ HTML5 ]
        HTML version 5, detected by the doctype declaration 


[ HTTPServer ]
        HTTP server header string. This plugin also attempts to 
        identify the operating system from the server header. 

        String       : nginx (from server string)

[ JQuery ]
        A fast, concise, JavaScript that simplifies how to traverse 
        HTML documents, handle events, perform animations, and add 
        AJAX. 

        Version      : 3.7.1
        Website     : http://jquery.com/

[ MetaGenerator ]
        This plugin identifies meta generator tags and extracts its 
        value. 

        String       : All in One SEO (AIOSEO) 4.6.7.1,Elementor 3.23.2; features: additional_custom_breakpoints, e_lazyload; settings: css_print_method-external, google_font-enabled, font_display-auto,Powered by Slider Revolution 6.5.2 - responsive, Mobile-Friendly Slider Plugin for WordPress with comfortable drag and drop interface.,WooCommerce 10.4.4,WordPress 6.9.4                                                                                                                                                             

[ PoweredBy ]
        This plugin identifies instances of 'Powered by x' text and 
        attempts to extract the value for x. 

        String       : Slider

[ Script ]
        This plugin detects instances of script HTML elements and 
        returns the script language/type. 

        String       : application/json,application/ld+json,module,speculationrules,text/javascript

[ Strict-Transport-Security ]
        Strict-Transport-Security is an HTTP header that restricts 
        a web browser from accessing a website without the security 
        of the HTTPS protocol. 

        String       : max-age=31536000;

[ UncommonHeaders ]
        Uncommon HTTP server headers. The blacklist includes all 
        the standard headers and many non standard but common ones. 
        Interesting but fairly common headers should have their own 
        plugins, eg. x-powered-by, server and x-aspnet-version. 
        Info about headers can be found at www.http-stats.com 

        String       : link,x-cache-status,x-rocket-nginx-serving-static,x-content-type-options,referrer-policy,content-security-policy (from headers)

[ WordPress ]
        WordPress is an opensource blogging system commonly used as 
        a CMS. 

        Version      : 6.9.4
        Aggressive function available (check plugin file or details).
        Google Dorks: (1)
        Website     : http://www.wordpress.org/

[ X-Frame-Options ]
        This plugin retrieves the X-Frame-Options value from the 
        HTTP header. - More Info: 
        http://msdn.microsoft.com/en-us/library/cc288472%28VS.85%29.
        aspx

        String       : SAMEORIGIN

[ X-XSS-Protection ]
        This plugin retrieves the X-XSS-Protection value from the 
        HTTP header. - More Info: 
        http://msdn.microsoft.com/en-us/library/cc288472%28VS.85%29.
        aspx

        String       : 1; mode=block

[ nginx ]
        Nginx (Engine-X) is a free, open-source, high-performance 
        HTTP server and reverse proxy, as well as an IMAP/POP3 
        proxy server. 

        Website     : http://nginx.net/

HTTP Headers:
        HTTP/1.1 200 OK
        Server: nginx
        Date: Sat, 21 Mar 2026 18:58:00 GMT
        Content-Type: text/html; charset=UTF-8
        Transfer-Encoding: chunked
        Connection: close
        Vary: Accept-Encoding
        Link: <https://www.carreirasemfronteiras.com.br/wp-json/>; rel="https://api.w.org/"
        Link: <https://www.carreirasemfronteiras.com.br/wp-json/wp/v2/pages/5646>; rel="alternate"; title="JSON"; type="application/json"
        Link: <https://www.carreirasemfronteiras.com.br/>; rel=shortlink
        Expires: Sat, 21 Mar 2026 18:58:00 GMT
        Cache-Control: max-age=0
        X-Cache-Status: HIT
        X-Rocket-Nginx-Serving-Static: MISS
        Strict-Transport-Security: max-age=31536000;
        X-XSS-Protection: 1; mode=block
        X-Content-Type-Options: nosniff
        X-Frame-Options: SAMEORIGIN
        Referrer-Policy: no-referrer-when-downgrade
        Content-Security-Policy: default-src * 'unsafe-inline' 'unsafe-eval' data: blob:;
        Content-Encoding: gzip
```

==================

# ⚠️ Atenção ⚠️

Cuidado ao executar este comando ele irá fazer varredura que sobre tudo relacionado ao site:
```shell
dirb http://devsemfronteiras.tech
```

```txt
-----------------
DIRB v2.22    
By The Dark Raver
-----------------

START_TIME: Sat Mar 21 16:07:28 2026
URL_BASE: http://devsemfronteiras.tech/
WORDLIST_FILES: /usr/share/dirb/wordlists/common.txt

-----------------

GENERATED WORDS: 4612                                                          

---- Scanning URL: http://devsemfronteiras.tech/ ----
(!) WARNING: NOT_FOUND[] not stable, unable to determine correct URLs {30X}.
    (Try using FineTunning: '-f')
                                                                               
-----------------
END_TIME: Sat Mar 21 16:07:28 2026
DOWNLOADED: 0 - FOUND: 0
```

========================

The Harvester:
Pode obter todas as informações daquela aplicação na web inteira:
```shell
python3 theHarvester.py -d devsemfronteiras.tech -b all
```

======================

Nmap
Buscar informações através dessa ferramenta:
```shell
nmap -help
```

```txt
Nmap 7.98 ( https://nmap.org )
Usage: nmap [Scan Type(s)] [Options] {target specification}
TARGET SPECIFICATION:
  Can pass hostnames, IP addresses, networks, etc.
  Ex: scanme.nmap.org, microsoft.com/24, 192.168.0.1; 10.0.0-255.1-254
  -iL <inputfilename>: Input from list of hosts/networks
  -iR <num hosts>: Choose random targets
  --exclude <host1[,host2][,host3],...>: Exclude hosts/networks
  --excludefile <exclude_file>: Exclude list from file
HOST DISCOVERY:
  -sL: List Scan - simply list targets to scan
  -sn: Ping Scan - disable port scan
  -Pn: Treat all hosts as online -- skip host discovery
  -PS/PA/PU/PY[portlist]: TCP SYN, TCP ACK, UDP or SCTP discovery to given ports
  -PE/PP/PM: ICMP echo, timestamp, and netmask request discovery probes
  -PO[protocol list]: IP Protocol Ping
  -n/-R: Never do DNS resolution/Always resolve [default: sometimes]
  --dns-servers <serv1[,serv2],...>: Specify custom DNS servers
  --system-dns: Use OS's DNS resolver
  --traceroute: Trace hop path to each host
SCAN TECHNIQUES:
  -sS/sT/sA/sW/sM: TCP SYN/Connect()/ACK/Window/Maimon scans
  -sU: UDP Scan
  -sN/sF/sX: TCP Null, FIN, and Xmas scans
  --scanflags <flags>: Customize TCP scan flags
  -sI <zombie host[:probeport]>: Idle scan
  -sY/sZ: SCTP INIT/COOKIE-ECHO scans
  -sO: IP protocol scan
  -b <FTP relay host>: FTP bounce scan
PORT SPECIFICATION AND SCAN ORDER:
  -p <port ranges>: Only scan specified ports
    Ex: -p22; -p1-65535; -p U:53,111,137,T:21-25,80,139,8080,S:9
  --exclude-ports <port ranges>: Exclude the specified ports from scanning
  -F: Fast mode - Scan fewer ports than the default scan
  -r: Scan ports sequentially - don't randomize
  --top-ports <number>: Scan <number> most common ports
  --port-ratio <ratio>: Scan ports more common than <ratio>
SERVICE/VERSION DETECTION:
  -sV: Probe open ports to determine service/version info
  --version-intensity <level>: Set from 0 (light) to 9 (try all probes)
  --version-light: Limit to most likely probes (intensity 2)
  --version-all: Try every single probe (intensity 9)
  --version-trace: Show detailed version scan activity (for debugging)
SCRIPT SCAN:
  -sC: equivalent to --script=default
  --script=<Lua scripts>: <Lua scripts> is a comma separated list of
           directories, script-files or script-categories
  --script-args=<n1=v1,[n2=v2,...]>: provide arguments to scripts
  --script-args-file=filename: provide NSE script args in a file
  --script-trace: Show all data sent and received
  --script-updatedb: Update the script database.
  --script-help=<Lua scripts>: Show help about scripts.
           <Lua scripts> is a comma-separated list of script-files or
           script-categories.
OS DETECTION:
  -O: Enable OS detection
  --osscan-limit: Limit OS detection to promising targets
  --osscan-guess: Guess OS more aggressively
TIMING AND PERFORMANCE:
  Options which take <time> are in seconds, or append 'ms' (milliseconds),
  's' (seconds), 'm' (minutes), or 'h' (hours) to the value (e.g. 30m).
  -T<0-5>: Set timing template (higher is faster)
  --min-hostgroup/max-hostgroup <size>: Parallel host scan group sizes
  --min-parallelism/max-parallelism <numprobes>: Probe parallelization
  --min-rtt-timeout/max-rtt-timeout/initial-rtt-timeout <time>: Specifies
      probe round trip time.
  --max-retries <tries>: Caps number of port scan probe retransmissions.
  --host-timeout <time>: Give up on target after this long
  --scan-delay/--max-scan-delay <time>: Adjust delay between probes
  --min-rate <number>: Send packets no slower than <number> per second
  --max-rate <number>: Send packets no faster than <number> per second
FIREWALL/IDS EVASION AND SPOOFING:
  -f; --mtu <val>: fragment packets (optionally w/given MTU)
  -D <decoy1,decoy2[,ME],...>: Cloak a scan with decoys
  -S <IP_Address>: Spoof source address
  -e <iface>: Use specified interface
  -g/--source-port <portnum>: Use given port number
  --proxies <url1,[url2],...>: Relay connections through HTTP/SOCKS4 proxies
  --data <hex string>: Append a custom payload to sent packets
  --data-string <string>: Append a custom ASCII string to sent packets
  --data-length <num>: Append random data to sent packets
  --ip-options <options>: Send packets with specified ip options
  --ttl <val>: Set IP time-to-live field
  --spoof-mac <mac address/prefix/vendor name>: Spoof your MAC address
  --badsum: Send packets with a bogus TCP/UDP/SCTP checksum
OUTPUT:
  -oN/-oX/-oS/-oG <file>: Output scan in normal, XML, s|<rIpt kIddi3,
     and Grepable format, respectively, to the given filename.
  -oA <basename>: Output in the three major formats at once
  -v: Increase verbosity level (use -vv or more for greater effect)
  -d: Increase debugging level (use -dd or more for greater effect)
  --reason: Display the reason a port is in a particular state
  --open: Only show open (or possibly open) ports
  --packet-trace: Show all packets sent and received
  --iflist: Print host interfaces and routes (for debugging)
  --append-output: Append to rather than clobber specified output files
  --resume <filename>: Resume an aborted scan
  --noninteractive: Disable runtime interactions via keyboard
  --stylesheet <path/URL>: XSL stylesheet to transform XML output to HTML
  --webxml: Reference stylesheet from Nmap.Org for more portable XML
  --no-stylesheet: Prevent associating of XSL stylesheet w/XML output
MISC:
  -6: Enable IPv6 scanning
  -A: Enable OS detection, version detection, script scanning, and traceroute
  --datadir <dirname>: Specify custom Nmap data file location
  --send-eth/--send-ip: Send using raw ethernet frames or IP packets
  --privileged: Assume that the user is fully privileged
  --unprivileged: Assume the user lacks raw socket privileges
  -V: Print version number
  -h: Print this help summary page.
EXAMPLES:
  nmap -v -A scanme.nmap.org
  nmap -v -sn 192.168.0.0/16 10.0.0.0/8
  nmap -v -iR 10000 -Pn -p 80
SEE THE MAN PAGE (https://nmap.org/book/man.html) FOR MORE OPTIONS AND EXAMPLES
```

O comando que iremos usar é este aqui:
```shell
nmap -v -A devsemfronteiras.tech
```

```txt
Starting Nmap 7.98 ( https://nmap.org ) at 2026-03-21 16:16 -0300
NSE: Loaded 158 scripts for scanning.
NSE: Script Pre-scanning.
Initiating NSE at 16:16
Completed NSE at 16:16, 0.00s elapsed
Initiating NSE at 16:16
Completed NSE at 16:16, 0.00s elapsed
Initiating NSE at 16:16
Completed NSE at 16:16, 0.00s elapsed
Initiating Parallel DNS resolution of 1 host. at 16:16
Completed Parallel DNS resolution of 1 host. at 16:16, 0.02s elapsed
Initiating Ping Scan at 16:16
Scanning devsemfronteiras.tech (104.21.90.42) [4 ports]
Completed Ping Scan at 16:16, 0.02s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 16:16
Completed Parallel DNS resolution of 1 host. at 16:16, 0.50s elapsed
Initiating SYN Stealth Scan at 16:16
Scanning devsemfronteiras.tech (104.21.90.42) [1000 ports]
Discovered open port 8080/tcp on 104.21.90.42
Discovered open port 443/tcp on 104.21.90.42
Discovered open port 80/tcp on 104.21.90.42
Discovered open port 8443/tcp on 104.21.90.42
Completed SYN Stealth Scan at 16:16, 4.47s elapsed (1000 total ports)
Initiating Service scan at 16:16
Scanning 4 services on devsemfronteiras.tech (104.21.90.42)
Completed Service scan at 16:16, 12.27s elapsed (4 services on 1 host)
Initiating OS detection (try #1) against devsemfronteiras.tech (104.21.90.42)
Retrying OS detection (try #2) against devsemfronteiras.tech (104.21.90.42)
Initiating Traceroute at 16:16
Completed Traceroute at 16:16, 0.02s elapsed
Initiating Parallel DNS resolution of 2 hosts. at 16:16
Completed Parallel DNS resolution of 2 hosts. at 16:16, 0.50s elapsed
NSE: Script scanning 104.21.90.42.
Initiating NSE at 16:16
Completed NSE at 16:16, 5.09s elapsed
Initiating NSE at 16:16
Completed NSE at 16:16, 0.23s elapsed
Initiating NSE at 16:16
Completed NSE at 16:16, 0.00s elapsed
Nmap scan report for devsemfronteiras.tech (104.21.90.42)
Host is up (0.0046s latency).
Other addresses for devsemfronteiras.tech (not scanned): 172.67.194.239 2606:4700:3034::ac43:c2ef 2606:4700:3035::6815:5a2a
Not shown: 996 filtered tcp ports (no-response)
PORT     STATE SERVICE  VERSION
80/tcp   open  http     Cloudflare http proxy
|_http-server-header: cloudflare
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Did not follow redirect to https://carreirasemfronteiras.com.br/
443/tcp  open  ssl/http Cloudflare http proxy
|_http-server-header: cloudflare
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Did not follow redirect to https://carreirasemfronteiras.com.br/
| ssl-cert: Subject: commonName=devsemfronteiras.tech
| Subject Alternative Name: DNS:devsemfronteiras.tech, DNS:*.devsemfronteiras.tech
| Issuer: commonName=WE1/organizationName=Google Trust Services/countryName=US
| Public Key type: ec
| Public Key bits: 256
| Signature Algorithm: ecdsa-with-SHA256
| Not valid before: 2026-02-20T23:57:21
| Not valid after:  2026-05-22T00:56:08
| MD5:     e2a7 9e86 82e1 a640 1ce4 148c 54d5 529a
| SHA-1:   65af e128 b8ed 16d3 949a f346 16d4 32d4 7867 e1ac
|_SHA-256: bf5f f2c0 3fc8 c69f 9ad1 4586 3e44 469b 5206 4c1b 6bcb e32a e28a 4e19 2c73 9d9e
8080/tcp open  http     Cloudflare http proxy
|_http-server-header: cloudflare
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Did not follow redirect to https://carreirasemfronteiras.com.br/
8443/tcp open  ssl/http Cloudflare http proxy
|_http-title: Did not follow redirect to https://carreirasemfronteiras.com.br/
| ssl-cert: Subject: commonName=devsemfronteiras.tech
| Subject Alternative Name: DNS:devsemfronteiras.tech, DNS:*.devsemfronteiras.tech
| Issuer: commonName=WE1/organizationName=Google Trust Services/countryName=US
| Public Key type: ec
| Public Key bits: 256
| Signature Algorithm: ecdsa-with-SHA256
| Not valid before: 2026-02-20T23:57:21
| Not valid after:  2026-05-22T00:56:08
| MD5:     e2a7 9e86 82e1 a640 1ce4 148c 54d5 529a
| SHA-1:   65af e128 b8ed 16d3 949a f346 16d4 32d4 7867 e1ac
|_SHA-256: bf5f f2c0 3fc8 c69f 9ad1 4586 3e44 469b 5206 4c1b 6bcb e32a e28a 4e19 2c73 9d9e
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: cloudflare
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Aggressive OS guesses: Apple iOS 14.0 - 15.6 or tvOS 14.3 - 16.1 (Darwin 20.0.0 - 22.1.0) (89%), Android 7.0 (Linux 3.18) (86%), FreeBSD 11.0-RELEASE - 12.0-CURRENT (85%), FreeBSD 11.2-RELEASE - 11.3 RELEASE (85%), FreeBSD 12.0-RELEASE - 13.0-RELEASE (85%), Apple iOS 15.0 - 15.6 (Darwin 21.1.0 - 21.6.0) (85%), FreeBSD 11.2-RELEASE - 11.4-RELEASE (85%), FreeBSD 12.0-RELEASE - 13.1-RELEASE (85%)
No exact OS matches for host (test conditions non-ideal).
Uptime guess: 0.000 days (since Sat Mar 21 16:16:40 2026)
Network Distance: 2 hops
TCP Sequence Prediction: Difficulty=255 (Good luck!)
IP ID Sequence Generation: All zeros

TRACEROUTE (using port 80/tcp)
HOP RTT     ADDRESS
1   4.38 ms www.webgui.Nokiawifi.com (192.168.1.254)
2   3.74 ms 104.21.90.42

NSE: Script Post-scanning.
Initiating NSE at 16:16
Completed NSE at 16:16, 0.00s elapsed
Initiating NSE at 16:16
Completed NSE at 16:16, 0.00s elapsed
Initiating NSE at 16:16
Completed NSE at 16:16, 0.00s elapsed
Read data files from: /usr/share/nmap
OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 28.95 seconds
           Raw packets sent: 2074 (94.700KB) | Rcvd: 39 (2.352KB)
```
