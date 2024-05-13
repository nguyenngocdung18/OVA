![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/cf7b2147-041f-4750-ab51-f6b1c206df31)

# ENUMERATING
## ip sweep
![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/7bb869d2-d1a5-45ea-ac98-ffcbfed2a3f6)

## using nmap
![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/0e3960f5-47df-4949-9708-987a0011a9c9)

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/74cb16f0-b389-403e-acc0-5999bbbc0060)

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/e30c8af3-b046-47ce-b5fb-f1bbcac6414c)

=> ip của máy là 192.168.199.140 và đang mở 2 port 22, 80.

## using ffuf
![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/621e93b9-5986-4f23-85d1-74f3219bce17)

## view web
![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/6a7f8aa5-1909-4907-a123-850aeaf07ac4)

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/05d005ac-efac-492f-ac92-7163ae2c5739)

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/57d799d1-bd66-4643-8414-20eb7880e06c)

hmm.. file đã được tải lên thành công và chuyển tới /tmp
## using nuclei tool
![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/1933362e-9863-4f78-9bc8-b748b6e9f118)

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/4f68d86b-0c34-486f-8d0f-1ffb87da2b11)

truy cập từ đường dẫn tìm thấy khi dùng CVE-2018-7422 : ```http://192.168.199.140/wp-content/plugins/site-editor/editor/extensions/pagebuilder/includes/ajax_shortcode_pattern.php?ajax_path=/etc/passwd```

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/a5795c81-df26-4894-80db-e865d9df399e)

=> lỗi LFI

# EXPLOITING
thay đổi URL dẫn tới tệp /tmp/hello.php
![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/61cccf58-3ff7-4e5c-967b-a1e27a5f6db2)

sử dụng ```nc``` => thành công lấy được shell

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/24d306e6-2afb-45b2-99e9-95455b53f0f5)

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/a3354793-012d-4aeb-81a6-424b53bbffe4)

khi thử chạy câu lênh ```grep -r "password" /etc/``` thấy ```/usr/bin/mysqladmin -u root -h app109 password 'new-password'$```

![image](https://github.com/nguyenngocdung18/OVA/assets/134156226/cbab3a5a-c0f7-45c2-ac25-fab760b97ca4)
