# Comprehensive Shodan Dorks

---

## 📍 Geographic & Network Filters

### Location-Based
```
city:"Ludhiana"
city:"Bangalore"
city:"Punjab"
country:"IN"
country:"US"
country:"RU"
geo:"30.9010,75.8573"
geo:"56.913055,118.250862"
```

### Network & Organization
```
net:210.214.0.0/16
org:"Microsoft"
org:"Reliance"
org:"United States Department"
asn:AS55836
hostname:"example.com"
-hostname:"sub.example.com"
hostname:example.com,example.org
server:"gws"
```

### Operating Systems
```
os:"Windows 7"
os:"Windows Server 2022"
os:"Windows Server 2012"
os:"Linux 3.x"
```

### Temporal Filters
```
after:2025-01-01
before:2026-02-09
apache after:2025-01-01 before:2026-02-09
```

---

## 🔐 SSL/TLS & Certificates

```
ssl.cert.issuer.cn:example.com
ssl.cert.subject.cn:example.com
ssl.cert.expired:true
ssl.cert.serial:146473198
ssl.jarm:07d14d16d21d21d07c42d41d00041d24a458a375eef0c576d23a7bab9a9fb1
```

### SSH Fingerprints
```
dc:14:de:8e:d7:c1:15:43:23:82:25:81:d2:59:e8:c0
```

---

## 🖥️ Device Types

```
device:firewall
device:router
device:wap
device:webcam
device:media
device:"broadband router"
device:pbx
device:printer
device:switch
device:storage
device:specialized
device:phone
device:"voip"
device:"voip phone"
device:"voip adaptor"
device:"load balancer"
device:"print server"
device:terminal
device:remote
device:telecom
device:power
device:proxy
device:pda
device:bridge
```

---

## 🌐 Web Servers & Software

### Common Web Servers
```
product:apache
product:nginx
server:nginx
server:apache
server:microsoft
server:"cisco-ios"
```

### Specific Products
```
product:android
product:chromecast
cpe:apple
cpe:microsoft
cpe:nginx
cpe:cisco
```

### Web Technologies
```
http.html:/dana-na
http.title:"Index of /"
http.html:".pem"
onion-location
```

---

## 💾 Database Systems

### MySQL
```
product:"MySQL"
port:3306
mysql port:"3306"
```

### MongoDB
```
product:"MongoDB"
port:27017
"MongoDB Server Information" port:27017 -authentication
"Set-Cookie: mongo-express=" "200 OK"
```

### Elasticsearch
```
port:9200
port:9200 json
port:"9200" all:elastic
port:"9200" all:"elastic indices"
```

### Kibana
```
kibana content-length:217
```

### Redis
```
product:"Redis"
port:6379
product:"Redis key-value store"
```

### CouchDB
```
product:"CouchDB"
port:"5984"
Server: "CouchDB/2.1.0"
```

### PostgreSQL
```
port:5432 PostgreSQL
```

### Memcached
```
product:"Memcached"
port:11211
```

### Riak
```
port:8087 Riak
```

### Cassandra
```
product:"Cassandra"
```

---

## 🏭 ICS/SCADA/OT Systems

### Core Industrial Protocols
```
port:502                              # Modbus
port:102                              # Siemens S7
port:44818                            # EtherNet/IP
port:47808                            # BACnet
port:5094 hart-ip                     # HART-IP
port:9600 "response code"             # Omron FINS
port:2404 "asdu address"              # IEC 60870-5-104
port:20000 "source address"           # DNP3
port:18245,18246 product:"general electric"  # GE-SRTP
port:1911,4911 product:Niagara        # Niagara Fox
port:5006,5007 product:mitsubishi     # MELSEC-Q
port:2455 "operating system"          # CODESYS
port:1962 PLC                         # PCWorx
port:789 product:"Red Lion Controls"  # Crimson v3.0
port:20547 PLC                        # ProConOS
```

