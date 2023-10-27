## 1. Scenario

![XSS_SQLiteM_S0.png](img/XSS_SQLiteM_S0.png)

https://exchange.xforce.ibmcloud.com/vulnerabilities/72141

![XSS_SQLiteM_S1.png](img/XSS_SQLiteM_S0.png)

---
## 2. Vulnerability

Following description from **xforce**, I tried with following payload and it's reflected xss on `sqlite/index.php`
- Payload: `dbsel='<script>alert(1337)</script>`

![XSS_SQLiteM_V1.png](img/XSS_SQLiteM_V1.png)

![XSS_SQLiteM_V0.png](img/XSS_SQLiteM_V0.png)

---
