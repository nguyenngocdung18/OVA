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

nhận thấy list trên chỉ fuzz các tệp tin nên đi thử với các list khác 

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/68b31ffc-3e13-4213-b2da-654f4a274faf)

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/4688b0ae-a0b2-446b-b88c-c8ce5faf9286)

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/53c4ff86-386b-4e59-8b79-84d97a0be6b8)

1 tài khoản có mật khẩu khá lạ so với các user khác: polo:YP1thBg5A8yc
## view web
![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/c83d199b-0b44-4ef0-8dea-b563c807e50a)

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/dd1c4cf4-e937-440b-990c-4096532899b0)

=> bản wordpress 6.2.2 
# EXPLOIT
## using wpscan

``` wpscan --url http://192.168.199.139/ -e u,vt,vp```

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/954af65b-152d-4202-898a-e0da5ea241ad)

user này cũng không thể tìm thấy thêm gì khác có thể khai thác 

## Connect to SSH server
![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/97e1a833-0b7e-4571-8d1a-4b4126cf7f59)

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/c65c871b-4d8d-4c4a-92b6-2a72b0a5bf8f)

# PRIVILEGE ESCALATION
Nhận thấy user này có trong group 4(adm)
![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/108e984c-0709-431f-8227-c103902ac08c)

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/5a851d42-b5d2-473f-a939-58ad29c89d82)

## using john the ripper
![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/cc4ebc75-1ce3-4c04-a44d-7bc0ca232493)