### Critical Infrastructure
```
"in-tank inventory" port:10001                    # Gas Station Pumps
"privileged command" GET                          # Fuel Pumps
P372 "ANPR enabled"                               # License Plate Readers
mikrotik streetlight                              # Traffic Lights
"voter system serial" country:US                  # Voting Machines
NCR port:161                                      # ATMs
"Cisco IOS" "ADVIPSERVICESK9_LI-M"               # Lawful Intercept
"[2J[H Encartele Confidential"                   # Prison Phones
http.title:"Tesla PowerPack System" http.component:"d3" -ga3ca4f2  # Tesla Powerpacks
"Server: gSOAP/2.8" "Content-Length: 583"        # EV Chargers
"Cobham SATCOM" OR ("Sailor" "VSAT")             # Maritime
title:"Slocum Fleet Mission Control"             # Submarine Control
"Server: CarelDataServer" "200 Document follows" # Refrigeration
http.title:"Nordex Control" "Windows 2000 5.0 x86"  # Wind Turbines
"[1m[35mWelcome on console"                      # GPS Trackers
```

### Industrial Equipment
```
"DICOM Server Response" port:104                 # Medical X-Ray
"Server: EIG Embedded Web Server" "200 Document follows"  # Electricity Meters
"Siemens, SIMATIC" port:161                      # Siemens Automation
"Server: Microsoft-WinCE" "Content-Length: 12581"  # Siemens HVAC
"HID VertX" port:4070                            # Door Controllers
"log off" "select the appropriate"               # Railroad
title:"xzeres wind"                              # Wind Turbines
"html:PIPS Technology ALPR Processors"           # ALPR
"Server: Prismview Player"                       # Billboards
```

---

## 📹 IP Cameras & Surveillance

### Generic Cameras
```
title:camera
webcam has_screenshot:true
title:camera webcam has_screenshot:true
```

### Specific Brands
```
"d-Link Internet Camera, 200 OK"
"Hipcam RealServer/V1.0"
"Server: yawcam" "Mime-Type: text/html"
("webcam 7" OR "webcamXP") http.component:"mootools" -401
"Server: IP Webcam Server" "200 OK"
html:"DVR_H264 ActiveX"
NETSurveillance uc-httpd
Server: uc-httpd 1.0.0
product:"Reolink"
port:37777                            # DVR/NVR ports
inurl:/view.shtml
```

---

## 🏠 IoT & Smart Home Devices

```
"\x08_airplay" port:5353              # AirPlay
"Chromecast:" port:8008               # Chromecast
"Server: AV_Receiver" "HTTP/1.1 406"  # Yamaha
"Model: PYNG-HUB"                     # Crestron
port:1883                             # MQTT brokers
product:"Tuya"                        # Smart home
port:9999 "Tasmota"                   # ESP8266
```

---

## ☁️ Cloud Services

### Amazon Web Services (AWS)
```
http.title:"Amazon S3"
"AccessDenied"
"NoSuchBucket"
bucket found
http.html:"AWS Management Console"
```

### Microsoft Azure
```
Server: "Windows-Azure-Blob"
http.html:"Blob"
port:8080 "Azure" "Blob"
```

### Google Cloud Platform (GCP)
```
http.title:"Google Cloud Storage"
port:443 "storage.googleapis.com"
```

### Kubernetes & Containers
```
port:6443 "kube-apiserver"
kubernetes port:6443
"Docker Containers:" port:2375
"Docker-Distribution-Api-Version: registry" -gitlab port:5000
```

---

## 🔌 Remote Access Services

### Remote Desktop Protocol (RDP)
```
"\x03\x00\x00\x0b\x06\xd0\x00\x00\x124\x00"
port:3389
```

### VNC
```
"authentication disabled" port:5900,5901
"authentication disabled" "RFB 003.008"
```

### Telnet
```
port:23 "root@" -login -password -name -Session
port:23 console gateway
"polycom command shell" -failed port:23
nport -keyin port:23
```

---

## 🎯 Command & Control (C2) Infrastructure

```
product:"cobalt strike team server"
product:"Cobalt Strike Beacon"
ssl.cert.serial:146473198
ssl.jarm:07d14d16d21d21d07c42d41d00041d24a458a375eef0c576d23a7bab9a9fb1
http.html_hash:-1957161625 product:"Brute Ratel C4"
ssl:"Covenant" http.component:"Blazor"
ssl:"MetasploitSelfSignedCA"
```

---

## 🌐 Network Infrastructure

### Enterprise Gateways
```
title:"citrix gateway"
title:"Weave Scope" http.favicon.hash:567176827
```

### Jenkins
```
"X-Jenkins" "Set-Cookie: JSESSIONID" http.title:"Dashboard"
x-jenkins 200 http.title:"Dashboard"
```

