![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/183d55ca-013c-4b3d-9c8e-8542a434af18)

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/995f22f2-eee8-44b8-8cbb-93407a75209b)

# ENUMERATING
## Scan IP
using ```arp-scan + ip range```

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/ec49a939-2897-4216-a146-caf291769b28)

or ```nmap -v + ip range```

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/affaddad-07d0-4c14-a9c3-938e669d7a42)

có vẻ như máy này có ip là 192.168.199.139 và đang mở 2 port 22, 80

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/cce68ed3-4b1f-46db-b8b2-3070e1efb5a9)

## using ffuf 
![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/2240e1b4-04a2-45df-b2dd-91ff4153c26e)

## view web
![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/c83d199b-0b44-4ef0-8dea-b563c807e50a)

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/dd1c4cf4-e937-440b-990c-4096532899b0)

=> bản wordpress 6.2.2 

## using wpscan

``` wpscan --url http://192.168.199.139/ -e u,vt,vp```

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/954af65b-152d-4202-898a-e0da5ea241ad)

```wpscan --url http://192.168.199.139/ -P /usr/share/wordlists/rockyou.txt --usernames wordpress```
## Fuzzing web