### DNS & Network Services
```
"dnsmasq-pi-hole" "Recursion: enabled"
port:53 "Recursion: Enabled"
hacked-router-help-sos
```

---

## 📂 NAS & File Sharing

### SMB/CIFS
```
"Authentication: disabled" port:445
"Authentication: disabled" NETLOGON SYSVOL -unix port:445
"Authentication: disabled" "Shared this folder to access QuickBooks files OverNetwork" -unix port:445
```

### FTP
```
"220" "230 Login successful." port:21
port:21 proftpd
```

### NAS Devices
```
"Set-Cookie: iomega=" -"manage/login.html"
Redirecting sencha port:9000             # Buffalo
"Server: Logitech Media Server" "200 OK"
"X-Plex-Protocol" "200 OK" port:32400    # Plex
"CherryPy/5.1.0" "/home"                 # Tautulli
```

---

## 🚨 Vulnerabilities & CVEs

```
vuln:CVE-2021-44228                      # Log4Shell
vuln:CVE-2017-5689                       # Intel AMT
HP-ILO-4 !"HP-ILO-4/2.53" port:1900
"Intel(R) Active Management Technology" port:623,664,16992
"smart install client active"
"Press Enter for Setup Mode port:9999"
```

---

## ⚠️ Web Misconfigurations

```
http.html:"* The wp-config.php creation script uses this file"
html:"def_wirelesspassword"
http.title:"Index of /" http.html:".pem"
```

---

## 🎯 Quick Recon Templates

### India-Focused Reconnaissance
```
country:IN city:"Ludhiana" port:80,443,22,3389
country:IN port:9200 OR port:27017 OR port:6379
```

### ICS/SCADA Discovery
```
port:502 OR port:102 OR port:44818 OR port:47808 country:IN
port:502 OR port:102 OR port:44818 OR port:47808
```

### Exposed Database Services
```
port:9200 OR port:27017 OR port:6379 OR port:11211
port:3306 OR port:5432 OR port:1433
```

### Camera Surveillance
```
title:camera has_screenshot:true country:IN
title:camera has_screenshot:true
```

### Cloud Misconfigurations
```
http.title:"Amazon S3" OR Server:"Windows-Azure-Blob"
"AccessDenied" OR "NoSuchBucket" OR http.html:"Blob"
```

### Multi-Service Scan (High Value Targets)
```
port:22,23,80,443,445,3389,8080,8443
country:IN (port:22 OR port:3389 OR port:445)
```

---

## 📊 Port Reference Quick Guide

| Port | Service | Dork Example |
|------|---------|--------------|
| 21 | FTP | `port:21 proftpd` |
| 22 | SSH | `port:22` |
| 23 | Telnet | `port:23 console` |
| 53 | DNS | `port:53 "Recursion: Enabled"` |
| 80 | HTTP | `port:80` |
| 102 | S7 (SCADA) | `port:102` |
| 443 | HTTPS | `port:443` |
| 445 | SMB | `port:445 "Authentication: disabled"` |
| 502 | Modbus | `port:502` |
| 1883 | MQTT | `port:1883` |
| 3306 | MySQL | `port:3306` |
| 3389 | RDP | `port:3389` |
| 5432 | PostgreSQL | `port:5432` |
| 5900 | VNC | `port:5900` |
| 6379 | Redis | `port:6379` |
| 8080 | HTTP Alt | `port:8080` |
| 9200 | Elasticsearch | `port:9200` |
| 11211 | Memcached | `port:11211` |
| 27017 | MongoDB | `port:27017` |

---

## 💡 Usage Best Practices

1. **Combine filters** for precision: `country:IN port:3306 product:"MySQL"`
2. **Use exclusions** to filter noise: `-authentication -login`
3. **Screenshot verification**: Add `has_screenshot:true` to visual confirmation
4. **Time-based hunting**: Use `after:` and `before:` for recent exposures
5. **Verify findings** before reporting to reduce false positives

---

## ⚖️ Legal Disclaimer

This reference is intended exclusively for authorized security professionals conducting:
- Penetration testing with written permission
- Security Operations Center (SOC) monitoring
- Open Source Intelligence (OSINT) within legal boundaries
- Vulnerability research on owned/authorized systems

**Unauthorized access to computer systems is illegal.** Always ensure proper authorization and comply with applicable laws and regulations.

---
